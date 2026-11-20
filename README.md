# 🏪 Angadi Mitra

> **Making everyday kirana management simpler through technology.**

[![Tech4Bharat 2026](https://img.shields.io/badge/Tech4Bharat-2026-orange)](https://thegavshackathon.com)
[![Problem Statement](https://img.shields.io/badge/PS%205.1-Kirana%20Stock-green)](https://thegavshackathon.com/docs/Tech4Bharat-2026-Problem-Statements.pdf)
[![Theme](https://img.shields.io/badge/Theme%205-Retail%2C%20FMCG%20%26%20Logistics-blue)](https://thegavshackathon.com)
[![Status](https://img.shields.io/badge/Status-Foundation%20Phase-yellow)](#project-status)

---

## 📋 Hackathon Details

| Field | Details |
|---|---|
| **Hackathon** | Tech4Bharat 2026 – JanAI Mass Entrepreneurship Challenge |
| **Problem Statement** | PS 5.1 – Kirana Stock |
| **Theme** | Theme 5 – Retail, FMCG & Logistics |
| **AI Approach** | Agentic AI |
| **Team** | Nithyashree & Pooja |

---

## 🛒 Problem Overview

Small and village-level kirana (provision) stores across India manage stock through memory and physical shelf checks. They lack billing systems, structured inventory records, and tools to identify slow-moving or expiring products. This leads to:

- **Out-of-stock situations** on fast-moving items, causing lost sales
- **Dead stock** tying up approximately 15–20% of working capital
- **Stock expiry losses** estimated at ₹5,000–₹10,000 per month
- **Festival demand** being guessed rather than anticipated
- **Distributor-driven purchasing** without data-backed decisions
- **Limited digital literacy** making existing software inaccessible

> *Source: Tech4Bharat 2026 Problem Statement PS 5.1 – verify exact figures against the official document.*

---

## 💡 Proposed Solution

**Angadi Mitra** is a multilingual, image-first, voice-assisted **Agentic AI** inventory management assistant designed specifically for small and village-level kirana stores across India.

It is **not** a complicated ERP or accounting system. It is a simple digital assistant that feels accessible to a first-time digital user.

### What it does:
- Understands voice commands in Indian languages ("Add ten biscuit packets")
- Shows visual dashboards with product images and large readable quantities
- Identifies low-stock, out-of-stock, and slow-moving products
- Flags products nearing expiry
- Suggests restocking quantities within the shopkeeper's chosen budget
- **Requires shopkeeper approval before any purchase action**
- Works on entry-level Android devices with low-bandwidth connectivity
- Delivers useful insights within the first 7 days

---

## ✨ Key Features

| # | Feature | Description |
|---|---|---|
| 1 | 🌐 Multilingual Onboarding | Language selection on first visit (Kannada, Hindi, English, and other Indian languages) |
| 2 | 🔐 Simple Authentication | Minimal-info account creation for first-time digital users |
| 3 | 🖼️ Image-First Dashboard | Large product photos, local-language names, simple icons |
| 4 | 📦 Inventory Management | Add/update products, record incoming stock, view low/out-of-stock items |
| 5 | 🎙️ Voice Stock Updates | Say "5 soap boxes arrived" – system asks for confirmation before saving |
| 6 | 🚚 Distributor Receiving | Record deliveries via voice or visual selection with confirmation |
| 7 | 🔍 Product Identification | Barcode scanning, image selection, manual entry, regional aliases |
| 8 | 💰 Price Management | Shopkeeper-controlled purchase and selling prices |
| 9 | ⚠️ Low-Stock Alerts | Configurable thresholds and notifications |
| 10 | 📅 Expiry Monitoring | Track and alert on products nearing expiry (where data is available) |
| 11 | 🐌 Dead-Stock Analysis | Identify slow-moving stock with explanations |
| 12 | 🚀 Fast-Moving Tracking | Identify high-velocity products to prevent stockouts |
| 13 | 🤖 AI Restocking Suggestions | Budget-aware recommendations with reasons, requiring shopkeeper approval |
| 14 | 💵 Budget-Aware Purchasing | Respect cash budget; prioritise, defer, and explain trade-offs |
| 15 | 🎊 Festival Demand Forecasting | Demand estimates for festivals and seasons (labelled as estimates) |
| 16 | 📆 7-Day Onboarding | Progressive workflow delivering value from Day 1 |

---

## 🤖 Agentic AI Approach

Angadi Mitra uses a genuine agentic AI architecture — **not a simple chatbot**:

```
Shopkeeper Voice/Text Input
        ↓
  [STT / NLP Layer]
        ↓
  [Agent Orchestrator] ← LLM (Gemini / OpenAI)
        ↓
  ┌─────┴─────────────────────────────────────┐
  │  Tool Calls (the agent uses these):        │
  │  • get_inventory_status()                  │
  │  • update_stock_quantity()                 │
  │  • check_budget_headroom()                 │
  │  • analyse_stock_velocity()               │
  │  • get_expiry_alerts()                     │
  │  • generate_restock_plan()                 │
  │  • request_shopkeeper_approval()           │
  └───────────────────────────────────────────┘
        ↓
  [Deterministic Logic Layer]
  (Inventory arithmetic, budget validation,
   threshold checks — no AI guessing here)
        ↓
  [Human Approval Gate]
  (Every purchase requires explicit approval)
        ↓
  [Audit Log]
```

**Key principles:**
- Deterministic logic for inventory and budget (not AI-estimated)
- LLM only for understanding, planning, and explaining
- Shopkeeper approves every purchase — the AI never spends money autonomously
- All forecasts labelled as estimates, not guarantees

See [`docs/agentic_ai_workflow.md`](docs/agentic_ai_workflow.md) for full details.

---

## 🛠️ Proposed Technology Stack

> *Stack is under evaluation. Final decisions will be documented in [`docs/technology_stack.md`](docs/technology_stack.md).*

| Layer | Proposed Technology | Reason |
|---|---|---|
| **Frontend** | React + TypeScript + Vite | Component-based, beginner-friendly, good mobile support |
| **UI** | Tailwind CSS + shadcn/ui | Rapid UI development, accessible components |
| **Backend** | Supabase (PostgreSQL + Auth + Storage) | Managed, beginner-friendly, free tier, real-time |
| **AI Agent** | Google Gemini API (Function Calling) | Strong Indian language support, generous free tier |
| **Voice (STT)** | Web Speech API / Google Cloud STT | Browser-native fallback + cloud for Indian languages |
| **Voice (TTS)** | Web Speech API / Google Cloud TTS | Verified Indian language voice support |
| **Offline** | IndexedDB + background sync | Local-first with safe sync on reconnect |
| **PWA** | Vite PWA plugin | Installable on Android, offline-capable |

---

## 📁 Project Structure

```
angadi-mitra/
├── README.md
├── .gitignore
├── docs/
│   ├── problem_statement_analysis.md   # PS 5.1 analysis and traceability
│   ├── requirements_traceability.md    # Official req → feature mapping
│   ├── solution_architecture.md        # System architecture and design
│   ├── agentic_ai_workflow.md          # Agent workflow and tool definitions
│   ├── technology_stack.md             # Tech stack research and decisions
│   ├── competitor_analysis.md          # Competitor comparison table
│   ├── field_validation_plan.md        # Shopkeeper interview and validation plan
│   ├── business_model.md               # Revenue and sustainability model
│   ├── presentation_content.md         # 9-slide presentation outline
│   └── implementation_roadmap.md       # Development roadmap
├── src/
│   ├── agents/                         # Agentic AI orchestration logic
│   ├── components/                     # React UI components
│   ├── pages/                          # Application pages/screens
│   ├── services/                       # API and database service layer
│   ├── hooks/                          # Custom React hooks
│   ├── types/                          # TypeScript type definitions
│   ├── utils/                          # Utility functions
│   └── i18n/                           # Internationalisation strings
└── public/                             # Static assets
```

---

## 🚦 Project Status

> **Foundation Phase** — Research, documentation, and architecture complete. Implementation not yet started.

| Phase | Status | Description |
|---|---|---|
| ✅ Research | Complete | Problem statement, competitors, tech stack |
| ✅ Documentation | Complete | Architecture, workflow, requirements |
| ✅ Repository | Complete | GitHub repo, project structure |
| 🔄 UI Prototype | Planned | React frontend skeleton |
| 🔄 Backend Setup | Planned | Supabase schema and APIs |
| 🔄 Agent Integration | Planned | Gemini function-calling agent |
| 🔄 Voice Integration | Planned | STT/TTS in Indian languages |
| 🔄 Field Validation | Proposed | Shopkeeper interviews (not yet conducted) |
| 🔄 Pilot Testing | Proposed | Requires implementation first |

---

## ⚙️ Setup Instructions

> *Implementation not yet started. These instructions will be updated when code is added.*

### Prerequisites (planned)
- Node.js 18+
- A Supabase account (free tier)
- A Google Cloud account (for Gemini API and Cloud STT/TTS)

### Environment Variables (planned)
Create a `.env.local` file (never commit this file):
```
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
VITE_GEMINI_API_KEY=your_gemini_api_key
VITE_GOOGLE_STT_KEY=your_google_stt_key
```

---

## 👥 Team

| Name | GitHub | Role |
|---|---|---|
| Nithyashree | [@nithyashree94486-code](https://github.com/nithyashree94486-code) | Lead Developer & Product |
| Pooja | [@pooja132a79450](https://github.com/pooja132a79450) | Developer & Research |

---

## 📄 Documentation Index

| Document | Description |
|---|---|
| [Problem Statement Analysis](docs/problem_statement_analysis.md) | PS 5.1 breakdown and traceability |
| [Requirements Traceability](docs/requirements_traceability.md) | Official req → feature mapping |
| [Solution Architecture](docs/solution_architecture.md) | System design and diagrams |
| [Agentic AI Workflow](docs/agentic_ai_workflow.md) | Agent orchestration design |
| [Technology Stack](docs/technology_stack.md) | Tech decisions and rationale |
| [Competitor Analysis](docs/competitor_analysis.md) | Market landscape |
| [Field Validation Plan](docs/field_validation_plan.md) | Research and validation approach |
| [Business Model](docs/business_model.md) | Revenue and sustainability |
| [Presentation Content](docs/presentation_content.md) | 9-slide pitch outline |
| [Implementation Roadmap](docs/implementation_roadmap.md) | Development plan |

---

## ⚠️ Important Disclaimers

- All features listed are **proposed** — implementation has not yet started.
- Field research figures from the problem statement must be verified against the [official PDF](https://thegavshackathon.com/docs/Tech4Bharat-2026-Problem-Statements.pdf).
- No real shopkeeper interviews or pilot tests have been conducted yet.
- AI forecasting features will be labelled as estimates, not guarantees.
- No purchase orders are placed autonomously — shopkeeper approval is mandatory.

---

*Built for Tech4Bharat 2026 | PS 5.1 – Kirana Stock | Theme 5 – Retail, FMCG & Logistics*
