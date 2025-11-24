---
title: "Worklog Tuần 1"
date: 2025-09-11
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The following information is for reference purposes only. Please do not copy verbatim for your own report, including this warning.
{{% /notice %}}

### Mục tiêu Tuần 1:

* Kết nối và làm quen với các thành viên của First Cloud Journey.
* Hiểu các dịch vụ cơ bản của AWS và sử dụng cả AWS Management Console và AWS CLI.
* Nắm vững khái niệm điện toán đám mây và hệ sinh thái AWS thông qua các video hướng dẫn.

### Công việc thực hiện trong tuần:

| Ngày | Công việc                                                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                               |
|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1    | - Làm quen với thành viên FCJ<br>- Đọc và ghi chú nội quy của đơn vị thực tập                                                                                                                                                     | 09/11/2025   | 09/11/2025      |                                                                                                                                                                  |
| 2    | - Tìm hiểu AWS và các loại dịch vụ<br>&emsp;+ Hiểu điện toán đám mây là cung cấp tài nguyên CNTT theo yêu cầu<br>&emsp;+ Khám phá lợi ích: tối ưu chi phí; tăng tốc độ phát triển; mở rộng toàn cầu<br>&emsp;+ Nhóm dịch vụ cơ bản: Compute, Storage, Networking, Database | 09/12/2025   | 09/12/2025      | https://cloudjourney.awsstudygroup.com/1-explore/   <hr> <a href="image1.png" target="_blank"><img src="/images/image1.png"> Sự Khác Biệt Của AWS</a>                                                                                                             |
| 3    | - Tạo tài khoản AWS Free Tier<br>- Học về AWS Console & AWS CLI<br>- Thực hành:<br>&emsp;+ Tạo tài khoản và bảo mật root user với MFA<br>&emsp;+ Cài đặt và cấu hình AWS CLI<br>&emsp;+ Sử dụng CLI và Console song song để thao tác cơ bản<br>&emsp;+ Thiết lập AWS Budgets để theo dõi chi phí | 09/13/2025   | 09/13/2025      | https://000001.awsstudygroup.com/ <hr> https://000007.awsstudygroup.com/ <hr> https://000011.awsstudygroup.com/   <hr>  https://000011.awsstudygroup.com/ <hr> <a href="image2.png" target="_blank"><img src="/images/image2.png"> Công Cụ Quản Lý AWS Services</a>                                               |
| 4    | - Tìm hiểu Hạ tầng Toàn cầu của AWS<br>&emsp;+ Khái niệm Data Centers, Availability Zones (AZs), Regions<br>&emsp;+ Khám phá cách mạng lưới toàn cầu và Edge Locations (PoPs) phục vụ CloudFront, WAF, Route 53<br>- Học EC2 cơ bản:<br>&emsp;+ Loại instance, AMI, EBS<br>&emsp;+ Kết nối SSH đến EC2<br>&emsp;+ Elastic IP | 09/14/2025   | 09/14/2025      | https://000006.awsstudygroup.com/ <hr> https://000004.awsstudygroup.com/5-amazonec2basic/ <hr> https://000011.awsstudygroup.com/4-infras/                       |
| 5    | - Thực hành:<br>&emsp;+ Khởi chạy EC2; kết nối SSH; gắn EBS<br>- Nghiên cứu bổ sung:<br>&emsp;+ Nghiên cứu AWS Well-Architected Framework (5 trụ cột)                                                                             | 09/15/2025   | 09/15/2025      | https://000011.awsstudygroup.com <hr> https://cloudjourney.awsstudygroup.com/                                                                                   |

### Thành tựu Tuần 1:

* Hiểu AWS là gì, các nhóm dịch vụ cơ bản và các lợi ích cốt lõi.
  * Điện toán đám mây là việc cung cấp tài nguyên CNTT theo yêu cầu qua Internet, với mô hình thanh toán theo mức sử dụng.
  * Các lợi thế chính: tăng/giảm tài nguyên linh hoạt, tăng tốc độ phát triển, triển khai toàn cầu nhanh chóng.
  * Thành thạo nhóm dịch vụ cơ bản: Compute, Storage, Networking, Database và hơn thế nữa.
* Đã tạo và cấu hình thành công tài khoản AWS Free Tier.
  * Tạo tài khoản thực hành và bảo mật root user bằng MFA.
  * Hiểu cách tạo và quản lý IAM user, nhóm để kiểm soát quyền truy cập.
* Làm quen với AWS Management Console và AWS CLI.
  * Sử dụng Console để khám phá dịch vụ, phân biệt root account và IAM user.
  * Cài đặt, cấu hình AWS CLI với access key và secret key.
* Sử dụng AWS CLI để thực hiện các thao tác cơ bản:
  * Kiểm tra thông tin tài khoản và cấu hình.
  * Lấy danh sách region.
  * Xem thông tin EC2.
  * Tạo và quản lý key pair.
  * Kiểm tra dịch vụ đang chạy.
* Kết hợp giao diện web và CLI để quản lý tài nguyên song song.
* Tìm hiểu chiến lược tối ưu chi phí và các gói hỗ trợ AWS.
  * Mô hình giá: On-Demand, Reserved Instances, Savings Plans, Spot Instances.
  * Gói hỗ trợ: Basic, Developer, Business, Enterprise.
* Thực hiện bài tập thực hành và nghiên cứu bổ sung.
  * Sử dụng AWS Budgets để tạo cảnh báo chi phí và sử dụng.
  * Bắt đầu tìm hiểu AWS Well-Architected Framework và cách áp dụng trong thực tế.

### Những khó khăn Tuần 1:

  * Đăng ký AWS Free Tier: khó xác thực thẻ ngân hàng hoặc bị từ chối thanh toán $1 để xác minh.  
  * Bảo mật tài khoản: khi cài MFA hoặc quản lý IAM users/groups dễ nhầm lẫn giữa root account và IAM account.  
  * AWS CLI: gặp lỗi cài đặt/cấu hình (sai đường dẫn, chưa set biến môi trường, nhập sai Access key/Secret key).  
  * Kết nối EC2: SSH không thành công do sai key pair, chưa mở port 22 trong Security Group, hoặc quên phân quyền file .pem.  
  * Quản lý chi phí: chưa quen dùng AWS Budgets, khó ước lượng tài nguyên tiêu tốn Free Tier.  
  * Thuật ngữ chuyên ngành (on-demand, scalability, elasticity, regions, availability zones) khá nhiều, dễ gây nhầm lẫn.  
  * Khối lượng kiến thức mới: nhiều dịch vụ AWS cần ghi nhớ (EC2, S3, RDS, VPC…), dễ bị quá tải.  
  * Phân biệt dịch vụ: khó hiểu sự khác nhau giữa các nhóm dịch vụ (Compute vs. Storage vs. Networking).  
  * Mô hình giá: On-Demand, Reserved, Spot, Savings Plans… phức tạp và khó chọn tình huống áp dụng.  
  * Hiểu Well-Architected Framework: trừu tượng, cần thời gian để hình dung 5 trụ cột vào thực tế.  