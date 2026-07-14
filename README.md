<div align="center">
  <h1>Nexora API ⚡</h1>
  <p><strong>The Intelligent Engine for Expense Tracking & Blockchain Auditing</strong></p>

  [![Node.js](https://img.shields.io/badge/Node.js-20.x-green.svg)](https://nodejs.org/)
  [![Express](https://img.shields.io/badge/Express-5.x-blue.svg)](https://expressjs.com/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue.svg)](https://www.typescriptlang.org/)
  [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue.svg)](https://www.postgresql.org/)
  [![Redis](https://img.shields.io/badge/Redis-7-red.svg)](https://redis.io/)
</div>

<br />

Welcome to the backend repository for **Nexora**! This API powers the entire Nexora ecosystem, handling everything from AI-driven receipt OCR and natural language processing to secure authentication and blockchain-anchored audit trails. 

Designed for performance and reliability, it is built with **Node.js**, **Express**, and **TypeScript**, backed by **PostgreSQL** and **Redis**.

---

## 🌟 Key Capabilities

* **AI-Powered OCR (`Gemini 2.5 Flash`)**: Extracts structured merchant and item data directly from receipt images in milliseconds.
* **Natural Language Expenses (`Llama 3.3 via Groq`)**: Processes complex voice and text commands (e.g., *"I spent ₹500 on coffee and split it with Alice"*).
* **Blockchain Anchoring (`Ethereum Sepolia`)**: Asynchronously anchors financial data to the blockchain via **BullMQ** for an immutable audit trail.
* **Intelligent Splitting**: Automatically resolves names to user UUIDs and handles equal, exact, or percentage-based bill splits.
* **Robust Security**: Features strict rate-limiting (`express-rate-limit`), request validation (`zod`), JWT and Google OAuth authentication, and memory-only file processing.

---

## 🏗️ Architecture Stack

| Component | Technology | Description |
| :--- | :--- | :--- |
| **Framework** | Express 5.x & Node.js | Core server runtime and routing. |
| **Language** | TypeScript | Ensures type safety and developer productivity. |
| **Primary DB** | PostgreSQL (`pg`) | Relational storage for users, expenses, and splits. |
| **Cache & Queue** | Redis & BullMQ | Manages rate limits and async background jobs (blockchain anchoring). |
| **AI Models** | Gemini & Groq (Llama) | Core intelligence for OCR and NLP parsing. |
| **Payments** | Stripe | Webhook integration for payment event processing. |

---

## 🚦 Getting Started (Local Development)

### 1. Prerequisites
Make sure you have the following installed on your machine:
* **Node.js** (v20 or higher)
* **PostgreSQL** (Running locally or via a cloud provider)
* **Redis** (Running locally or via Docker)

### 2. Installation
Clone the repository and install the required dependencies:
```bash
git clone https://github.com/Arman0604/Nexora.git
cd Breach_Backend
npm install
```

### 3. Environment Configuration
Create a `.env` file in the root directory and configure it based on `.env.example`:
```bash
cp .env.example .env
```
*Ensure you populate your `DATABASE_URL`, `REDIS_URL`, `JWT_ACCESS_SECRET`, and the necessary AI API keys (`GEMINI_API_KEY`, `GROQ_API_KEY`).*

### 4. Running the Server
Start the development server with hot-reloading:
```bash
npm run dev
```
Start the background blockchain worker queue:
```bash
npm run test:process:blockchain
```

---

## 🛠️ Core Scripts

* `npm run dev`: Starts the application in development mode using `nodemon` and `tsx`.
* `npm run build`: Compiles the TypeScript source code into the `dist` directory.
* `npm run start`: Runs the compiled production build from `dist/index.js`.
* `npm run typecheck`: Validates TypeScript typings without emitting build files.
* `npm run test:process:blockchain`: Starts the dedicated worker script for blockchain anchoring.

---

## 🚀 Deployment Status

The application is fully production-ready and configured for zero-downtime deployment (e.g., Render, Railway, or AWS). 
* **Dynamic CORS**: Configured to securely support multi-origin environments (`FRONTEND_URL` and `*.vercel.app` previews).
* **Graceful Degradation**: Optional external services (like Stripe) fail gracefully during startup if environment variables are missing, preventing hard crashes.
