---
title: "Nhật Ký Tuần 9"
date: 2025-11-03
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục Tiêu Tuần 9:

- Hoàn thiện đề xuất dự án và nhận phê duyệt
- Thiết lập môi trường phát triển
- Khởi tạo cấu trúc dự án Frontend và Backend
- Cấu hình nền tảng hạ tầng AWS

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1-2 | - Trình bày đề xuất dự án cho team <br> - Nhận feedback và phê duyệt <br> - Hoàn thiện yêu cầu kỹ thuật | 2025/11/03 | 2025/11/04 | Tài liệu đề xuất dự án |
| 3-4 | - Thiết lập môi trường phát triển <br>&emsp; + Cài đặt Node.js, Maven, AWS CLI <br>&emsp; + Cấu hình Git repository <br> - Khởi tạo cấu trúc dự án <br>&emsp; + Tạo React + Vite frontend <br>&emsp; + Tạo Spring Boot backend | 2025/11/05 | 2025/11/06 | <https://vitejs.dev/> <br> <https://spring.io/> |
| 5-7 | - Cấu hình nền tảng AWS <br>&emsp; + Tạo VPC và subnets <br>&emsp; + Thiết lập Security Groups <br>&emsp; + Tạo RDS MySQL database <br>&emsp; + Cấu hình S3 buckets <br> - Kiểm tra kết nối database | 2025/11/07 | 2025/11/09 | <https://docs.aws.amazon.com/> |

### Thành Tựu Tuần 9:

- **Phê Duyệt Đề Xuất:**
  - Trình bày đề xuất Hệ Thống Hỗ Trợ Hiến Máu
  - Nhận phê duyệt từ mentors và team
  - Hoàn thiện tech stack: React+Vite, Spring Boot, MySQL trên RDS

- **Môi Trường Phát Triển:**
  - Cài đặt và cấu hình các công cụ phát triển
  - Thiết lập Git repository cho version control
  - Tạo cấu trúc dự án với thư mục FE và BE riêng biệt
  - Khởi tạo React frontend với Vite build tool
  - Tạo Spring Boot backend với Maven

- **Thiết Lập Hạ Tầng AWS:**
  - Tạo VPC với public và private subnets
  - Cấu hình Security Groups cho EC2, RDS và ALB
  - Provisioning RDS MySQL database instance
  - Tạo S3 buckets cho frontend hosting và backend artifacts
  - Kiểm tra kết nối database từ môi trường local

### Các Thách Thức Gặp Phải:

- **Cấu Hình VPC:** Hiểu về subnet routing → Nghiên cứu tài liệu AWS VPC
- **Kết Nối RDS:** Vấn đề connection timeout → Cấu hình Security Group inbound rules đúng cách
- **Cấu Trúc Dự Án:** Tổ chức monorepo → Tách riêng thư mục FE, BE và AWS

### Bài Học Chính:

- Học các kiến thức cơ bản về VPC networking và thiết kế subnet
- Hiểu cấu hình security group cho RDS
- Có kinh nghiệm khởi tạo và cấu trúc dự án

### Tài Liệu Tham Khảo:

- [React + Vite](https://vitejs.dev/guide/)
- [Spring Boot](https://spring.io/guides/gs/spring-boot/)
- [AWS VPC](https://docs.aws.amazon.com/vpc/)
- [Amazon RDS](https://docs.aws.amazon.com/rds/)



