# 🛒 ClariCart

### AI-Powered Product Intelligence Platform

> ClariCart is an LLM-powered product analysis platform that helps users make smarter purchasing decisions through **live web intelligence**, **review analysis**, **RAG pipelines**, and **AI-generated insights** — all within seconds.

**Built with:** LangChain · LangGraph · FastAPI · Next.js 16 · ChromaDB · Gemini 2.0 Flash · Apify · Playwright

<p align="center">
  <img src="screenshots/banner.png" width="900" alt="ClariCart Banner"/>
</p>

---

## 🎯 Problem Solved

Online shoppers spend **hours** reading reviews, comparing specs, and second-guessing purchases.

ClariCart automates this entire process by combining **LLM reasoning**, **retrieval-augmented generation (RAG)**, and **real-time web intelligence** to deliver actionable buying insights in seconds — not hours.

---

## 🚀 Highlights

| Capability | Details |
|---|---|
| ⚡ **Live Product Intelligence** | Real-time data from Amazon India via Apify + Playwright |
| 🤖 **AI Assistant (ClariBot)** | Powered by Gemini 2.0 Flash via LangGraph agent |
| 🔍 **Multi-Source Discovery** | DuckDuckGo, Bing, JSON-LD, and regex CSS fallbacks |
| 🧠 **RAG Review Analysis** | ChromaDB + `all-MiniLM-L6-v2` embeddings for deep review mining |
| 📊 **Automated Sentiment** | Auto-generated Pros & Cons tables grounded in real reviews |
| 🌐 **3D Premium UI** | Next.js 16 + Three.js Hyperspeed + Framer Motion animations |
| 🔐 **Auth-Gated Access** | NextAuth.js member-only access to premium AI features |
| 🐳 **Production Ready** | Dockerized backend, Vercel-optimized frontend |

---

## ✨ Features

### 🤖 ClariBot — AI Shopping Assistant
- Conversational product analysis powered by **Gemini 2.0 Flash**
- Understands natural language queries and maps them to real product data
- Generative UI responses: directly renders product cards inside the chat
- Grounded in live scraped data — never hallucinating from stale knowledge

### 🔍 Multi-Strategy Scraping Engine
- **Apify** actor integration for large-scale Amazon review scraping
- **Playwright** Chromium automation for live page rendering + bot bypass
- **JSON-LD** structured data extraction from product pages
- **Regex + CSS selector** fallbacks for resilient data acquisition
- **Multi-engine search** (DuckDuckGo, Bing) for rating and review count lookup

### 🧠 RAG-Powered Review Intelligence
- Ingests raw customer reviews into **ChromaDB** as vector embeddings
- Uses **HuggingFace `all-MiniLM-L6-v2`** for semantic similarity search
- LangGraph retrieval agent synthesizes reviews into structured insights
- Outputs **"Veracity Verdict"**: a structured Pros / Cons / Expert Rating breakdown

### 📊 Product Analytics Dashboard
- Live product metadata: pricing, ratings, review counts, images
- Side-by-side product comparison support
- Sentiment-driven consumer decision support
- Real-time streaming responses from the LangGraph agent

### 🌐 Premium Frontend Experience
- **Three.js Hyperspeed** animated background for a stunning first impression
- **Framer Motion** micro-animations across all interactions
- **Glassmorphism** UI design with dark-mode aesthetics
- **NextAuth.js** authentication with protected routes

---

## 🏗️ System Architecture

<p align="center">
  <img src="screenshots/Screenshot%202026-06-17%20025103.png" width="1000" alt="ClariCart Architecture Diagram"/>
</p>

### Architecture Overview

ClariCart follows a multi-layer AI architecture that combines real-time web intelligence, retrieval-augmented generation (RAG), and agentic reasoning to generate trustworthy product insights.

#### Workflow

1. 👤 User enters a product query through the Next.js dashboard.
2. 🔐 NextAuth validates authentication and initializes the UI session.
3. 🌌 Three.js renders the immersive dashboard experience.
4. 📡 Frontend sends a structured request to the FastAPI backend.
5. 🧠 FastAPI hands off the task to the LangGraph orchestrator.
6. 🗄️ ChromaDB retrieves semantically similar customer reviews.
7. 🔎 Google Search Grounding fetches live pricing and product metadata.
8. 🛒 RapidAPI / Amazon connectors gather real-time product information.
9. 🤖 Gemini 2.0 Flash or Llama 3.3 synthesizes retrieved context.
10. 📊 AI agent generates a final Veracity Verdict.
11. ⚡ LangGraph returns the structured response to FastAPI.
12. 🎨 Next.js dynamically renders product cards and AI insights.
13. ✅ User receives grounded buying recommendations and review intelligence.

### Core Components

| Component                    | Responsibility                     |
| ---------------------------- | ---------------------------------- |
| Next.js Dashboard            | User Interface & Product Discovery |
| NextAuth                     | Authentication & Access Control    |
| FastAPI Backend              | API Layer & Request Processing     |
| LangGraph Orchestrator       | Agent Workflow Management          |
| ChromaDB                     | Vector Search & Review Retrieval   |
| Gemini 2.0 Flash / Llama 3.3 | Reasoning & Verdict Generation     |
| Google Search Grounding      | Live Product Intelligence          |
| RapidAPI / Amazon            | Product Metadata & Reviews         |
| Three.js Engine              | Interactive 3D User Experience     |

### Architecture Flow

```text
👤 User
   ↓
🖥️ Next.js Dashboard (Vercel)
   ↓
⚡ FastAPI Backend (Railway)
   ↓
🧠 LangGraph Orchestrator
   ├── 🗄️ ChromaDB Vector Store
   ├── 🔎 Google Search Grounding
   ├── 🛒 RapidAPI / Amazon
   └── 🤖 Gemini 2.0 Flash / Llama 3.3
   ↓
📊 Veracity Verdict
   ↓
🎨 Dynamic Product Cards
   ↓
✅ User Recommendations
```


## 🛠️ Tech Stack

### 🤖 AI & LLM
| Technology | Role |
|---|---|
| Google Gemini 2.0 Flash | Core LLM for reasoning and response generation |
| LangChain | Agent framework, tool binding, prompt management |
| LangGraph | Stateful agent orchestration (ReAct loop) |
| HuggingFace `all-MiniLM-L6-v2` | Semantic embedding model for RAG |
| ChromaDB | Persistent vector store for review retrieval |

### ⚡ Backend
| Technology | Role |
|---|---|
| FastAPI | High-performance REST API server |
| Python 3.10+ | Core runtime |
| Apify | Cloud actor for scalable Amazon scraping |
| Playwright | Browser automation for live page rendering |
| BeautifulSoup4 | HTML parsing and structured extraction |
| SQLite | Chat history persistence |

### 🖥️ Frontend
| Technology | Role |
|---|---|
| Next.js 16 (App Router) | React framework with SSR/SSG |
| React | UI component architecture |
| Three.js / Postprocessing | Immersive 3D Hyperspeed visual effects |
| Framer Motion | Smooth animations and transitions |
| Tailwind CSS + Vanilla CSS | Styling and glassmorphism design |
| NextAuth.js | Authentication and session management |

### ☁️ Infrastructure
| Technology | Role |
|---|---|
| Docker | Containerized backend deployment |
| Vercel | Frontend edge deployment |
| Render / Railway | Cloud backend hosting |

---

## 📁 Project Structure

```
ClariCart/
├── backend/
│   ├── api.py                  # FastAPI server + LangGraph agent + tool definitions
│   ├── product_api.py          # Product metadata API endpoints
│   ├── review_ingestion.py     # ChromaDB vector ingestion pipeline
│   ├── requirements.txt        # Python dependencies
│   ├── Dockerfile              # Container configuration
│   └── chroma_db/              # Persistent vector store
├── frontend/
│   ├── app/                    # Next.js App Router pages
│   ├── components/             # UI components (ClariBot, dashboard, visuals)
│   ├── styles/                 # CSS + Tailwind configuration
│   └── public/                 # Static assets
├── screenshots/                # Project visuals for documentation
├── dev.ps1                     # One-command local dev launcher (Windows)
└── start_dev.bat               # Alternative dev launcher
```

---

## ⚙️ Local Development

### Prerequisites
- Python 3.10+, Node.js 18+, Git
- API Keys: Google Gemini, Apify

### 1. Clone the Repository
```bash
git clone https://github.com/Viperstom/www.ClariCart.com
cd ClariCart
```

### 2. Backend Setup
```bash
cd backend
cp .env.example .env          # Add your GOOGLE_API_KEY and APIFY_API_TOKEN
pip install -r requirements.txt
uvicorn api:app --reload --host 0.0.0.0 --port 8000
```

### 3. Frontend Setup
```bash
cd frontend
cp .env.example .env.local    # Add your NEXTAUTH_SECRET and API URL
npm install
npm run dev
```

### 4. Quick Launch (Windows)
```powershell
.\dev.ps1                     # Starts both servers simultaneously
```

Open **[http://localhost:3000](http://localhost:3000)** to interact with ClariCart.

---

## 🐳 Production Deployment

### Backend (Docker → Render/Railway)
```bash
cd backend
docker build -t claricart-api .
docker run -p 8000:8000 --env-file .env claricart-api
```

### Frontend (Vercel)
Connect your GitHub repository to Vercel, set `NEXT_PUBLIC_API_URL` to your deployed backend URL, and deploy instantly.

---

## 🗺️ Future Roadmap

- [ ] **Multi-platform support** — Flipkart, Myntra, eBay product analysis
- [ ] **Voice Interface** — Natural speech queries via Web Speech API
- [ ] **Price History Tracking** — Price trend charts with alerts
- [ ] **Comparison Mode** — Side-by-side AI analysis of multiple products
- [ ] **Browser Extension** — Instant ClariCart overlay on any product page
- [ ] **Export Reports** — PDF/CSV export of AI analysis and review summaries

---

## 🛡️ License

**Proprietary / All Rights Reserved.**

This project and its entire source code are completely proprietary. Unauthorized copying, distribution, or reproduction of any part of this repository is strictly prohibited. See the [`LICENSE`](LICENSE) file for full details.

---

<p align="center">
  <b>Built with ❤️ for smarter shopping decisions</b><br/>
  <i>LangChain · LangGraph · FastAPI · Next.js · ChromaDB · Gemini</i>
</p>
