---
title: "Nhật Ký Tuần 8"
date: 2025-10-27
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục Tiêu Tuần 8:

- Hoàn thành đề xuất dự án Hệ Thống Hỗ Trợ Hiến Máu (BDSS)
- Thiết kế kiến trúc AWS cloud
- Xác định công nghệ và yêu cầu kỹ thuật
- Ước tính ngân sách và timeline

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1-2 | - Nghiên cứu yêu cầu hệ thống hiến máu <br> - Xác định phạm vi và mục tiêu dự án <br> - Định nghĩa nhóm người dùng và tính năng | 2025/10/27 | 2025/10/28 | Nghiên cứu điển hình hệ thống y tế |
| 3-4 | - Thiết kế sơ đồ kiến trúc AWS <br>&emsp; + Frontend: Route 53, CloudFront, S3 <br>&emsp; + Backend: API Gateway, EC2, RDS <br>&emsp; + Bảo mật: Cognito, IAM <br> - Xác định tech stack: React+Vite, Spring Boot, MySQL | 2025/10/29 | 2025/10/30 | <https://aws.amazon.com/architecture/> |
| 5-6 | - Ước tính chi phí dịch vụ AWS <br> - Tạo timeline triển khai <br> - Đánh giá rủi ro và chiến lược giảm thiểu | 2025/10/31 | 2025/11/01 | <https://calculator.aws/> |
| 7 | - Hoàn thiện tài liệu đề xuất <br> - Chuẩn bị trình bày <br> - Đánh giá tuần | 2025/11/02 | 2025/11/02 | Hướng dẫn viết kỹ thuật |

### Thành Tựu Tuần 8:

- **Hoàn Thành Đề Xuất Dự Án:**
  - Nghiên cứu thách thức quản lý hiến máu và định nghĩa giải pháp
  - Xác định vấn đề chính: quy trình thủ công, tìm kiếm không hiệu quả, thiếu đồng bộ
  - Định nghĩa 4 nhóm người dùng: Khách, Thành viên, Nhân viên, Quản trị viên

- **Thiết Kế Kiến Trúc AWS:**
  - Thiết kế kiến trúc 3 tầng: Frontend (Route 53, CloudFront, S3), Backend (API Gateway, EC2, RDS), Bảo mật (Cognito, IAM)
  - Tạo sơ đồ kiến trúc hiển thị tương tác các thành phần
  - Lập kế hoạch VPC với public/private subnets để bảo mật

- **Công Nghệ Sử Dụng:**
  - **Frontend:** React + Vite
  - **Backend:** Spring Boot trên EC2
  - **Database:** MySQL trên RDS
  - **Xác thực:** Cognito (4 vai trò)
  - **CI/CD:** GitLab → CodePipeline → EC2
  - **Giám sát:** CloudWatch, SNS

- **Ngân Sách & Timeline:**
  - Ước tính ~$8.90/tháng cho dịch vụ AWS
  - Lập kế hoạch timeline triển khai 5 tháng
  - Xác định tối ưu chi phí với Free Tier

- **Đánh Giá Rủi Ro:**
  - Xác định rủi ro kỹ thuật, bảo mật và ngân sách
  - Định nghĩa chiến lược giảm thiểu (backups, WAF, monitoring)

### Các Thách Thức Gặp Phải:

- **Thiết Kế Kiến Trúc:** Cân bằng đơn giản và khả năng mở rộng → Sử dụng thiết kế modular
- **Kiểm Soát Chi Phí:** Giữ trong ngân sách → Tận dụng Free Tier và right-sized instances
- **Bảo Mật:** Tuân thủ dữ liệu y tế → Triển khai mã hóa và IAM policies nghiêm ngặt

### Bài Học Chính:

- Học các nguyên tắc thiết kế kiến trúc AWS
- Hiểu tầm quan trọng của lập kế hoạch và tài liệu dự án
- Có kinh nghiệm ước tính chi phí và đánh giá rủi ro

### Tài Liệu Tham Khảo:

**Kiến Trúc AWS:**
- [AWS Architecture Center](https://aws.amazon.com/architecture/) - Best practices và kiến trúc tham khảo
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/) - Nguyên tắc thiết kế
- [AWS Solutions Library](https://aws.amazon.com/solutions/) - Giải pháp được xây dựng sẵn

**Tài Liệu Dịch Vụ AWS:**
- [Amazon EC2](https://docs.aws.amazon.com/ec2/) - Compute instances
- [Amazon RDS](https://docs.aws.amazon.com/rds/) - Managed database
- [Amazon API Gateway](https://docs.aws.amazon.com/apigateway/) - API management
- [Amazon Cognito](https://docs.aws.amazon.com/cognito/) - User authentication
- [AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/) - CI/CD automation
- [Amazon CloudFront](https://docs.aws.amazon.com/cloudfront/) - Content delivery
- [Amazon SNS](https://docs.aws.amazon.com/sns/) - Notification service

**Quản Lý Chi Phí:**
- [AWS Pricing Calculator](https://calculator.aws/) - Công cụ ước tính chi phí
- [AWS Cost Management](https://aws.amazon.com/aws-cost-management/) - Tối ưu chi phí
- [AWS Free Tier](https://aws.amazon.com/free/) - Chi tiết free tier

**Quản Lý Dự Án:**
- [Project Management Best Practices](https://www.pmi.org/) - Hướng dẫn PMI
- [Agile Methodology](https://www.agilealliance.org/) - Phát triển Agile
- [Risk Management Framework](https://www.nist.gov/cyberframework) - NIST framework

**Healthcare IT:**
- [HIPAA Compliance on AWS](https://aws.amazon.com/compliance/hipaa-compliance/) - Bảo mật dữ liệu y tế
- [Healthcare Solutions on AWS](https://aws.amazon.com/health/) - Giải pháp ngành
