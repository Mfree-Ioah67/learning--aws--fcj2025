---
title: "Nhật Ký Tuần 11"
date: 2025-11-17
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục Tiêu Tuần 11:

- Phát triển frontend với React và Vite
- Triển khai các components giao diện người dùng
- Tích hợp frontend với backend APIs
- Deploy frontend lên S3 và CloudFront

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1-3 | - Thiết kế UI/UX mockups <br> - Tạo React components <br>&emsp; + Trang Login/Register <br>&emsp; + Dashboard <br>&emsp; + Form hiến máu <br>&emsp; + Tìm kiếm người hiến <br> - Triển khai routing với React Router | 2025/11/17 | 2025/11/19 | Tài liệu React, Material-UI |
| 4-5 | - Tích hợp với backend APIs <br>&emsp; + Axios cho HTTP requests <br>&emsp; + Quản lý JWT token <br>&emsp; + Xử lý lỗi API <br> - Kiểm thử user flows end-to-end | 2025/11/20 | 2025/11/21 | Tài liệu Axios |
| 6-7 | - Build production bundle <br> - Deploy lên S3 <br>&emsp; + Cấu hình S3 cho static hosting <br>&emsp; + Upload dist files <br> - Thiết lập CloudFront CDN <br> - Kiểm thử ứng dụng đã deploy | 2025/11/22 | 2025/11/23 | Tài liệu AWS S3, CloudFront |

### Thành Tựu Tuần 11:

- **Phát Triển Frontend:**
  - Thiết kế UI sạch và responsive với Material-UI
  - Tạo các React components có thể tái sử dụng
  - Triển khai trang xác thực (Login, Register)
  - Xây dựng dashboard với thống kê hiến máu
  - Phát triển form yêu cầu hiến máu
  - Tạo tìm kiếm người hiến với filters (nhóm máu, vị trí)
  - Triển khai React Router cho navigation

- **Tích Hợp API:**
  - Cấu hình Axios cho API calls
  - Triển khai lưu trữ JWT token trong localStorage
  - Tạo API service layer để tổ chức code sạch
  - Thêm loading states và xử lý lỗi
  - Kiểm thử user flows hoàn chỉnh: Đăng ký → Đăng nhập → Tạo Hiến máu → Tìm Người hiến

- **Deploy Frontend:**
  - Build production bundle tối ưu với Vite: `npm run build`
  - Cấu hình S3 bucket cho static website hosting
  - Upload dist files lên S3 sử dụng AWS CLI
  - Thiết lập CloudFront distribution cho CDN
  - Cấu hình custom domain (tùy chọn)
  - Xác minh ứng dụng hoạt động trên CloudFront URL

### Các Thách Thức Gặp Phải:

- **CORS Issues:** Backend chặn requests từ frontend → Cấu hình CORS trong Spring Boot
- **State Management:** State phức tạp qua các components → Sử dụng React Context API
- **CloudFront Caching:** Files cũ vẫn được serve → Tạo invalidation cho `/*`

### Bài Học Chính:

- Thành thạo React hooks (useState, useEffect, useContext)
- Hiểu các patterns tích hợp frontend-backend
- Học thiết lập S3 static hosting và CloudFront CDN

### Tài Liệu Tham Khảo:

- [React Documentation](https://react.dev/)
- [Vite Build Tool](https://vitejs.dev/)
- [AWS S3 Static Hosting](https://docs.aws.amazon.com/s3/static-website/)
- [CloudFront CDN](https://docs.aws.amazon.com/cloudfront/)
