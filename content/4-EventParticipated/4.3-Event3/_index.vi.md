---
title: "Workshop AI/ML/GenAI trên AWS"
date: 2025-11-15
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Thông tin dưới đây chỉ mang tính chất tham khảo. Vui lòng **không sao chép nguyên văn** vào báo cáo của bạn, bao gồm cả cảnh báo này.
{{% /notice %}}

# Báo Cáo Tóm Tắt: "Workshop AI/ML/GenAI trên AWS"

### Mục Tiêu Sự Kiện

- Hiểu về bối cảnh AI/ML và hệ sinh thái dịch vụ AWS tại Việt Nam
- Học machine learning end-to-end với Amazon SageMaker
- Khám phá khả năng Generative AI với Amazon Bedrock
- Nắm vững kỹ thuật prompt engineering và RAG (Retrieval-Augmented Generation)
- Xây dựng giải pháp AI/ML thực tế sử dụng dịch vụ AWS

### Thông Tin Sự Kiện

- **Địa điểm**: Văn phòng AWS Vietnam
- **Ngày & Giờ**: 8:30 sáng – 12:00 trưa, Thứ Bảy, ngày 15 tháng 11 năm 2025

### Diễn Giả & Điều Phối Viên

**Giảng viên:**

- **Lâm Tuấn Kiệt** – Senior DevOps Engineer, FPT Software – Tổng quan Amazon SageMaker và ML Services
- **Đinh Lê Hoàng Anh** – Cloud Engineer Trainee, FCAJ Đại học Kỹ thuật Swinburne – Amazon Bedrock và các dịch vụ AWS AI/ML 
- **Danh Hoàng Hiếu Nghị** – Fresher AI Engineer, Renova Cloud – Amazon Bedrock Agent Core, trình diễn trực tiếp và hướng dẫn thực hành

**Điều phối viên:**

- **AWS Vietnam Community Team**
- **FCJ Program Leaders**

### Chương Trình Sự Kiện

#### 8:30 – 9:00 sáng: Chào Mừng & Giới Thiệu

- Đăng ký tham gia và giao lưu
- Tổng quan workshop và mục tiêu học tập
- Hoạt động phá băng
- Tổng quan về bối cảnh AI/ML tại Việt Nam

#### 9:00 – 10:30 sáng: Tổng Quan Dịch Vụ AWS AI/ML

**Amazon SageMaker – Nền Tảng ML End-to-end**

- **Chuẩn Bị và Gán Nhãn Dữ Liệu**:
  - SageMaker Data Wrangler cho tiền xử lý dữ liệu
  - Ground Truth cho gán nhãn và chú thích dữ liệu
  - Feature Store cho quản lý và tái sử dụng features
- **Huấn Luyện, Tinh Chỉnh và Triển Khai Model**:
  - Thuật toán tích hợp sẵn và custom training scripts
  - Hyperparameter tuning với tối ưu hóa model tự động
  - Các tùy chọn triển khai model: real-time, batch, và serverless inference
  - A/B testing và multi-model endpoints
- **Khả Năng MLOps Tích Hợp**:

  - SageMaker Pipelines cho tự động hóa ML workflow
  - Model Registry cho version control và governance
  - Model Monitor cho phát hiện data drift và chất lượng model
  - Tích hợp với CI/CD tools cho continuous deployment

- **Trình Diễn Trực Tiếp**: Hướng dẫn SageMaker Studio
  - Tạo notebook instance
  - Huấn luyện machine learning model
  - Triển khai và kiểm tra model endpoint

#### 10:30 – 10:45 sáng: Giải Lao

- Giao lưu và giải khát
- Hỏi đáp với chuyên gia AWS

#### 10:45 sáng – 12:00 trưa: Generative AI với Amazon Bedrock và AWS AI/ML Services

**Tổng Quan AWS AI/ML Services**

- **Amazon Rekognition**: Computer vision cho phân tích hình ảnh và video
- **Amazon Translate**: Dịch văn bản tự động với neural machine translation
- **Amazon Textract**: Trích xuất text và data từ documents
- **Amazon Transcribe**: Chuyển đổi speech-to-text tự động
- **Amazon Polly**: Text-to-speech với giọng nói tự nhiên
- **Amazon Comprehend**: Natural language processing và text analytics
- **Amazon Kendra**: Intelligent search service với ML
- **Amazon Lookout**: Anomaly detection cho operational data
- **Amazon Personalize**: Recommendation engine với ML

**Foundation Models: Claude, Llama, Titan**

- **So Sánh Model & Hướng Dẫn Lựa Chọn**:
  - Claude (Anthropic): Tốt nhất cho conversational AI và lý luận phức tạp
  - Llama (Meta): Linh hoạt open-source và tùy chỉnh
  - Titan (Amazon): Hiệu quả chi phí và tích hợp AWS-native
  - Chọn model phù hợp cho use case của bạn

**Kỹ Thuật Prompt Engineering**

- **Chiến Lược Prompting Hiệu Quả**:
  - Hướng dẫn rõ ràng và thiết lập ngữ cảnh
  - Few-shot learning với ví dụ
  - Chain-of-Thought (CoT) reasoning cho tác vụ phức tạp
  - Role-based prompting và định nghĩa persona
- **Kỹ Thuật Nâng Cao**:
  - Kiểm soát temperature và token
  - System prompts vs user prompts
  - Prompt templates và khả năng tái sử dụng

**Retrieval-Augmented Generation (RAG)**

- **Kiến Trúc RAG**:
  - Vector databases và embeddings
  - Semantic search và document retrieval
  - Context injection vào prompts
- **Tích Hợp Knowledge Base**:
  - Amazon Bedrock Knowledge Bases
  - **Amazon S3** để lưu trữ documents và dữ liệu knowledge base
  - Kết nối với data sources (S3 buckets, databases, APIs)
  - Chiến lược chunking và quản lý metadata
  - S3 bucket policies và access control cho lưu trữ dữ liệu an toàn

**Amazon Bedrock Agent Core**

- **Agent Orchestration**:
  - Bedrock Agent Core cho xây dựng AI agents tự động
  - Multi-step reasoning và task planning
  - Action groups và API integrations
  - Memory và conversation state management
- **Tool Integration**:
  - Lambda functions cho custom logic
  - External API connections
  - Database queries và data retrieval

**Guardrails: An Toàn và Lọc Nội Dung**

- Content moderation và phát hiện toxicity
- Lọc PII (Personally Identifiable Information)
- Lọc theo chủ đề và denied topics
- Custom guardrails cho yêu cầu doanh nghiệp

**Trình Diễn Trực Tiếp: Xây Dựng Chatbot Generative AI sử dụng Bedrock**

- Thiết lập quyền truy cập Bedrock foundation model
- Tạo chatbot đơn giản với prompt engineering
- Triển khai RAG với Knowledge Bases
- Thêm guardrails cho phản hồi an toàn
- Kiểm tra và cải tiến chatbot

### Điểm Chính Rút Ra

#### Khả Năng Amazon SageMaker

- **Nền Tảng ML End-to-End**: SageMaker cung cấp tất cả công cụ cần thiết từ chuẩn bị dữ liệu đến triển khai model
- **Tích Hợp MLOps**: Khả năng tích hợp sẵn cho tự động hóa và giám sát ML workflows
- **Khả Năng Mở Rộng**: Dễ dàng scale từ thử nghiệm đến production workloads
- **Tối Ưu Chi Phí**: Giá pay-as-you-go với tùy chọn spot instances và serverless inference

#### Generative AI với Bedrock

- **Đa Dạng Model**: Truy cập nhiều foundation models mà không cần quản lý infrastructure
- **Prompt Engineering**: Kỹ năng quan trọng để có outputs chất lượng từ LLMs
- **Kiến Trúc RAG**: Kết hợp sức mạnh của LLMs với dữ liệu độc quyền của bạn
- **An Toàn Trước Tiên**: Guardrails đảm bảo triển khai AI có trách nhiệm
- **Khả Năng Agent**: Cho phép AI workflows phức tạp, nhiều bước

#### Triển Khai Thực Tế

- **Bắt Đầu với Use Cases**: Xác định vấn đề kinh doanh cụ thể mà AI/ML có thể giải quyết
- **Thử Nghiệm và Cải Tiến**: Sử dụng SageMaker Studio cho rapid prototyping
- **Tận Dụng Pre-built Models**: Bắt đầu với foundation models trước khi custom training
- **Triển Khai Guardrails**: Luôn ưu tiên an toàn và tuân thủ
- **Giám Sát và Tối Ưu**: Liên tục theo dõi hiệu suất model và chi phí

### Áp Dụng Vào Công Việc

- **Khám Phá SageMaker**: Bắt đầu với SageMaker Studio free tier để thử nghiệm ML workflows
- **Xây Dựng RAG Applications**: Triển khai knowledge base integration cho domain-specific chatbots
- **Thực Hành Prompt Engineering**: Phát triển chiến lược prompting hiệu quả cho use cases của bạn
- **Triển Khai MLOps**: Tự động hóa ML pipelines sử dụng SageMaker Pipelines
- **Deploy Bedrock Agents**: Tạo intelligent agents cho tự động hóa quy trình kinh doanh
- **Đảm Bảo Tuân Thủ**: Sử dụng Bedrock Guardrails để đáp ứng yêu cầu quy định
- **Chia Sẻ Kiến Thức**: Ghi chép learnings và best practices với nhóm của bạn

### Trải Nghiệm Sự Kiện

Tham dự **"Workshop AI/ML/GenAI trên AWS"** tại văn phòng AWS Vietnam là một trải nghiệm học tập đắm chìm, cung cấp tiếp xúc thực hành với công nghệ AI/ML tiên tiến. Các trải nghiệm chính bao gồm:

#### Học Hỏi Từ Chuyên Gia AWS

- **AWS Solutions Architects** cung cấp insights toàn diện về khả năng ML end-to-end của SageMaker
- **AWS GenAI Specialists** trình diễn ứng dụng thực tế của Amazon Bedrock và foundation models
- Các use cases thực tế minh họa cách các công ty Việt Nam đang tận dụng dịch vụ AWS AI/ML
- Hướng dẫn chuyên gia về việc chọn công cụ và models phù hợp cho nhu cầu kinh doanh cụ thể

#### Trình Diễn Thực Hành

- Chứng kiến **SageMaker Studio** hoạt động, từ chuẩn bị dữ liệu đến triển khai model
- Thấy cách **Amazon Bedrock** cho phép phát triển nhanh ứng dụng GenAI mà không cần quản lý infrastructure
- Học các kỹ thuật **prompt engineering** thực tế giúp cải thiện ngay outputs của LLM
- Khám phá **kiến trúc RAG** để xây dựng ứng dụng AI có nhận thức về kiến thức
- Hiểu cách **Bedrock Agents** điều phối workflows phức tạp nhiều bước

#### Hiểu Biết Về Bối Cảnh AI/ML

- Có insights về **xu hướng áp dụng AI/ML** tại Việt Nam
- Học về **sự khác biệt giữa traditional ML và Generative AI** approaches
- Hiểu khi nào sử dụng **SageMaker vs Bedrock** cho các use cases khác nhau
- Khám phá tầm quan trọng của **MLOps** cho hệ thống ML production

#### Giao Lưu và Xây Dựng Cộng Đồng

- Kết nối với các developers và data scientists đang khám phá dịch vụ AWS AI/ML
- Trao đổi ý tưởng về thách thức và giải pháp triển khai AI/ML thực tế
- Xây dựng mối quan hệ với chuyên gia AWS để được hỗ trợ và hướng dẫn liên tục
- Tham gia cộng đồng AWS AI/ML để học tập liên tục

#### Hiểu Biết Thực Tế Thu Được

- **Foundation models** dân chủ hóa quyền truy cập vào khả năng AI mạnh mẽ mà không cần tài nguyên khổng lồ
- **Prompt engineering** là kỹ năng quan trọng ảnh hưởng đáng kể đến chất lượng ứng dụng GenAI
- **Kiến trúc RAG** giải quyết vấn đề LLMs thiếu kiến thức domain-specific
- **Guardrails** là thiết yếu cho triển khai AI có trách nhiệm và tuân thủ
- **SageMaker** cung cấp nền tảng hoàn chỉnh tăng tốc phát triển và triển khai ML

#### Các Bước Tiếp Theo

- Bắt đầu thử nghiệm với **SageMaker Studio** sử dụng free tier
- Xây dựng proof-of-concept **RAG application** sử dụng Bedrock Knowledge Bases
- Thực hành kỹ thuật **prompt engineering** trên các foundation models khác nhau
- Khám phá **Bedrock Agents** để tự động hóa business workflows
- Triển khai **MLOps practices** sử dụng SageMaker Pipelines
- Tiếp tục tham gia với **cộng đồng AWS AI/ML** để học tập liên tục

#### Một Số Hình Ảnh Sự Kiện

![Workshop AI/ML](images/1.jpg)

---

![Workshop AI/ML](images/2.jpg)

---

![Workshop AI/ML](images/3.jpg)

---

![Workshop AI/ML](images/4.jpg)

---

![Workshop AI/ML](images/5.jpg)

---

![Workshop AI/ML](images/6.jpg)

---

![Workshop AI/ML](images/7.jpg)

---

![Workshop AI/ML](images/8.jpg)

---

![Workshop AI/ML](images/9.jpg)

---

![Workshop AI/ML](images/10.jpg)

---

![Workshop AI/ML](images/11.jpg)

---

![Workshop AI/ML](images/12.jpg)

---

![Workshop AI/ML](images/13.jpg)

---

![Workshop AI/ML](images/14.jpg)

---

![Workshop AI/ML](images/15.jpg)

---

![Workshop AI/ML](images/16.jpg)

---

![Workshop AI/ML](images/17.jpg)

---

![Workshop AI/ML](images/18.jpg)

---

![Workshop AI/ML](images/19.jpg)

---

![Workshop AI/ML](images/20.jpg)

---

![Workshop AI/ML](images/21.jpg)

---

![Workshop AI/ML](images/22.jpg)

---

![Workshop AI/ML](images/23.jpg)

---

![Workshop AI/ML](images/24.jpg)

---

![Workshop AI/ML](images/25.jpg)

---

![Workshop AI/ML](images/26.jpg)

---

![Workshop AI/ML](images/27.jpg)

---

![Workshop AI/ML](images/28.jpg)

---

![Workshop AI/ML](images/29.jpg)

---

![Workshop AI/ML](images/30.jpg)

---

![Workshop AI/ML](images/31.jpg)

---

![Workshop AI/ML](images/32.jpg)

---

![Workshop AI/ML](images/33.jpg)

---

![Workshop AI/ML](images/34.jpg)

---

![Workshop AI/ML](images/35.jpg)

---

![Workshop AI/ML](images/36.jpg)

> Nhìn chung, workshop này cung cấp giới thiệu toàn diện về dịch vụ AWS AI/ML, từ machine learning truyền thống với SageMaker đến Generative AI tiên tiến với Bedrock. Các trình diễn thực hành và hướng dẫn chuyên gia làm cho các khái niệm phức tạp trở nên dễ tiếp cận và có thể áp dụng ngay lập tức. Điểm chính rút ra là AWS cung cấp một hệ sinh thái hoàn chỉnh để xây dựng, triển khai và mở rộng ứng dụng AI/ML, giúp việc đưa đổi mới AI vào production dễ dàng hơn bao giờ hết.
