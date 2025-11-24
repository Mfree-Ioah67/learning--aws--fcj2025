---
title: "Worklog Tuần 5"
date: 2025-10-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục Tiêu Tuần 5:

- Hiểu AWS Shared Responsibility Model và các best practices về bảo mật
- Nắm vững kiến thức cơ bản về IAM: Users, Groups, Roles và Policies
- Học các dịch vụ bảo mật AWS: KMS, Security Hub, CloudTrail
- Triển khai chiến lược tagging tài nguyên và kiểm soát truy cập
- Thực hành nguyên tắc least privilege với IAM policies

### Các nhiệm vụ cần thực hiện trong tuần này:

| Ngày | Nhiệm vụ                                                                                                                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                           |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------------- |
| 1    | - Nghiên cứu Shared Responsibility Model <br>&emsp; + Trách nhiệm của AWS vs Customer <br> - Học kiến thức cơ bản IAM: <br>&emsp; + Users, Groups, Roles, Policies <br>&emsp; + MFA và password policies                                             | 2025/10/06   | 2025/10/06      | <https://docs.aws.amazon.com/IAM/>                                           |
| 2    | - Tìm hiểu sâu về các dịch vụ bảo mật AWS: <br>&emsp; + Amazon Cognito cho xác thực người dùng <br>&emsp; + AWS Organizations cho quản lý multi-account <br>&emsp; + AWS Identity Center (SSO) <br>&emsp; + KMS cho quản lý encryption key           | 2025/10/07   | 2025/10/07      | <https://docs.aws.amazon.com/kms/>                                           |
| 3    | - **Lab 18:** Triển khai Security Hub <br>&emsp; + Bật Security Hub <br>&emsp; + Xem xét security scores <br> - **Lab 27:** Resource tagging <br>&emsp; + Tạo và quản lý tags <br>&emsp; + Lọc tài nguyên theo tags <br>&emsp; + Tạo Resource Groups | 2025/10/08   | 2025/10/08      | <https://000018.awsstudygroup.com/> <br> <https://000027.awsstudygroup.com/> |
| 4    | - **Lab 28:** IAM Policies và Roles <br>&emsp; + Tạo IAM users và policies <br>&emsp; + Cấu hình IAM roles <br>&emsp; + Switch roles và kiểm tra permissions <br>&emsp; + Triển khai tag-based access control                                        | 2025/10/09   | 2025/10/09      | <https://000028.awsstudygroup.com/>                                          |
| 5    | - **Lab 30:** Hạn chế IAM user <br>&emsp; + Tạo restriction policies <br>&emsp; + Kiểm tra limited user permissions <br> - **Lab 44:** IAM nâng cao <br>&emsp; + Tạo IAM groups và users <br>&emsp; + Cấu hình switch role với IP/time restrictions  | 2025/10/10   | 2025/10/10      | <https://000030.awsstudygroup.com/> <br> <https://000044.awsstudygroup.com/> |
| 6    | - **Lab 33:** KMS và CloudTrail <br>&emsp; + Tạo KMS keys <br>&emsp; + Mã hóa dữ liệu S3 <br>&emsp; + Bật CloudTrail logging <br>&emsp; + Query logs với Athena <br> - **Lab 48:** IAM roles vs Access keys                                          | 2025/10/11   | 2025/10/11      | <https://000033.awsstudygroup.com/> <br> <https://000048.awsstudygroup.com/> |
| 7    | - **Lab 22:** Tự động hóa với Lambda <br>&emsp; + Tạo Lambda functions cho EC2 start/stop <br>&emsp; + Cấu hình Slack notifications <br> - Ôn tập tuần và dọn dẹp                                                                                    | 2025/10/12   | 2025/10/12      | <https://000022.awsstudygroup.com/>                                          |

### Thành Tựu Tuần 5:

- **Thành Thạo IAM:**

  - Tạo và quản lý IAM users, groups và roles
  - Triển khai custom IAM policies với nguyên tắc least privilege
  - Cấu hình MFA cho bảo mật nâng cao
  - Hiểu logic đánh giá policy và permission boundaries

- **Dịch Vụ Bảo Mật:**

  - Bật AWS Security Hub cho giám sát bảo mật tập trung
  - Xem xét security scores và compliance standards
  - Cấu hình AWS Organizations cho quản trị multi-account
  - Triển khai AWS Identity Center cho SSO access

- **Mã Hóa & Quản Lý Key (Lab 33):**

  - Tạo và quản lý KMS customer-managed keys
  - Mã hóa S3 objects với KMS keys
  - Cấu hình key policies và grants
  - Bật CloudTrail cho API logging
  - Query CloudTrail logs sử dụng Amazon Athena

- **Resource Tagging (Lab 27):**

  - Triển khai chiến lược tagging cho tổ chức tài nguyên
  - Tạo tags sử dụng Console và CLI
  - Lọc tài nguyên theo tags
  - Tạo Resource Groups cho quản lý hàng loạt
  - Sử dụng tags cho phân bổ chi phí và kiểm soát truy cập

- **IAM Nâng Cao (Labs 28, 30, 44):**

  - Triển khai tag-based access control (ABAC)
  - Tạo IAM roles với assume role policies
  - Cấu hình switch role với IP và time restrictions
  - Kiểm tra permission boundaries và service control policies
  - Hạn chế user actions dựa trên resource tags

- **IAM Best Practices (Lab 48):**

  - So sánh IAM roles vs access keys
  - Triển khai IAM roles cho EC2 instances
  - Loại bỏ hardcoded credentials
  - Cấu hình temporary security credentials

- **Tự Động Hóa (Lab 22):**
  - Tạo Lambda functions cho quản lý vòng đời EC2
  - Cấu hình EventBridge rules cho scheduling
  - Tích hợp Slack webhooks cho notifications
  - Triển khai tag-based automation

### Thách Thức Gặp Phải:

- **Cú Pháp Policy:** Lỗi cú pháp JSON policy → Sử dụng IAM Policy Simulator để validate policies
- **Permission Denied:** User không thể truy cập tài nguyên → Thêm permissions thiếu và kiểm tra SCPs
- **KMS Key Policy:** Không thể sử dụng KMS key → Thêm IAM user/role vào key policy
- **CloudTrail Logs:** Logs không xuất hiện trong S3 → Đợi 15 phút cho log delivery
- **Switch Role Failed:** IP restriction chặn truy cập → Cập nhật condition để cho phép IP hiện tại
- **Tag Propagation:** Tags không áp dụng cho tài nguyên mới → Bật tag inheritance trong Organizations
- **Lambda Timeout:** Function timeout → Tăng timeout và tối ưu code

### Tài Liệu Tham Khảo:

**Tài Liệu Chính Thức AWS:**

- [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/) - Tài liệu IAM đầy đủ
- [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/) - Trách nhiệm bảo mật
- [AWS KMS](https://docs.aws.amazon.com/kms/) - Hướng dẫn Key Management Service
- [AWS Security Hub](https://docs.aws.amazon.com/securityhub/) - Giám sát bảo mật
- [AWS Organizations](https://docs.aws.amazon.com/organizations/) - Quản lý multi-account
- [AWS CloudTrail](https://docs.aws.amazon.com/cloudtrail/) - Dịch vụ API logging
- [Amazon Cognito](https://docs.aws.amazon.com/cognito/) - Xác thực người dùng

**AWS Workshops & Labs:**

- [Security Hub Workshop](https://000018.awsstudygroup.com/) - Lab 18: Giám sát bảo mật
- [Lambda Automation Workshop](https://000022.awsstudygroup.com/) - Lab 22: Tự động hóa EC2
- [Tagging Workshop](https://000027.awsstudygroup.com/) - Lab 27: Resource tagging
- [IAM Workshop](https://000028.awsstudygroup.com/) - Lab 28: IAM policies và roles
- [IAM Restrictions Workshop](https://000030.awsstudygroup.com/) - Lab 30: Hạn chế user
- [KMS Workshop](https://000033.awsstudygroup.com/) - Lab 33: Mã hóa và logging
- [Advanced IAM Workshop](https://000044.awsstudygroup.com/) - Lab 44: IAM nâng cao
- [IAM Roles Workshop](https://000048.awsstudygroup.com/) - Lab 48: Roles vs access keys

**Bài Viết Kỹ Thuật:**

- [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) - Khuyến nghị bảo mật
- [IAM Policy Evaluation Logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html) - Cách policies hoạt động
- [Tagging Best Practices](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html) - Chiến lược tagging
- [KMS Best Practices](https://docs.aws.amazon.com/kms/latest/developerguide/best-practices.html) - Hướng dẫn quản lý key
- [CloudTrail Best Practices](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/best-practices-security.html) - Khuyến nghị logging
