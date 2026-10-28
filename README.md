# 🐾 OpenClaw Agent Studio & API Key Vault

<div align="center">

![OpenClaw Banner](https://img.shields.io/badge/OpenClaw-Autonomous_Agent-amber?style=for-the-badge&logo=bot&logoColor=black)
![Google Gemini AI](https://img.shields.io/badge/Google_Gemini-3.1_Flash-4285F4?style=for-the-badge&logo=google&logoColor=white)
![React 19](https://img.shields.io/badge/React_19-TypeScript-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_v4-Styling-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-emerald?style=for-the-badge)

<p align="center">
  <b>Nền tảng mô phỏng AI Agent tự trị (Local-First) thế hệ mới & Trạm quản lý khóa API chuẩn mật mã</b>
  <br />
  <i>Tích hợp trí tuệ Google Gemini AI · Cấu hình nhân cách qua Markdown · Trí nhớ dài hạn · 1-Click Copy</i>
</p>

[Trải Nghiệm Live Demo](#-hướng-dẫn-chạy-dự-án) • [Kiến Trúc Hoạt Động](#-kiến-trúc-hệ-thống) • [Tính Năng Nổi Bật](#-tính-năng-nổi-bật) • [Cấu Trúc Thư Mục](#-cấu-trúc-dự-án)

</div>

---

## 🌟 Giới Thiệu (Overview)

**OpenClaw Agent Studio** là một ứng dụng Full-Stack hiện đại mô phỏng trọn vẹn kiến trúc của framework **OpenClaw** (trước đây là *ClawdBot / MoltBot*) – giải pháp AI Agent tự trị chạy cục bộ (*Local-First / Self-Hosted*) đang dẫn đầu xu hướng thế giới.

Khác với các chatbot thụ động truyền thống, OpenClaw sở hữu **quyền hành động thực tế**: tự động gọi lệnh shell (`bash`), đọc/ghi file mã nguồn trong Workspace, lưu trữ ký ức vĩnh viễn vào `MEMORY.md` và kết nối liền mạch tới các nền tảng chat phổ biến như **Telegram, WhatsApp, Discord** và **Web Terminal**.

Đi kèm với đó là **API Key Studio** – hệ thống tạo và kiểm soát khóa bảo mật chuẩn doanh nghiệp (tương tự tiêu chuẩn của Stripe và GitHub), trang bị tính năng **1-Click Copy ("One Copy")** tức thời và bộ giả lập **API Sandbox** trực quan.

---

## 🚀 Tính Năng Nổi Bật (Key Features)

### 🤖 1. Vòng Lặp Agent Tự Trị (OpenClaw Autonomous Loop)
* **Vòng lặp 5 bước trực quan:** Theo dõi từng micro-step của Agent trong thời gian thực:
  $$\text{Kênh chat (Telegram/Web)} \longrightarrow \text{Tải bối cảnh Markdown} \longrightarrow \text{Suy luận Gemini} \longrightarrow \text{Thực thi Tool} \longrightarrow \text{Cập nhật Ký ức}$$
* **Hỗ trợ công cụ tự trị thực tế:**
  * `bash`: Thực thi câu lệnh shell trong môi trường sandbox cô lập.
  * `file_write` / `file_read`: Tự động viết script, phân tích file mã nguồn.
  * `memory_save`: Tự động trích xuất thông tin quan trọng của người dùng để lưu vào bộ nhớ dài hạn.
* **Mô phỏng đa kênh (Multi-Channel Switching):** Chuyển đổi linh hoạt giữa giao diện Web Terminal, Telegram Bot, WhatsApp và Discord.

### 📝 2. Triết Lý "Markdown-as-Config"
Toàn bộ hành vi của Agent được quản lý bằng các file văn bản Markdown thuần túy, có thể chỉnh sửa trực tiếp trên giao diện:
* `SOUL.md`: Định hình tính cách, tôn chỉ và nguyên tắc ứng xử của Agent.
* `MEMORY.md`: Ký ức dài hạn vĩnh viễn, không bị mất đi khi tắt máy hay bắt đầu phiên chat mới.
* `TOOLS.md`: Giới hạn quyền hạn và công cụ MCP được phép gọi.
* `openclaw.json`: Cấu hình mạng daemon Gateway trung gian (mặc định cổng `18789`).

### 🧠 3. Tiếp Sức Bởi Trí Tuệ Google Gemini AI
* Trực tiếp kết nối mô hình **`gemini-3.1-flash-lite`** & **`gemini-3.8-flash`** thông qua `@google/genai` TypeScript SDK.
* Tốc độ phản hồi cực nhanh (chỉ ~2-4 giây), định dạng Markdown sâu sắc, cấu trúc rõ ràng với ngôn ngữ Tiếng Việt tự nhiên.

### 🛡️ 4. Trạm Khóa Mật Mã & 1-Click Copy (API Key Studio)
* **1-Click Generation ("One Copy"):** Tạo khóa ngẫu nhiên đạt chuẩn CSPRNG (192-bit Entropy) và tự động sao chép vào Clipboard chỉ với một lần nhấp.
* **Bảo mật tuyệt đối:** Lưu trữ băm **SHA-256** (không bao giờ lưu Plaintext trong DB).
* **GitHub Secret Scanning:** Tích hợp mã kiểm tra toàn vẹn **CRC32 Checksum** ở đuôi key giúp các hệ thống quét rò rỉ mã nguồn nhận diện chính xác.
* **Xoay vòng không gián đoạn (Zero-Downtime Rotation):** Áp dụng thời gian ân hạn 24 giờ khi đổi khóa bí mật.
* **API Sandbox:** Console kiểm thử gửi request HTTP trực tiếp, đo thời gian trễ (latency ms) và mô phỏng phản hồi mã trạng thái `200 OK`, `401 Unauthorized`, `403 Forbidden`.

---

## 🏛️ Kiến Trúc Hệ Thống (System Architecture)

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CHANNELS & USER CLIENTS                         │
│       [Web Terminal]      [Telegram Bot]      [WhatsApp / Discord]     │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ WebSockets / HTTP
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   OPENCLAW GATEWAY DAEMON (Port 18789)                 │
│  - Session Management             - Message Ingestion & Routing        │
│  - Bearer Token Auth              - Lane Queues (Chống nghẽn lệnh)     │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
       ┌────────────────────────────┴────────────────────────────┐
       ▼                                                         ▼
┌───────────────────────────────┐         ┌──────────────────────────────┐
│  WORKSPACE CONTEXT ASSEMBLY   │         │    AUTONOMOUS TOOL SYSTEM    │
│  ├── SOUL.md   (Nhân cách)    │         │  ├── bash (Shell Execution)  │
│  ├── MEMORY.md (Ký ức dài hạn)│ ◄─────► │  ├── file_read / file_write  │
│  ├── TOOLS.md  (Danh mục tool)│         │  ├── memory_save             │
│  └── USER.md   (Hồ sơ cá nhân)│         │  └── web_search & MCP        │
└──────────────┬────────────────┘         └──────────────┬───────────────┘
               │                                         │
               └────────────────────┬────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                      GOOGLE GEMINI AI BRAIN                            │
│           Mô hình: gemini-3.1-flash-lite / gemini-3.8-flash            │
│           Nhiệm vụ: Suy luận chiến lược & Phản hồi thông minh          │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 💻 Hướng Dẫn Cài Đặt & Chạy Trên Máy Tính (Local Setup)

### Yêu cầu tiên quyết:
* Máy tính đã cài đặt **[Node.js](https://nodejs.org)** (Khuyên dùng bản 18 hoặc 20 LTS trở lên).
* Trình soạn thảo mã nguồn: **Visual Studio Code** (hoặc WebStorm/Cursor).

### Các bước khởi chạy:

**1. Tải mã nguồn về máy:**
* Bấm nút **"Tải về máy (.ZIP)"** trên giao diện web để tải file `openclaw-full-project.zip` và giải nén.
* Hoặc clone trực tiếp qua Git:
```bash
git clone https://github.com/clan41857/openclaw-agent-studio.git
cd openclaw-agent-studio
```

**2. Cài đặt các gói thư viện phụ thuộc:**
```bash
npm install
```

**3. Thiết lập biến môi trường:**
Tạo file `.env` tại thư mục gốc (hoặc sao chép từ `.env.example`):
```env
PORT=3000
# Khóa API Google Gemini (Lấy miễn phí tại https://aistudio.google.com/app/apikey)
GEMINI_API_KEY="AIzaSyYourGeminiApiKeyHere"
```

**4. Khởi động máy chủ ứng dụng:**
```bash
npm run dev
```

**5. Trải nghiệm:**
Mở trình duyệt web của bạn và truy cập:
```
http://localhost:3000
```

---

## 📂 Cấu Trúc Dự Án (Project Structure)

```text
├── server.ts                    # Backend Express + Endpoint gọi Gemini AI & sinh file ZIP
├── package.json                 # Cấu hình scripts & dependencies (React 19, Tailwind v4)
├── tsconfig.json                # Cấu hình TypeScript compiler
├── vite.config.ts               # Cấu hình Vite build tool
├── index.html                   # Entry point HTML giao diện
│
├── src/
│   ├── main.tsx                 # Khởi tạo React DOM root
│   ├── App.tsx                  # Component chính điều phối các tab và trạng thái
│   ├── index.css                # Cấu hình Tailwind CSS v4 styling
│   │
│   ├── components/              # Các UI Components chuyên biệt:
│   │   ├── OpenClawDemo.tsx     # Giao diện chính tương tác Agent & Markdown Workspace
│   │   ├── DownloadModal.tsx    # Modal tải mã nguồn ZIP & hướng dẫn đẩy lên GitHub
│   │   ├── Header.tsx           # Thanh điều hướng trên cùng & nút Quick Key
│   │   ├── QuickKeyBar.tsx      # Thanh sinh khóa 1-Click ("One Copy") tức thì
│   │   ├── KeysTable.tsx        # Bảng quản lý khóa, phân quyền, xoay vòng & thu hồi
│   │   ├── KeyStats.tsx         # Thống kê trực quan chỉ số sức khỏe & request
│   │   ├── CreateKeyModal.tsx   # Hộp thoại tạo khóa tùy biến entropy, scopes, expiry
│   │   ├── KeyRevealModal.tsx   # Hộp thoại bảo mật hiển thị key duy nhất 1 lần
│   │   ├── ApiSandbox.tsx       # Bàn thí nghiệm test Bearer Token & HTTP Status
│   │   ├── SecurityGuideModal.tsx # Cẩm nang phổ cập kiến thức mã nguồn mở
│   │   └── Toast.tsx            # Hệ thống thông báo trạng thái nổi (Floating toasts)
│   │
│   ├── data/
│   │   ├── openclawDefaults.ts  # Nội dung mặc định cho SOUL.md, MEMORY.md, TOOLS.md
│   │   └── mockKeys.ts          # Dữ liệu mẫu ban đầu & mock API endpoints
│   │
│   ├── types/
│   │   ├── apiKey.ts            # Định nghĩa kiểu dữ liệu khóa, scopes, quota
│   │   └── openclaw.ts          # Định nghĩa kiểu dữ liệu Agentic loop, channels, steps
│   │
│   └── utils/
│       └── crypto.ts            # Thuật toán sinh khóa CSPRNG, băm SHA-256, CRC32
```

---

## 🛠️ Công Nghệ Sử Dụng (Tech Stack)

| Thành phần | Công nghệ | Mục đích |
| :--- | :--- | :--- |
| **Frontend Framework** | **React 19** | Giao diện Single Page Application mượt mà, phản hồi tức thì |
| **Ngôn ngữ** | **TypeScript 5.x** | Kiểm soát kiểu chặt chẽ, an toàn 100% thời gian biên dịch |
| **Styling** | **Tailwind CSS v4** | Hệ thống thiết kế hiện đại dark-mode, chuẩn zero-pill discipline |
| **Backend Server** | **Express.js + tsx** | API proxy bảo vệ khóa bí mật, streaming dữ liệu & nén ZIP |
| **AI Engine** | **Google Gemini AI** | Mô hình `gemini-3.1-flash-lite` phân tích ngữ cảnh và quyết định công cụ |
| **Mật mã học** | **Web Crypto API** | Sinh entropy cao ngẫu nhiên (CSPRNG), băm SHA-256 và checksum CRC32 |
| **Đóng gói file** | **JSZip** | Nén mã nguồn tự động chuẩn DOS tương thích Windows/Mac/Linux |

---

## 🤝 Đóng Góp & Bản Quyền (License)

Dự án được phát hành dưới giấy phép mã nguồn mở **[MIT License](LICENSE)**. Bạn hoàn toàn có quyền tự do sử dụng, chỉnh sửa, tích hợp vào các dự án thương mại hoặc cá nhân.

<div align="center">
  <b>Được phát triển với niềm đam mê dành cho cộng đồng AI & Mã nguồn mở ❤️</b>
</div>
