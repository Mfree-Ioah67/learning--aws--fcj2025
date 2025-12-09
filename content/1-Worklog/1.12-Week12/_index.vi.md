---
title: "Nhật Ký Tuần 12"
date: 2025-11-24
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục Tiêu Tuần 12:

- Thiết lập CI/CD pipeline với AWS CodePipeline
- Triển khai monitoring và logging
- Thực hiện testing và sửa lỗi
- Hoàn thành tài liệu dự án

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1-2 | - Thiết lập CI/CD pipeline <br>&emsp; + Cấu hình AWS CodePipeline <br>&emsp; + Kết nối Git repository <br>&emsp; + Tự động hóa build và deploy <br> - Kiểm thử automated deployment | 2025/11/24 | 2025/11/25 | Tài liệu AWS CodePipeline |
| 3-4 | - Triển khai monitoring <br>&emsp; + CloudWatch logs cho backend <br>&emsp; + CloudWatch metrics <br>&emsp; + Thiết lập alarms <br> - Cấu hình API Gateway logging | 2025/11/26 | 2025/11/27 | Tài liệu AWS CloudWatch |
| 5-6 | - Testing toàn diện <br>&emsp; + Unit tests cho backend <br>&emsp; + Integration tests <br>&emsp; + Frontend E2E tests <br> - Sửa lỗi và tối ưu hóa | 2025/11/28 | 2025/11/29 | Testing best practices |
| 7 | - Hoàn thành tài liệu <br>&emsp; + README files <br>&emsp; + API documentation <br>&emsp; + Deployment guide <br> - Chuẩn bị trình bày dự án | 2025/11/30 | 2025/11/30 | Tiêu chuẩn tài liệu |

### Thành Tựu Tuần 12:

- **CI/CD Pipeline:**
  - Cấu hình AWS CodePipeline cho automated deployment
  - Kết nối pipeline với Git repository
  - Thiết lập build stage với CodeBuild
  - Tự động hóa backend deployment lên EC2
  - Tự động hóa frontend deployment lên S3 với CloudFront invalidation
  - Kiểm thử CI/CD flow hoàn chỉnh: Git push → Build → Deploy

- **Monitoring & Logging:**
  - Cấu hình CloudWatch Logs cho ứng dụng Spring Boot
  - Thiết lập CloudWatch metrics cho EC2 và RDS
  - Tạo CloudWatch alarms cho high CPU và memory usage
  - Bật API Gateway access logs
  - Triển khai application-level logging với log levels phù hợp

- **Testing & Quality:**
  - Viết unit tests cho backend services (JUnit)
  - Tạo integration tests cho API endpoints
  - Thực hiện manual E2E testing cho tất cả user flows
  - Sửa bugs phát hiện trong quá trình testing
  - Tối ưu database queries để cải thiện performance

- **Tài Liệu:**
  - Tạo README toàn diện với hướng dẫn setup
  - Tài liệu hóa tất cả API endpoints với ví dụ request/response
  - Viết deployment guide cho team members
  - Chuẩn bị slides trình bày dự án
  - Tài liệu hóa các quyết định kiến trúc và trade-offs

### Các Thách Thức Gặp Phải:

- **CodePipeline Configuration:** Build failures → Sửa Maven dependencies và build script
- **CloudWatch Logs:** Logs không xuất hiện → Cấu hình IAM role cho EC2 CloudWatch access
- **Performance Issues:** API responses chậm → Thêm database indexes và tối ưu queries

### Bài Học Chính:

- Thành thạo thiết lập AWS CI/CD pipeline
- Hiểu tầm quan trọng của monitoring và logging trong production
- Học các chiến lược testing cho ứng dụng full-stack
- Cải thiện kỹ năng tài liệu hóa và giao tiếp

### Tóm Tắt Dự Án:

Hoàn thành thành công Hệ Thống Hỗ Trợ Hiến Máu với:
- **Frontend:** React + Vite deployed trên S3/CloudFront
- **Backend:** Spring Boot deployed trên EC2
- **Database:** MySQL trên RDS
- **CI/CD:** Automated pipeline với CodePipeline
- **Monitoring:** CloudWatch logs và metrics
- **Security:** JWT authentication, HTTPS, Security Groups

### Tài Liệu Tham Khảo:

- [AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/)
- [CloudWatch Monitoring](https://docs.aws.amazon.com/cloudwatch/)
- [JUnit Testing](https://junit.org/junit5/)
- [API Documentation](https://swagger.io/)
