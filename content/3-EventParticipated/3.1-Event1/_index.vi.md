---
title: "Event 1"
date: 2026-03-14
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

### Banner sự kiện

![Banner Event](/images/3-EventParticipated/3.1-Event1/Cloud_Mastery_2026.jpg)

## 1. Building AI Agent with Strands (Banh Cam Vinh)

### Mục tiêu sự kiện

- Giới thiệu khái niệm nền tảng về **LLM** và giới hạn của **LLM** khi hoạt động độc lập.
- Trình bày vì sao cần thiết kế **AI Agent** (**multi-step reasoning**, **tool integration**, **autonomous behaviour**).
- Giới thiệu **Strands Agents**: workflow, loại **tools**, chuẩn mở và cách **Strands** giảm "glue code".

### Diễn giả

- **Banh Cam Vinh** — "Building AI Agent with Strands"

![Bài phát biểu của Banh Cam Vinh](/images/3-EventParticipated/3.1-Event1/photo-1.jpg)

### Nội dung nổi bật

- Giới hạn của **standalone LLM**: chỉ trả lời chat, thiếu trạng thái dài hạn, không kết nối API/DB, khó xử lý quy trình nhiều bước.
- Kết nối **LLM** với thế giới thực qua **tools** (APIs, databases, external services) để biến **LLM** thành agent có khả năng hành động.
- Định nghĩa **AI Agent**: **LLM** làm "bộ não" cộng với **lập kế hoạch**, **gọi tools**, đọc kết quả và thực thi lặp đi lặp lại.
- **Strands Agents** cung cấp workflow chuẩn, bộ công cụ và chuẩn provider open-standard, giúp tăng tốc xây dựng **agentic loops**.

### Bài học rút ra

- Để **LLM** thực sự "làm việc", cần thiết kế **agent** chứ không chỉ tối ưu prompt.
- **Tool calling** và **agentic loop** là lõi: lập kế hoạch → chọn tool → gọi tool → đọc kết quả → lặp lại.
- **Strands** giảm đáng kể công sức viết "glue code" khi xây hệ thống **agent-based**.

### Ứng dụng

- Xây chatbot nội bộ (FAQ, IT support, CS): thiết kế **agents** có khả năng gọi APIs công ty (tickets, HR, CRM).
- Xử lý workflow nhiều bước (onboarding, đăng ký dịch vụ): dùng **agents** để orchestration các hành động tự động.
- Map APIs/services nội bộ thành tools để **agents** điều phối thay vì viết logic thủ công.

---

## 2. Automated Prompt Engineering: Enhancing LLM Output Quality (Nguyen Tuan Thinh)

### Mục tiêu sự kiện

- Giải thích tầm quan trọng của **prompt engineering**: generic prompts tạo ra generic outputs và chi phí token cao hơn.
- Hệ thống hóa các thành phần của prompt mạnh và giới thiệu kỹ thuật nâng cao (**CoT**, **RAG**, **ToT**, v.v.).
- Demo **Proptimizer** — một browser extension tối ưu prompts và tổng quan kiến trúc **AWS** của nó.

### Diễn giả

- **Nguyen Tuan Thinh** — DevOps Engineer, First Cloud AI Journey

![Bài phát biểu của Nguyen Tuan Thinh](/images/3-EventParticipated/3.1-Event1/photo-2.jpg)

### Nội dung nổi bật

- "Generic prompts → Generic outputs": prompt mạnh bao gồm **Role**, **Instruction**, **Context**, **Input Data**, **Output Format**, **Examples**, **Constraints**.
- Ví dụ cụ thể cho thấy prompts chính xác tạo ra outputs rõ ràng hơn, rẻ hơn.
- Kỹ thuật nâng cao: **Chain-of-Thought (CoT)**, **Self-Consistency**, **Tree-of-Thoughts (ToT)**, **Retrieval-Augmented Generation (RAG)**, **Role Prompting**.
- Demo **Proptimizer** và kiến trúc của nó dùng **CloudFront**, **S3**, **Cognito**, **API Gateway**, và **Lambda**.

### Bài học rút ra

- **Prompt engineering** là kỹ năng cốt lõi: coi prompts như specifications (role, task, context, format, examples, constraints).
- Tối ưu prompts giảm chi phí token và tăng độ ổn định và độ chính xác của kết quả.
- Kỹ thuật như **CoT/RAG/ToT** cải thiện reasoning vượt qua các câu trả lời single-shot.

### Ứng dụng

- Dùng standard prompt template cho các tác vụ (code, summary, analysis) để đảm bảo reliable outputs.
- Chuẩn hóa prompt templates và logging trong production để iteratively cải thiện performance.
- Xem xét **Proptimizer**-style tooling và **AWS** patterns nếu xây dựng prompt-optimization products.

---

## 3. AIoT Project: Locker Management (Aiden Dinh)

### Mục tiêu sự kiện

- Trình bày một dự án **AIoT** thực tế: hệ thống quản lý locker tự động sử dụng sensors, **RFID**, và **AI**.
- Chia sẻ kiến trúc hardware + cloud (**AWS**), data flow, costs, và working demo.

### Diễn giả

- **Aiden Dinh** — Katalon Operation Engineer, "AI-Powered Projects – AIoT Project: Locker Management"

![Bài phát biểu của Aiden Dinh](/images/3-EventParticipated/3.1-Event1/photo-3.jpg)

### Nội dung nổi bật

- Bài toán: tự động hóa quy trình mượn locker để giảm phụ thuộc manual manager.
- Kiến trúc: **Arduino** (edge) + **Raspberry Pi** (controller, **MQTT**) + sensors (reed switch, **RFID**) + camera.
- Cloud: **AWS IoT Core (MQTT)**, **S3** (images), **DynamoDB** (members/transactions), **Lambda** (**Rekognition**), **Amplify** (monitoring UI).
- Flow: **RFID**/sensor events kích hoạt photo capture → **Lambda** chạy **Rekognition** → match against collection → record transaction trong **DB**.

### Bài học rút ra

- Kết hợp sensing, connectivity, và **AI** giải quyết physical asset-management problems hiệu quả.
- **Rekognition** + **RFID** bật tính năng auditable borrow/return logs (ai, khi nào, cái gì).
- **AWS IoT Core** và serverless services cho phép scaling đến nhiều lockers và locations.

### Ứng dụng

- Áp dụng design này cho lab equipment inventory, smart cabinets, hoặc automated lending systems.
- Dùng project như IoT/Cloud case study cho coursework hoặc portfolio.

---

## Tổng kết

Sự kiện không chỉ cung cấp kiến thức kỹ thuật mà còn giúp em thay đổi cách tư duy về thiết kế ứng dụng, hiện đại hóa hệ thống và phối hợp hiệu quả hơn giữa các team.
