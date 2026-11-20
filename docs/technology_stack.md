# Technology Stack — Angadi Mitra

> **Status:** Under evaluation — decisions not yet finalised.
> **Last updated:** November 2026

---

## 1. Evaluation Criteria

For a student team building a hackathon prototype, the technology stack must balance:

| Criterion | Weight | Reason |
|---|---|---|
| **Beginner-friendliness** | High | Small team, limited time |
| **Free tier availability** | High | No budget for infrastructure |
| **Indian language support** | High | Core product requirement |
| **Mobile-first** | High | Target users on Android |
| **Offline capability** | High | Village-level connectivity |
| **Ecosystem size** | Medium | Community help available |
| **Scalability path** | Medium | Beyond hackathon |

---

## 2. Frontend

### Recommended: React + TypeScript + Vite

**Why React?**
- Largest frontend ecosystem; abundant tutorials and community help
- Component-based architecture suits an image-first dashboard
- Strong PWA support through Vite PWA plugin
- TypeScript catches type errors early — important for inventory arithmetic

**Why Vite over Create React App?**
- Significantly faster development server
- Better tree-shaking for smaller bundle sizes
- Active maintenance (CRA is deprecated)

**UI Library: Tailwind CSS + shadcn/ui**
- Tailwind enables rapid styling without writing CSS files
- shadcn/ui provides accessible, customisable components
- Both work well together and are beginner-friendly

**PWA Support: Vite PWA Plugin (vite-plugin-pwa)**
- Makes the app installable on Android home screen
- Enables service workers for offline caching
- Supports background sync

**Multilingual: react-i18next**
- Industry-standard internationalisation for React
- Supports right-to-left languages
- JSON-based translation files are easy to maintain

**Barcode Scanning: @zxing/browser**
- Open-source, works with device camera
- Supports most standard barcodes (EAN-13, QR, Code128, etc.)
- No backend required for scanning

---

## 3. Backend

### Recommended: Supabase

**What is Supabase?**
Supabase is an open-source Backend-as-a-Service built on PostgreSQL. It provides:
- PostgreSQL database with SQL query support
- Authentication (OTP/magic link — no password needed)
- File storage (for product images)
- Real-time subscriptions
- Row Level Security (RLS) — data isolation between shopkeepers
- Edge Functions for server-side logic (Deno/TypeScript)

**Why Supabase for a beginner team?**
- Free tier is generous (500MB database, 1GB storage, 50MB Edge Functions)
- Dashboard UI makes database management visual
- Auto-generated REST and GraphQL APIs
- OTP-based authentication suits Indian mobile users (no email required)
- RLS enforces data privacy without application-level code

**Alternative considered: Firebase**
- Firebase is well-known and has good documentation
- However, Supabase uses SQL (more transferable skill) and is open-source
- Supabase's RLS is simpler to reason about for data privacy

---

## 4. Database

### PostgreSQL via Supabase

PostgreSQL is the industry-standard open-source relational database. Key reasons:
- Strong data integrity for financial and inventory data
- JSON/JSONB columns for flexible AI recommendation storage
- Full-text search for product name matching
- Row Level Security for multi-tenant data isolation

See `solution_architecture.md` for the proposed schema.

---

## 5. AI and Agent Orchestration

### Recommended: Google Gemini API

**Why Gemini?**
- **Function Calling support** — essential for true agentic AI
- **Strong Indian language support** — Gemini 1.5 Flash handles Kannada, Hindi, Tamil, Telugu, Malayalam, Bengali, and others
- **Generous free tier** — Gemini 1.5 Flash: 15 requests/minute, 1 million tokens/day (as of research date — verify current limits)
- **Multimodal** — can analyse product images if needed
- **Context window** — 1M token context for analysing full inventory history

**Gemini Model Recommendation:**
- `gemini-1.5-flash` — fast, cost-effective, suitable for voice-to-action workflow
- `gemini-1.5-pro` — for complex multi-step analysis (use sparingly)

**Alternative considered: OpenAI GPT-4o**
- Strong function calling support
- Less generous free tier
- Good but not verified superior Indian language support
- Higher cost at scale

**Alternative considered: LangChain / LlamaIndex**
- Useful agent frameworks but add complexity for a beginner team
- For hackathon scope, direct Gemini Function Calling API is simpler
- Can be added later for more complex orchestration

---

## 6. Voice: Speech-to-Text (STT)

### Tier 1 (Primary): Web Speech API

**What it is:** Built into Chrome and Chromium-based browsers. Free, no API key needed.

**Indian language support (browser):**
- Hindi (`hi-IN`): ✅ Generally available in Chrome
- Kannada (`kn-IN`): ✅ Generally available in Chrome
- Tamil (`ta-IN`): ✅ Generally available in Chrome
- Telugu (`te-IN`): ✅ Generally available in Chrome
- Bengali (`bn-IN`): ✅ Generally available in Chrome
- Malayalam (`ml-IN`): ✅ Generally available in Chrome
- Gujarati (`gu-IN`): ✅ Generally available in Chrome
- English (India) (`en-IN`): ✅ Well supported

> **Note:** Browser STT support varies by device, OS version, and Chrome version. Always test on target devices. Some languages may require language packs downloaded to the device.

**Limitation:** Requires microphone permission. Quality varies on low-end devices.

### Tier 2 (Fallback / Enhanced): Google Cloud Speech-to-Text

**Indian language support (verified from Google Cloud documentation):**
- Hindi (`hi-IN`): ✅ Supported
- Kannada (`kn-IN`): ✅ Supported
- Tamil (`ta-IN`): ✅ Supported
- Telugu (`te-IN`): ✅ Supported
- Bengali (`bn-IN`): ✅ Supported
- Malayalam (`ml-IN`): ✅ Supported
- Marathi (`mr-IN`): ✅ Supported
- Gujarati (`gu-IN`): ✅ Supported
- Punjabi (`pa-IN`): ✅ Supported
- Urdu (`ur-IN`): ✅ Supported
- Odia (`or-IN`): Verify against current [Google Cloud STT language list](https://cloud.google.com/speech-to-text/docs/speech-to-text-supported-languages)

**Cost:** Free for first 60 minutes/month; then per-minute pricing.

> **Source:** https://cloud.google.com/speech-to-text/docs/speech-to-text-supported-languages
> Always verify against the current documentation — language support changes.

---

## 7. Voice: Text-to-Speech (TTS)

### Tier 1 (Primary): Web Speech API (SpeechSynthesis)

Built into browsers. Free, no API key.

**Indian language availability depends on voices installed on device.** This is a known limitation of browser TTS — voice quality and language availability vary significantly.

### Tier 2 (Enhanced): Google Cloud Text-to-Speech

**Verified Indian language voices (from Google Cloud documentation):**

| Language | Code | Standard Voices | WaveNet/Neural2 | Notes |
|---|---|---|---|---|
| Hindi | `hi-IN` | ✅ | ✅ | Good quality |
| Kannada | `kn-IN` | ✅ | ✅ | Available |
| Tamil | `ta-IN` | ✅ | ✅ | Available |
| Telugu | `te-IN` | ✅ | ✅ | Available |
| Bengali | `bn-IN` | ✅ | ✅ | Available |
| Malayalam | `ml-IN` | ✅ | ✅ | Available |
| Marathi | `mr-IN` | ✅ | ✅ | Available |
| Gujarati | `gu-IN` | ✅ | ✅ | Available |
| Punjabi | `pa-Guru-IN` | ✅ | Verify | Check current docs |
| Urdu | `ur-IN` | ✅ | Verify | Check current docs |

> **Source:** https://cloud.google.com/text-to-speech/docs/voices
> Always verify — Google updates supported voices regularly.

**Cost:** 1 million characters/month free for Standard voices; 1 million/month for WaveNet at a cost (verify current pricing).

### Not evaluated in depth: Azure Speech, Karya
- Azure Speech has strong Indian language support — evaluate if Google Cloud limits are reached
- Karya language services are designed for Indian languages — evaluate for regional dialects
- Sources: https://learn.microsoft.com/en-us/azure/ai-services/speech-service/language-support and https://languageserver.karya.in/

---

## 8. Offline Support

### IndexedDB via Dexie.js

**Why Dexie.js?**
- Wrapper around native IndexedDB with a cleaner API
- Supports reactive queries (integrates with React)
- Handles schema migrations
- Large community and documentation

**Sync Strategy:**
- Pending writes stored in IndexedDB with `sync_status: 'pending'`
- Background sync via Service Worker when connectivity returns
- Conflict resolution surfaced to shopkeeper

**Network detection:** `navigator.onLine` + periodic ping for more reliable detection

---

## 9. Summary Recommendation

| Layer | Technology | Why |
|---|---|---|
| Frontend Framework | React + TypeScript | Ecosystem, beginner-friendly |
| Build Tool | Vite | Speed, modern tooling |
| UI Styling | Tailwind CSS + shadcn/ui | Rapid development |
| PWA | vite-plugin-pwa | Offline + installable |
| Internationalisation | react-i18next | Standard, flexible |
| Barcode | @zxing/browser | Open-source, no backend |
| Backend & Database | Supabase (PostgreSQL) | Managed, free tier, RLS |
| Authentication | Supabase Auth (OTP) | Phone-based, no email needed |
| File Storage | Supabase Storage | Product images |
| AI Agent | Gemini 1.5 Flash (Function Calling) | Indian languages, free tier |
| STT (primary) | Web Speech API | Free, browser-native |
| STT (enhanced) | Google Cloud STT | Better accuracy, more languages |
| TTS (primary) | Web Speech API | Free, browser-native |
| TTS (enhanced) | Google Cloud TTS | Better Indian voice quality |
| Offline cache | Dexie.js (IndexedDB) | Structured local storage |
| Hosting | Vercel / Netlify | Free tier, easy deployment |

---

## 10. What to Avoid

| Technology | Reason to Avoid |
|---|---|
| Native Android (Java/Kotlin) | Longer development time for a student team |
| Complex ML models (self-hosted) | Requires GPU, too slow to implement |
| SQL Server / Oracle | Expensive, unnecessary for this scale |
| Elasticsearch | Overkill for product search at this scale |
| Redis (initially) | Not needed until scaling |
| Custom auth system | Use Supabase Auth — do not build your own |

---

## 11. Important Caveats

- Language support figures must be verified against current documentation before presentation
- Free tier limits change — verify before demo day
- Web Speech API behaviour on low-end Android varies — test on actual devices
- Gemini API rate limits may affect real-time voice workflows — implement queuing
- IndexedDB sync conflicts need careful handling — plan this early

---

*This document represents a research-based recommendation. Final technology decisions will be made during prototype development.*
