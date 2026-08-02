---
title: "Worklog Tuần 2"
date: 2026-06-22
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---
### Mục tiêu Tuần 2

* Tìm hiểu các khái niệm mạng AWS VPC: VPC CIDR block, public/private subnets, Internet Gateway, bảng định tuyến (Route Table), Security Group và Network ACL.
* Xây dựng môi trường phòng thí nghiệm phát hiện đe dọa trên máy trạm Windows / FLARE-VM.
* Cài đặt Elastic Agent, Sysmon (với cấu hình SwiftOnSecurity) và Suricata IDS để thu thập đa tầng telemetry máy trạm và mạng.
* Thực thi 7 kịch bản mô phỏng tấn công Endpoint sử dụng Atomic Red Team (PowerShell fileless, LSASS dumping, Run key persistence, Scheduled task, DLL injection, Network scan, C2 beaconing).
* Phát triển các quy tắc phát hiện KQL tùy chỉnh, lập trình công cụ SOAR Python (`elk_discord_alerter.py`) gửi cảnh báo về Discord và hoàn thiện 4 báo cáo săn đe dọa (Threat Hunt Reports).

### Các công việc triển khai trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu mạng AWS VPC: public/private subnet, bảng định tuyến, Internet Gateway, Security Group vs Network ACL.<br>- Thiết kế quy tắc phân vùng mạng và thiết lập cơ chế cách ly an toàn cho môi trường lab mô phỏng tấn công. | 22/06/2026 | 22/06/2026 | <https://000003.awsstudygroup.com><br><https://000092.awsstudygroup.com> |
| 3 | - Khởi tạo máy trạm thử nghiệm Windows 10 / FLARE-VM trên môi trường lab.<br>- Cài đặt Sysmon với cấu hình SwiftOnSecurity (`sysmonconfig.xml`) để thu thập Event ID 1 (Process Creation), Event ID 10 (Process Access), Event ID 13 (Registry Modification).<br>- Cài đặt Elastic Agent kết nối về Elastic SIEM Fleet và cấu hình Suricata IDS bắt gói tin mạng. | 23/06/2026 | 23/06/2026 | <https://000048.awsstudygroup.com><br><https://000062.awsstudygroup.com> |
| 4 | - Cài đặt Atomic Red Team framework trên máy trạm Windows.<br>- Thực thi 4 kịch bản tấn công Endpoint đầu tiên:<br>&emsp;+ Kịch bản 1 (T1059.001): PowerShell Fileless Execution (Base64 encoded command).<br>&emsp;+ Kịch bản 2 (T1003.001): LSASS Memory Dump qua `rundll32.exe` & `comsvcs.dll` (LOLBin abuse).<br>&emsp;+ Kịch bản 3 (T1547.001): Registry Run Key Persistence.<br>&emsp;+ Kịch bản 4 (T1053.005): Scheduled Task Persistence qua `schtasks.exe`. | 24/06/2026 | 24/06/2026 | Atomic Red Team Docs<br><https://000044.awsstudygroup.com> |
| 5 | - Thực thi 3 kịch bản tấn công Endpoint tiếp theo:<br>&emsp;+ Kịch bản 5 (T1055.001): DLL Injection qua `mavinject.exe`.<br>&emsp;+ Kịch bản 6 (T1046): Network Service Discovery & Port Scanning qua Nmap/Suricata.<br>&emsp;+ Kịch bản 7 (T1071.001): C2 Beaconing với malicious HTTP User Agent.<br>- Lập trình công cụ SOAR Python (`elk_discord_alerter.py`) truy vấn Elastic Security API và tự động đẩy cảnh báo sự cố kèm MITRE ID về kênh Discord qua webhook. | 25/06/2026 | 25/06/2026 | <https://000066.awsstudygroup.com><br>Elastic Security API Docs |
| 6 | - Xây dựng, kiểm thử và tối ưu 7 quy tắc phát hiện KQL/EQL tương ứng trên Elastic SIEM.<br>- Tiến hành 4 chiến dịch Threat Hunting chủ động trên dữ liệu log lịch sử:<br>&emsp;+ Hunt 1: LOLBin Abuse (`rundll32`, `mavinject`).<br>&emsp;+ Hunt 2: LSASS Reconnaissance (tinh chỉnh exclusion cho `svchost.exe` / `0x1410`).<br>&emsp;+ Hunt 3: Persistence Audit (vòng đời tạo và xóa Run key / Scheduled task).<br>&emsp;+ Hunt 4: C2 Beaconing (bổ sung luật Sysmon script egress).<br>- Hoàn thiện 4 báo cáo Threat Hunt (`hunt1` - `hunt4`). | 26/06/2026 | 26/06/2026 | Elastic SIEM Detection Engine<br>MITRE ATT&CK Framework |

### Kết quả đạt được Tuần 2

* Nắm vững kiến thức mạng AWS VPC, mô hình chia subnet, bảng định tuyến và cơ chế kiểm soát truy cập tường lửa Security Group / NACL.
* Xây dựng thành công môi trường máy trạm thử nghiệm với đầy đủ Elastic Agent, Sysmon và Suricata IDS thu thập đa tầng telemetry.
* Mô phỏng thành công 7 kịch bản tấn công Endpoint theo chuẩn MITRE ATT&CK bằng Atomic Red Team.
* Kỹ thuật hóa bộ quy tắc phát hiện KQL/EQL trên Elastic SIEM và triển khai công cụ SOAR Python gửi cảnh báo tức thì qua Discord webhook.
* Thực hiện 4 chiến dịch Threat Hunting chủ động trên dữ liệu log lịch sử, phát hiện khoảng trống giám sát và tinh chỉnh luật phát hiện.
