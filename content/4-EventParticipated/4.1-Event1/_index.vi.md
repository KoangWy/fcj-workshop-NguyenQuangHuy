---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch "AWS FC Community Day"

### Mục Đích Của Sự Kiện

- Chia sẻ kinh nghiệm thực tế, trải nghiệm và góc nhìn từ môi trường doanh nghiệp về Cloud & AI.
- Cập nhật các công nghệ tiên phong: Agentic Platform, Voice AI tiếng Việt, AWS DevOps Agent, Amazon Q Business/Developer và Private Security cho MCP Server.
- Kết nối cộng đồng kỹ sư, chuyên gia và định hướng con đường phát triển sự nghiệp (Career Path) cho sinh viên/kỹ sư trẻ.

### Danh Sách Diễn Giả

- **Steve Trần** - Founder @ Cloud Thinker (Cựu Solution Architect @ AWS)
- **Hiếu Nghị** - Cloud Engineer @ Renova Cloud
- **Anh Kiệt** - AWS Study Builder / Student AWS Cloud Club
- **Anh Trung** - Founder & CEO @ R AI (Cựu YC Founder)
- **Chị Bảo** - Cloud Engineer @ Cloud Kinetics
- **Anh Nguyên Nguyễn** - Cloud Engineer @ Cloud Kinetics
- **Anh Trường ** - AI Solution Architect @ Noventic
- **Chị Minh Anh** - Solution Specialist @ Noventic
- **Toàn Nguyễn** - AWS Security Builder

### Nội Dung Nổi Bật

#### Session 1: Cloud Architecture & Agentic Platform cho Infrastructure (Steve Trần - Cloud Thinker)

- **Hành trình sự nghiệp (Career Path)**: Chia sẻ định hướng phát triển từ Developer/DevOps lên Solution Architect tại AWS và Founder startup công nghệ.
- **Giải quyết Complexity & Tech Debt**: Ứng dụng AI Agent hỗ trợ kỹ sư vận hành hạ tầng Production critical (Incident investigation, IaC code review, FinOps/Cost Optimization, Security/Pen testing).
- **Kiến trúc Single-Agent vs Multi-Agent**: Phân tích lý do chọn Multi-Agent (Specialist agents) để tối ưu chi phí LLM, giảm tải Context Window và hỗ trợ Role-Based Access Control (RBAC).

#### Session 2: Voice AI Agent cho Tiếng Việt & Demo AWS Bedrock (Hiếu Nghị, Anh Kiệt, Anh Trung)

- **So sánh kiến trúc Voice AI**: Phân tích trade-offs giữa Speech-to-Speech và mô hình 3 bước **STT → LLM (Tool Calling) → TTS** (phù hợp với Tiếng Việt - low resource language, đảm bảo guardrails và kiểm soát output real-time).
- **Thách thức vận hành thực tế**: Phân biệt giới tính (xưng hô anh/chị), cơ chế ngắt lời thông minh (VAD/Context awareness), xử lý giọng vùng miền (accent) và Handoff to Human Agent mượt mà.
- **Live Demo**: Voice Agent tra cứu thông tin sản phẩm Apple/MacBook sử dụng AWS Bedrock Agent Core kết hợp Knowledge Base.

#### Session 3: AWS DevOps AI Agent cho Incident Management (Chị Bảo, Nguyên Nguyễn - Cloud Kinetics)

- **Khắc phục Fragmented Telemetry**: Tự động hóa quy trình Root Cause Analysis (RCA), giúp giảm đáng kể thời gian MTTD và MTTR cho hệ thống Microservices cỡ lớn.
- **6 Trụ cột cốt lõi**: Context Learning (Topology mapping), Control (Least Privilege), Integration (MCP), Collaboration (Slack/Jira), Convenience, Cost-Effective.
- **Quy trình xử lý 4 bước**: Trigger & Classification → Investigation (RCA) → Mitigation Plan (Human Approval) → Long-term Improvement.
- **Live Demo**: Giả lập tấn công DDoS vào hệ thống E-commerce chạy ECS/ALB, DevOps Agent khoanh vùng nguyên nhân và đưa ra lệnh khắc phục trực tiếp.

#### Session 4: Amazon Q - Ứng Dụng AI Automation Trong Doanh Nghiệp & HR (Anh Trường, Chị Minh Anh - Noventic)

- **Giải quyết bài toán HR**: Tự động hóa lọc CV (Screening), loại bỏ đánh giá cảm tính, bảo mật dữ liệu doanh nghiệp so với các AI public.
- **Khả năng kết nối dữ liệu**: Đọc dữ liệu đa dạng (SharePoint, Google Drive, S3, Jira, Database...) thông qua MCP Connectors và quản trị bảo mật chuẩn AWS.
- **Skill Customization**: Xây dựng skill tự động hóa tuyển dụng — phân tích CV theo JD, chấm điểm match %, dự toán mức lương, lập lịch phỏng vấn qua Outlook và xuất Dashboard báo cáo HTML.

#### Session 5: Private Security Architecture Cho Amazon Q & MCP Server (Toàn Nguyễn, Hiếu Nghị)

- **Nguy cơ bảo mật Public Endpoints**: Rủi ro tấn công DDoS, Man-in-the-Middle (MitM) và rò rỉ dữ liệu khi kết nối MCP Server qua Public Internet.
- **Kiến trúc Private Security**: Đặt MCP Server trong Private Subnet, giao tiếp an toàn qua VPC Interface Endpoints, AWS Cognito Authentication, Application Load Balancer (TLS/SSL) và Route 53 Private Resolver.
- **Live Demo & Cost Estimation**: Truy vấn thông tin hệ thống real-time qua Private MCP Server và đánh giá chi phí vận hành hạ tầng bảo mật.

### Những Gì Học Được

#### Tư Duy Kiến Trúc & Vận Hành

- **Human-in-the-loop**: AI Agents đóng vai trò trợ lực (Productivity Multiplier) chứ không thay thế hoàn toàn con người trong các hệ thống Production critical.
- **Tối ưu hóa tài nguyên**: Lựa chọn mô hình Multi-Agent chuyên biệt để tối ưu hóa token, giảm bớt loãng context và phân quyền chính xác.

#### Kỹ Thuật Voice AI & LLM Integration

- Hiểu rõ cơ chế xây dựng Voice AI cho ngôn ngữ ít tài nguyên như Tiếng Việt thông qua pipeline STT-LLM-TTS.
- Tầm quan trọng của Tool Calling, Guardrails và xử lý ngắt lời dựa trên ngữ cảnh thực tế.

#### Bảo Mật & Tự Động Hóa Enterprise

- Áp dụng chuẩn bảo mật Zero Trust cho MCP Server bằng VPC Endpoints và Private DNS.
- Tự động hóa các quy trình nghiệp vụ (DevOps, HR, FinOps) bằng việc kết nối dữ liệu nội bộ an toàn.

### Ứng Dụng Vào Công Việc

- **Triển khai thử nghiệm AWS DevOps Agent**: Lập kịch bản phân tích log/trace tự động cho các sự cố hệ thống trong lab/project.
- **Xây dựng Custom Skills với Amazon Q**: Thử nghiệm viết các file skill instruction (.md) để tự động hóa việc lọc tài liệu, phân tích yêu cầu hoặc xuất báo cáo.
- **Áp dụng kiến trúc Private VPC cho MCP**: Đảm bảo các tích hợp giữa AI Agent và hệ thống nội bộ tuân thủ phân quyền IAM Least Privilege và kết nối private.

### Trải nghiệm trong event

Tham gia sự kiện **AWS FC Community Day** là một trải nghiệm rất bổ ích và giàu tính thực tiễn:

- **Học hỏi từ các chuyên gia thực chiến**: Diễn giả từ các đơn vị lớn (Cloud Thinker, Renova Cloud, R AI, Cloud Kinetics, Noventic) mang đến những góc nhìn thực tế về bài toán vận hành và kinh doanh.
- **Live Demo ấn tượng**: Trực tiếp theo dõi các demo về Voice Agent tiếng Việt, DevOps Agent xử lý tấn công DDoS và Amazon Q lọc CV tự động giúp hình dung rõ ràng về khả năng ứng dụng thực tế.
- **Cân bằng giữa Kỹ thuật & Nghiệp vụ**: Sự kiện mang lại cái nhìn toàn diện từ hạ tầng sâu (Private VPC, Multi-Agent) đến ứng dụng nghiệp vụ doanh nghiệp (HR Automation, Cost Optimization).

#### Một số hình ảnh khi tham gia sự kiện
![Hình ảnh tham gia online](./../../../static/images/4-EventParticipated/event1.png)
