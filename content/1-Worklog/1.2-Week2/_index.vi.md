---
title: "Worklog Tuần 2"
date: 2025-09-21
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

- Tìm hiểu sâu về AWS networking và kiến trúc VPC
- Thành thạo quản lý EC2 instance và cấu hình storage
- Hiểu các mô hình kết nối VPC: Peering và Transit Gateway

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                           | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                      |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------- |
| 1   | - Tìm hiểu tổng quan các dịch vụ AWS <br>&emsp; + Compute (EC2, Lambda) <br>&emsp; + Storage (S3, EBS) <br>&emsp; + Networking (VPC, Route53) <br> - Học VPC cơ bản: CIDR blocks, Subnets, Route Tables             | 15/09/2025   | 15/09/2025      | <https://000003.awsstudygroup.com/> |
| 2   | - **Thực hành:** <br>&emsp; + Tạo IAM Access Keys <br>&emsp; + Cài đặt và cấu hình AWS CLI <br>&emsp; + Test CLI với các lệnh cơ bản <br>&emsp; + Xác minh credentials và default region                            | 16/09/2025   | 16/09/2025      | <https://000003.awsstudygroup.com/> |
| 3   | - Tìm hiểu sâu về EC2: <br>&emsp; + Instance types và use cases <br>&emsp; + Lựa chọn AMI <br>&emsp; + Các loại EBS volume <br> - Học network security: Security Groups vs NACLs <br> - Cấu hình VPC Flow Logs      | 17/09/2025   | 17/09/2025      | <https://000019.awsstudygroup.com/> |
| 4   | - **Lab Session:** <br>&emsp; + Khởi tạo EC2 instance với cấu hình tùy chỉnh <br>&emsp; + Thiết lập SSH key pair và kết nối <br>&emsp; + Tạo và gắn EBS volume <br> - Tìm hiểu kiến trúc VPC Peering và các hạn chế | 18/09/2025   | 18/09/2025      | <https://000019.awsstudygroup.com/> |
| 5   | - Học kiến trúc AWS Transit Gateway <br> - So sánh các phương án kết nối: <br>&emsp; + VPC Peering (1-to-1) <br>&emsp; + Transit Gateway (hub-and-spoke) <br> - Cấu hình Transit Gateway với nhiều VPC attachments  | 19/09/2025   | 19/09/2025      | <https://000020.awsstudygroup.com/> |
| 6   | - Ôn tập kiến thức tuần <br> - Thực hành troubleshoot các vấn đề VPC thường gặp <br> - Ghi chép learnings và best practices                                                                                         | 20/09/2025   | 20/09/2025      |                                     |
| 7   | - Test lại toàn bộ cấu hình <br> - Hoàn thành báo cáo tuần <br> - Tự đánh giá và xác định knowledge gaps                                                                                                            | 21/09/2025   | 21/09/2025      |                                     |

### Kết quả đạt được tuần 2:

- Nắm vững kiến trúc VPC: CIDR planning, subnets, route tables, Internet Gateway, NAT Gateway
- Cấu hình AWS CLI và thực thi các lệnh: `aws configure`, `aws ec2 describe-instances`, `aws s3 ls`
- Khởi tạo EC2 instance, kết nối SSH, gắn EBS volume, gán Elastic IP
- Triển khai Security Groups và NACLs cho network security
- Bật VPC Flow Logs để giám sát traffic
- Cấu hình VPC Peering giữa hai VPCs với route table updates
- Deploy AWS Transit Gateway làm connectivity hub tập trung cho nhiều VPCs
- Hoàn thành các mục tiêu tuần và ghi chép toàn bộ cấu hình

### Các thử thách gặp phải:

- **CIDR Trùng lặp:** VPC Peering thất bại do CIDR blocks trùng nhau → Thiết kế lại với ranges không trùng
- **SSH Timeout:** Thiếu Security Group inbound rule cho port 22 → Thêm SSH rule cho IP cụ thể
- **Chi phí NAT Gateway:** Phát hiện tính phí theo giờ → Ghi chép so sánh chi phí để tham khảo
- **Route Sai:** Private subnet không thể ra internet → Thêm default route tới NAT Gateway
- **Transit Gateway Chậm:** Attachments ở trạng thái pending → Đợi 5-10 phút để propagation
- **Chi phí Flow Logs:** CloudWatch Logs tốn kém → Chuyển sang S3 destination để tối ưu chi phí

### Tài liệu tham khảo:

**Tài liệu chính thức AWS:**

- [Amazon VPC là gì?](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) - Hướng dẫn sử dụng VPC
- [Hướng dẫn Amazon EC2](https://docs.aws.amazon.com/ec2/index.html) - Tài liệu đầy đủ về EC2
- [AWS CLI Command Reference](https://docs.aws.amazon.com/cli/latest/reference/) - Tài liệu AWS CLI
- [Hướng dẫn VPC Peering](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html) - Kết nối VPC Peering
- [AWS Transit Gateway](https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html) - Tài liệu Transit Gateway

**AWS Workshops & Tutorials:**

- [AWS VPC Workshop](https://000003.awsstudygroup.com/) - Thực hành cấu hình VPC
- [EC2 Workshop](https://000019.awsstudygroup.com/) - Quản lý EC2 instance
- [Transit Gateway Workshop](https://000020.awsstudygroup.com/) - Thiết lập Transit Gateway

**Bài viết kỹ thuật:**

- [VPC Design Best Practices](https://aws.amazon.com/blogs/networking-and-content-delivery/vpc-sharing-a-new-approach-to-multiple-accounts-and-vpc-management/) - AWS Networking Blog
- [Security Groups vs NACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) - Hiểu về network security
- [VPC Flow Logs Analysis](https://aws.amazon.com/blogs/aws/vpc-flow-logs-log-and-view-network-traffic-flows/) - Hướng dẫn giám sát traffic
- [Tối ưu chi phí NAT Gateway](https://aws.amazon.com/blogs/architecture/reduce-nat-gateway-costs-by-using-vpc-endpoints/) - Chiến lược giảm chi phí
