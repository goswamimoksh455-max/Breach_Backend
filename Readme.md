# Nexora: AI-Powered Expense Intelligence

Nexora is an intelligent expense tracking platform designed to eliminate the burden of manual data entry through advanced AI. It transforms traditional expense tracking into a frictionless conversation using computer vision and natural language processing.

## 🚀 Core Features
* **AI Receipt Scanning**: Powered by **Gemini 2.5 Flash**, the system extracts merchant details, amounts, and line items from photos in under 2 seconds.
* **NLP Quick Add**: Powered by **Llama 3.3 (Groq)**, users can add expenses via voice or text commands like *"I paid ₹1500 for pizza, split equally with Alice and Bob"*.
* **Smart Split Logic**: Intelligent mapping of names to UUIDs for equal, percentage, or custom bill splitting.
* **Blockchain Audit Layer**: Utilizes **Ethereum Sepolia** to anchor a tamper-proof audit trail for all financial records.

## 🛠️ Technology Stack
* **Frontend**: React / Vite with Tailwind CSS
* **Backend**: Node.js and Express.js with JWT authentication
* **Database**: PostgreSQL (Primary) and Redis (Rate limiting)
* **AI Models**: Gemini 2.5 Flash (OCR) and Llama 3.3 via Groq (NLP)
* **Blockchain**: Ethereum Sepolia

## 📈 System Architecture
1. **Capture**: Snap a photo or speak a command.
2. **Processing**: AI models extract and structure data into JSON format.
3. **Storage**: Data is stored in PostgreSQL, and an audit hash is anchored to the blockchain.
4. **Security**: Implements RBAC, input sanitization, and memory-only file storage (no files saved to disk).

## ✅ Latest Stable State (July 2026)
This commit represents the fully working backend designed for deployment on Render, integrated with the Vercel frontend:
- **Authentication**: Complete JWT-based login and registration (tokens returned directly on signup for auto-login).
- **CORS Configuration**: Dynamic multi-origin support for production (`FRONTEND_URL`) and preview deployments (`*.vercel.app`).
- **Environment Variables**: Robust startup validation. Optional integrations (like Stripe) degrade gracefully if keys are missing to prevent deployment crashes.
- **Webhooks**: Lazy initialization for Stripe webhooks to ensure the server starts reliably.

## 🗺️ Roadmap (2026-2027)
* **Q2 2026**: Multi-language support (Hindi, Tamil, Telugu)
* **Q3 2026**: Banking API integrations for auto-importing transactions
* **Q4 2026**: WhatsApp Bot launch for chat-based tracking
* **2027**: Market expansion into Southeast Asia

---
**Links:**
* **GitHub**: [github.com/nexora](https://github.com/nexora)
* **Live Demo**: [demo.nexora.app](https://demo.nexora.app)
* **Contact**: [team@nexora.app](mailto:team@nexora.app)
