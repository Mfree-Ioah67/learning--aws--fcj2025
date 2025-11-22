# Internship Report - AWS FCJ 2025

[![Deploy Hugo site to GitHub Pages](https://github.com/Mfree-Ioah67/learning--aws--fcj2025/actions/workflows/hugo.yml/badge.svg)](https://github.com/Mfree-Ioah67/learning--aws--fcj2025/actions/workflows/hugo.yml)

Báo cáo thực tập AWS First Cloud Journey 2025 - Website được xây dựng bằng Hugo và deploy trên GitHub Pages.

🌐 **Live Site**: [https://mfree-ioah67.github.io/learning--aws--fcj2025/](https://mfree-ioah67.github.io/learning--aws--fcj2025/)

## 📋 Nội dung

- **1-Worklog**: Nhật ký công việc 12 tuần thực tập
- **2-Proposal**: Đề xuất dự án
- **3-BlogsTranslated**: Các bài blog AWS đã dịch
- **4-EventParticipated**: Sự kiện đã tham gia
- **5-Workshop**: Workshop thực hành AWS (S3, VPC, Endpoints)
- **6-Self-Evaluation**: Tự đánh giá
- **7-Feedback**: Phản hồi

## 🚀 Quick Start

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) v0.134.3 hoặc mới hơn
- Git

### Local Development

```bash
# Clone repository
git clone https://github.com/Mfree-Ioah67/learning--aws--fcj2025.git
cd learning--aws--fcj2025/fcj-workshop-template-main

# Run local server
hugo server -D

# Build static files
hugo --minify
```

Server sẽ chạy tại: `http://localhost:1313/learning--aws--fcj2025/`

## 📁 Project Structure

```
fcj-workshop-template-main/
├── .github/
│   └── workflows/
│       └── hugo.yml                    # GitHub Actions deployment workflow
│
├── archetypes/
│   └── default.md                      # Content template
│
├── content/                            # Markdown content (bilingual: en/vi)
│   ├── 1-Worklog/                      # 📅 Weekly internship logs (Week 1-12)
│   │   ├── 1.1-Week1/
│   │   ├── 1.2-Week2/
│   │   └── ... (1.3 - 1.12)
│   │
│   ├── 2-Proposal/                     # 📋 Project proposal
│   │
│   ├── 3-BlogsTranslated/              # 📝 Translated AWS blogs (6 blogs)
│   │   ├── 3.1-Blog1/
│   │   ├── 3.2-Blog2/
│   │   └── ... (3.3 - 3.6)
│   │
│   ├── 4-EventParticipated/            # 🎉 AWS events attended
│   │   ├── 4.1-Event1/
│   │   └── 4.2-Event2/
│   │
│   ├── 5-Workshop/                     # 🛠️ Hands-on AWS workshop
│   │   ├── 5.1-Workshop-overview/
│   │   ├── 5.2-Prerequiste/
│   │   ├── 5.3-S3-vpc/                 # Gateway Endpoint
│   │   │   ├── 5.3.1-create-gwe/
│   │   │   └── 5.3.2-test-gwe/
│   │   ├── 5.4-S3-onprem/              # Interface Endpoint
│   │   │   ├── 5.4.1-prepare/
│   │   │   ├── 5.4.2-create-interface-enpoint/
│   │   │   ├── 5.4.3-test-endpoint/
│   │   │   └── 5.4.4-dns-simulation/
│   │   ├── 5.5-Policy/
│   │   └── 5.6-Cleanup/
│   │
│   ├── 6-Self-evaluation/              # 📊 Self assessment
│   └── 7-Feedback/                     # 💬 Feedback & reflection
│
├── layouts/
│   ├── partials/                       # Custom HTML partials
│   │   ├── custom-footer.html
│   │   ├── logo.html
│   │   └── menu-footer.html
│   └── shortcodes/                     # Custom Hugo shortcodes
│       ├── ghcontributors.html
│       ├── tab.html
│       └── tabs.html
│
├── static/                             # Static assets (images, fonts, CSS)
│   ├── css/
│   │   ├── theme-mine.css
│   │   └── theme-workshop.css
│   ├── fonts/
│   ├── images/
│   │   ├── 2-Proposal/                 # Architecture diagrams
│   │   ├── 5-Workshop/                 # Workshop screenshots
│   │   ├── avatar.png
│   │   └── favicon.png
│   └── AWS_Logo.svg
│
├── themes/
│   └── hugo-theme-learn/               # Hugo Learn theme
│
├── public/                             # 🚀 Generated static site (auto-built)
│
├── config.toml                         # Hugo configuration
└── README.md                           # This file
```

### 📊 Content Statistics

- **Weekly Logs**: 12 weeks of detailed work reports
- **Translated Blogs**: 6 AWS technical articles
- **Events**: 2 AWS community events documented
- **Workshop**: Complete hands-on lab with S3 VPC Endpoints
- **Languages**: Full bilingual support (English & Vietnamese)

## 🛠️ Tech Stack

- **Static Site Generator**: Hugo v0.134.3 (Extended)
- **Theme**: [Hugo Learn Theme](https://github.com/matcornic/hugo-theme-learn)
- **Deployment**: GitHub Pages via GitHub Actions
- **Languages**: Vietnamese & English

## 🚢 Deployment

Website tự động deploy khi push lên branch `main`:

1. GitHub Actions chạy workflow
2. Build Hugo site với `hugo --minify`
3. Deploy lên GitHub Pages

Xem deployment status tại [Actions tab](https://github.com/Mfree-Ioah67/learning--aws--fcj2025/actions)

## 🔧 Configuration

Chỉnh sửa `config.toml` để thay đổi:

- Base URL
- Site title
- Theme variant
- Menu shortcuts
- Language settings

## 📚 Workshop Content

Workshop chính: **Access S3 from VPC and On-premises**

- Create Gateway Endpoint
- Create Interface Endpoint
- DNS Simulation
- Policy Configuration

## 👤 Author

**Email**: phamhoanghainguyen12a12dt@gmail.com

## 🔗 Links

- [AWS Study Group Facebook](https://www.facebook.com/groups/awsstudygroupfcj/)
- [Hugo Documentation](https://gohugo.io/documentation/)
- [Hugo Learn Theme Docs](https://learn.netlify.app/en/)

## 📄 License

This project is for educational purposes as part of AWS FCJ 2025 internship program.
