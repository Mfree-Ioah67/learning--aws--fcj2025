---
title: "Nhật Ký Tuần 10"
date: 2025-11-10
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục Tiêu Tuần 10:

- Phát triển các API backend cốt lõi với Spring Boot
- Triển khai database models và repositories
- Thiết lập xác thực JWT
- Deploy backend lên EC2

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1-3 | - Thiết kế database schema (ERD) <br> - Tạo JPA entities và repositories <br> - Triển khai APIs xác thực người dùng <br>&emsp; + Đăng ký, Đăng nhập, Đăng xuất <br>&emsp; + Tạo JWT token | 2025/11/10 | 2025/11/12 | Tài liệu Spring Boot JPA |
| 4-5 | - Phát triển APIs hiến máu <br>&emsp; + Tạo yêu cầu hiến máu <br>&emsp; + Tìm kiếm người hiến theo nhóm máu <br>&emsp; + Cập nhật trạng thái hiến máu <br> - Kiểm thử APIs với Postman | 2025/11/13 | 2025/11/14 | REST API best practices |
| 6-7 | - Build file JAR với Maven <br> - Deploy backend lên EC2 <br>&emsp; + Upload JAR lên S3 <br>&emsp; + Cấu hình EC2 với Java <br>&emsp; + Chạy ứng dụng Spring Boot <br> - Kiểm thử APIs đã deploy | 2025/11/15 | 2025/11/16 | Tài liệu AWS EC2, S3 |

### Thành Tựu Tuần 10:

- **Phát Triển Backend:**
  - Thiết kế database schema với 5 bảng chính: Users, BloodDonations, Donors, Hospitals, DonationHistory
  - Tạo JPA entities với các mối quan hệ (OneToMany, ManyToOne)
  - Triển khai Spring Data JPA repositories
  - Xây dựng hệ thống xác thực với JWT tokens
  - Phát triển RESTful APIs cho quản lý người dùng và hiến máu

- **Triển Khai API:**
  - User APIs: Đăng ký, Đăng nhập, Lấy Profile, Cập nhật Profile
  - Donation APIs: Tạo Yêu cầu, Tìm Người hiến, Cập nhật Trạng thái, Lấy Lịch sử
  - Triển khai xử lý lỗi và validation đúng cách
  - Kiểm thử tất cả endpoints với Postman

- **Deploy Backend:**
  - Build file JAR sử dụng Maven: `mvn clean package`
  - Upload JAR lên S3 bucket để lưu trữ artifact
  - Cấu hình EC2 instance với Java 17
  - Deploy ứng dụng Spring Boot trên EC2
  - Cấu hình application.properties với kết nối RDS
  - Xác minh APIs hoạt động trên EC2

### Các Thách Thức Gặp Phải:

- **JPA Relationships:** Vấn đề circular dependency → Sử dụng `@JsonIgnore` và DTOs
- **JWT Implementation:** Xử lý token expiration → Triển khai cơ chế refresh token
- **EC2 Deployment:** Port 8080 không truy cập được → Cấu hình Security Group inbound rules

### Bài Học Chính:

- Thành thạo phát triển REST API với Spring Boot
- Hiểu về JPA entity relationships và lazy loading
- Học quy trình deploy ứng dụng Java lên EC2

### Tài Liệu Tham Khảo:

- [Spring Boot JPA](https://spring.io/guides/gs/accessing-data-jpa/)
- [JWT Authentication](https://jwt.io/introduction)
- [AWS EC2 Deployment](https://docs.aws.amazon.com/ec2/)
