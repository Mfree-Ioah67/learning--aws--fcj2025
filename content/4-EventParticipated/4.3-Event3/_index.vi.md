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

![Lâm Tuấn Kiệt trình bày về Amazon SageMaker](z7226089182052_a87c70d3e5127727e468ec919746aa14.jpg)

![Lâm Tuấn Kiệt giới thiệu ML Services](z7226089182835_fd058a0d2646ba5ff862659b2a851ae3.jpg)

![Lâm Tuấn Kiệt demo SageMaker Studio](z7226089185538_6584042d4867f420dcdf26fbcd02f0d1.jpg)

![Lâm Tuấn Kiệt hướng dẫn MLOps](z7226089188785_2f1d4536d4d2edb5bd8521822269e0d7.jpg)

![Đinh Lê Hoàng Anh trình bày về Amazon Bedrock](z7226089195549_6134c1712f06d5fb6b0548a7a64e9750.jpg)

![Đinh Lê Hoàng Anh giới thiệu Foundation Models](z7226089198697_2575442063921150c411a74a9edc32fc.jpg)

![Đinh Lê Hoàng Anh demo Prompt Engineering](z7226089200374_4b9ccc01a946fe9ed479a97f20ad5505.jpg)

![Đinh Lê Hoàng Anh hướng dẫn RAG Architecture](z7226089200375_950fb4714f844f7be177194a7e37a3a7.jpg)

![Danh Hoàng Hiếu Nghị trình diễn Bedrock Agents](z7226089203525_3469cd3ec7d62c0017a5263da64eff32.jpg)

![Danh Hoàng Hiếu Nghị demo Guardrails](z7226089204044_8ce2e2975e24f9819d49e65be4db11c5.jpg)

![Danh Hoàng Hiếu Nghị xây dựng GenAI Chatbot](z7226089206129_2c222262ed586da5b52d7b6030a4c290.jpg)

![Danh Hoàng Hiếu Nghị hướng dẫn thực hành](z7226089216695_6b73693cec27aa10336add1ef9a03555.jpg)

![Tham gia và giao lưu](z7226089218316_67802975e0cb2fd27eca5753c983b534.jpg)

![Thảo luận nhóm](z7226089218462_0e1235918301fc52b7c887a7ea1096f0.jpg)

![Networking session](z7226089346755_df5c575289ae1e889d41530a7fa23152.jpg)

![Q&A với speakers](z7226089354417_4443e34ead3ca15caf40177f0f9f49fc.jpg)

![Thực hành hands-on](z7226089356840_d7bda4bcca7392f3f9556ae7e7caa637ef.jpg)

![Không khí workshop](z7226089356841_3c998c403886d96d8baf709f4dd4e5b6.jpg)

![Hình ảnh sự kiện](z7226089359526_87729a069d3be3043972c2c282e0becf.jpg)

![Hình ảnh sự kiện](z7226089360189_8d1b4512bf90f8903f0734fe096ecb90.jpg)

![Hình ảnh sự kiện](z7226089363728_27d9d0b068a8848a7a785090e98a754b.jpg)

![Hình ảnh sự kiện](z7226089363826_ba00915e1e271ea506cf280d71ae827d.jpg)

![Hình ảnh sự kiện](z7226089366343_1c4a98050cab1358bc27dab7a80a30f1.jpg)

![Hình ảnh sự kiện](z7226089372751_ee454114f82defa27d40fe7e7aa52754.jpg)

![Hình ảnh sự kiện](z7226089376197_63dd66304899769457969cade64e530e.jpg)

![Hình ảnh sự kiện](z7226089380342_06bc2cb44d6cb83846a4e7c1439da961.jpg)

![Hình ảnh sự kiện](z7226089383771_75be752db48944cbb444abe055a5371f.jpg)

![Hình ảnh sự kiện](z7226089385022_19d8d1f46dfd4a6d96f3df63cf28a66b.jpg)

![Hình ảnh sự kiện](z7226089387809_43295d0a2232a6f931293789e9b67e92.jpg)

![Hình ảnh sự kiện](z7226089394453_f5dfbd223cf4d77fb7d75a8219d136b3.jpg)

![Hình ảnh sự kiện](z7226089394608_8ddbe6d08a035fa4f121c1d0ebce372e.jpg)

![Hình ảnh sự kiện](z7226089400963_b53f90b1d0b891779316d6b8123d0637.jpg)

![Hình ảnh sự kiện](z7226089401010_47235c5b5898dbe77edd8d9294b8dac8.jpg)

![Hình ảnh sự kiện](z7226089406027_4e19736efe7e840ce9e3412d682d06a7.jpg)

![Hình ảnh sự kiện](z7226089411924_8f2a33fdef076d4a9ac07e59ae723840.jpg)

![Hình ảnh sự kiện](z7226089412672_0d8e8c7c237589eda3e2b20edffa4dd7.jpg)

> Nhìn chung, workshop này cung cấp giới thiệu toàn diện về dịch vụ AWS AI/ML, từ machine learning truyền thống với SageMaker đến Generative AI tiên tiến với Bedrock. Các trình diễn thực hành và hướng dẫn chuyên gia làm cho các khái niệm phức tạp trở nên dễ tiếp cận và có thể áp dụng ngay lập tức. Điểm chính rút ra là AWS cung cấp một hệ sinh thái hoàn chỉnh để xây dựng, triển khai và mở rộng ứng dụng AI/ML, giúp việc đưa đổi mới AI vào production dễ dàng hơn bao giờ hết.
