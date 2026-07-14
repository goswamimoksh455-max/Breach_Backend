<div align="center">
  <h1>✨ Nexora Backend ✨</h1>
  <p><strong>AI-Powered Expense Intelligence & Blockchain Audit Trail</strong></p>

  [![Node.js](https://img.shields.io/badge/Node.js-5.2-green.svg)](https://nodejs.org/)
  [![Express](https://img.shields.io/badge/Express-5.x-blue.svg)](https://expressjs.com/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue.svg)](https://www.typescriptlang.org/)
  [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue.svg)](https://www.postgresql.org/)
  [![Redis](https://img.shields.io/badge/Redis-7-red.svg)](https://redis.io/)
  [![License: ISC](https://img.shields.io/badge/License-ISC-yellow.svg)](https://opensource.org/licenses/ISC)
</div>

<br />

Nexora is an intelligent expense tracking platform designed to eliminate the burden of manual data entry through advanced AI. It transforms traditional expense tracking into a frictionless conversation using computer vision and natural language processing. 

This repository contains the robust Node.js/Express backend powering Nexora.

## 🚀 Core Features

- **🧠 AI Receipt Scanning**: Powered by **Gemini 2.5 Flash**, the system extracts merchant details, amounts, and line items from photos in under 2 seconds.
- **💬 NLP Quick Add**: Powered by **Llama 3.3 (Groq)**, users can add expenses via voice or text commands (e.g., *"I paid ₹1500 for pizza, split equally with Alice and Bob"*).
- **🧮 Smart Split Logic**: Intelligent mapping of names to UUIDs for equal, percentage, or custom bill splitting.
- **🔗 Blockchain Audit Layer**: Utilizes **Ethereum Sepolia** to anchor a tamper-proof audit trail for all financial records via asynchronous processing (`bullmq`).
- **🛡️ Enterprise Security**: Implements RBAC, input sanitization (`zod`), rate limiting (`express-rate-limit`), and memory-only file storage (using `multer` buffers—no files saved to disk).
- **💸 Stripe Integration**: Seamless payment processing and webhook handling.

## 🛠️ Technology Stack

- **Runtime & Framework**: Node.js, Express.js (v5)
- **Language**: TypeScript
- **Database**: PostgreSQL (`pg`), Redis (Caching, Rate Limiting, Queues via `ioredis`)
- **Queueing**: BullMQ
- **Authentication**: JWT (JSON Web Tokens), Google OAuth
- **AI Models**: Google Gemini 2.5 Flash (OCR), Llama 3.3 via Groq (NLP)
- **Validation**: Zod
- **Infrastructure Ready**: Docker support (`docker-compose.yml`), dynamic CORS setup, robust env validations.

## ⚙️ Prerequisites

- **Node.js** (v20+ recommended)
- **PostgreSQL** database instance
- **Redis** server instance
- **API Keys**: Groq API Key, Gemini API Key, Stripe Keys (optional for core features).

## 🚀 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Arman0604/Nexora.git
   cd Breach_Backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Environment Setup:**
   Copy the example environment file and fill in your keys.
   ```bash
   cp .env.example .env
   ```

4. **Run the Development Server:**
   ```bash
   npm run dev
   ```

## 🔐 Environment Variables

The application requires the following environment variables. See `.env.example` for details.

| Variable | Description |
| :--- | :--- |
| `NODE_ENV` | Environment (`development`, `production`) |
| `PORT` | API Port (default: 3000) |
| `DATABASE_URL` | PostgreSQL connection string |
| `REDIS_URL` | Redis connection string |
| `JWT_ACCESS_SECRET` | Secret for signing JWT access tokens |
| `JWT_REFRESH_SECRET` | Secret for signing JWT refresh tokens |
| `STRIPE_SECRET_KEY` | Stripe secret key |
| `STRIPE_PUBLISHABLE_KEY`| Stripe publishable key |
| `STRIPE_WEBHOOK_SECRET` | Stripe webhook signing secret |
| `GOOGLE_CLIENT_ID` | Google OAuth Client ID |
| `GROQ_API_KEY` | Groq API key for Llama 3.3 NLP |
| `GEMINI_API_KEY` | Google Gemini API key for OCR |

## 📜 Available Scripts

- `npm run dev`: Starts the server in development mode using `nodemon` and `tsx`.
- `npm run build`: Compiles TypeScript to JavaScript (`dist` folder).
- `npm run start`: Runs the compiled production code.
- `npm run typecheck`: Runs TypeScript type checking without emitting files.
- `npm run test:process:blockchain`: Runs the blockchain anchor queue script.

## ✅ Latest Stable State (July 2026)

This commit represents the fully working backend designed for deployment on Render, integrated with the Vercel frontend:
- **Authentication**: Complete JWT-based login and registration (tokens returned directly on signup for auto-login).
- **CORS Configuration**: Dynamic multi-origin support for production (`FRONTEND_URL`) and preview deployments (`*.vercel.app`).
- **Environment Variables**: Robust startup validation. Optional integrations (like Stripe) degrade gracefully if keys are missing to prevent deployment crashes.
- **Webhooks**: Lazy initialization for Stripe webhooks to ensure the server starts reliably.

## 🗺️ Roadmap (2026-2027)

- **Q2 2026**: Multi-language support (Hindi, Tamil, Telugu)
- **Q3 2026**: Banking API integrations for auto-importing transactions
- **Q4 2026**: WhatsApp Bot launch for chat-based tracking
- **2027**: Market expansion into Southeast Asia

---
<div align="center">
  <b>Links:</b> <a href="https://github.com/Arman0604/Nexora">GitHub</a> &bull; <a href="https://demo.nexora.app">Live Demo</a> &bull; <a href="mailto:team@nexora.app">Contact</a>
</div>
