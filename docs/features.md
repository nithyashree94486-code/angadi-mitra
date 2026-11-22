# Proposed Features — Angadi Mitra

## Tech4Bharat 2026 | PS 5.1 – Kirana Stock | Theme 5 – Rural FMCG & Logistics

> **Status:** All capabilities listed below represent proposed and planned functional designs.  
> No features have been implemented or deployed in software at this stage.

---

## 1. Accessibility Features

### 1.1 Multilingual User Interface
- **What it does:** Enables the shopkeeper to navigate the application in their chosen Indian language (e.g., Kannada, Hindi, Tamil, Telugu, English). All labels, counters, instructions, and messages adapt dynamically.
- **Why it matters:** Language is the primary adoption barrier in rural India. Shopkeepers are comfortable with their native vernacular and alienated by English-only enterprise software.
- **How a shopkeeper uses it:** On first launch, the shopkeeper taps their language flag/name. The app remembers this setting for all future sessions.
- **Dependency / Limitation:** Requires verified translation strings for localized retail vocabulary; dialectal variants require alias mapping.

### 1.2 Voice-Assisted Interaction
- **What it does:** Allows shopkeepers to query stock levels, log inventory changes, and receive audio summaries via natural spoken language.
- **Why it matters:** Typing on mobile keyboards during busy store hours is cumbersome and impractical for shopkeepers with low digital literacy.
- **How a shopkeeper uses it:** The shopkeeper holds a microphone button and speaks naturally (e.g., *"Five soap bars arrived"*).
- **Dependency / Limitation:** Dependent on device microphone quality, background noise suppression in noisy bazaars, and browser/cloud speech recognition support.

### 1.3 Image-First Product Selection
- **What it does:** Represents inventory items as visual cards featuring prominent product packaging photos, regional script names, and large stock numerals.
- **Why it matters:** Allows rapid visual identification without reading dense alphanumeric product codes, SKUs, or English descriptions.
- **How a shopkeeper uses it:** The shopkeeper glances at the screen and recognizes products instantly by their packaging visual (e.g., red Parle-G packet, green Lifebuoy soap).
- **Dependency / Limitation:** High-resolution product images must be compressed and cached locally to prevent high bandwidth consumption on low-end phones.

### 1.4 Simple & High-Contrast Navigation
- **What it does:** Provides large touch targets (minimum 48px height), uncluttered screens, high-contrast text, and single-level navigation menus.
- **Why it matters:** Designed specifically for shopkeepers using low-end smartphones with cracked or low-brightness displays in outdoor sunlight.
- **How a shopkeeper uses it:** Big, accessible buttons allow quick one-handed operation without accidental misclicks.
- **Dependency / Limitation:** Must adhere to strict UI component simplicity, resisting feature creep that clutters the screen.

---

## 2. Inventory Management Features

### 2.1 Product Catalog & Alias Management
- **What it does:** Maintains shop items with standardized product categories, brand associations, packaging sizes, and customizable regional aliases.
- **Why it matters:** The same product is called by different colloquial names in different villages (e.g., "Parle biscuit", "glucose biscuit", "ಬಿಸ್ಕತ್").
- **How a shopkeeper uses it:** Associates their own colloquial product names with catalog items so voice recognition connects to the right product.
- **Dependency / Limitation:** Requires building and expanding a localized alias dictionary over time through field observation.

### 2.2 Conversational Stock Quantity Updates
- **What it does:** Updates existing product stock quantities via voice commands or simple numeric increment/decrement buttons.
- **Why it matters:** Eliminates manual multi-step form submissions, making daily inventory tracking fast and frictionless.
- **How a shopkeeper uses it:** Taps "+" or speaks *"Sold 3 packets of sugar"* at the end of the shift or during shelf checks.
- **Dependency / Limitation:** Low-confidence speech interpretations must trigger visual confirmation screens to prevent accidental data corruption.

### 2.3 Distributor Stock Receiving
- **What it does:** Provides a streamlined workflow to record bulk shipments received from FMCG distributors during their weekly or bi-weekly visits.
- **Why it matters:** Deliveries involve multiple product cartons arriving simultaneously; recording them manually takes hours or is completely skipped.
- **How a shopkeeper uses it:** The shopkeeper speaks the received list or selects received items from a quick visual distributor checklist.
- **Dependency / Limitation:** Invoices are often handwritten paper slips; OCR capabilities remain a future exploration, requiring manual confirmation for now.

### 2.4 Low-Stock & Out-of-Stock Visual Alerts
- **What it does:** Continuously checks inventory balances against configurable minimum thresholds and highlights items in yellow (low) or red (out of stock).
- **Why it matters:** Prevents fast-moving staples from stocking out unnoticed, protecting daily store revenue.
- **How a shopkeeper uses it:** The dashboard top ribbon displays a clear counter: *"3 items low, 1 out of stock"*; tapping opens the prioritized replenishment list.
- **Dependency / Limitation:** Requires initial setting of safety thresholds (defaulted heuristically by the system based on pack sizes).

---

## 3. Stock Intelligence & Agentic AI Features

### 3.1 Fast-Moving Product Velocity Analysis
- **What it does:** Monitors product depletion rates over rolling 7-day and 14-day windows to identify high-velocity stock.
- **Why it matters:** Highlights which items generate consistent turnover and need continuous buffer stock.
- **How a shopkeeper uses it:** The shopkeeper reviews a "Fast Movers" card to ensure adequate quantities are on hand before weekend rushes.
- **Dependency / Limitation:** Requires at least 7–14 days of logged stock movements to produce meaningful depletion velocity trends.

### 3.2 Slow-Moving & Dead-Stock Monitoring
- **What it does:** Flags products that have experienced zero or negligible movement over 30+ days and calculates the working capital locked in them.
- **Why it matters:** The problem statement estimates that 15–20% of working capital is trapped in dead stock; releasing this capital improves cash liquidity.
- **How a shopkeeper uses it:** The assistant alerts: *"These 4 items haven't sold in 3 weeks, holding ₹1,200 of your money. Consider discounting or returning them."*
- **Dependency / Limitation:** Relies on consistent logging; unrecorded offline cash sales might artificially inflate dead-stock estimates.

### 3.3 Expiry Date & Batch Tracking
- **What it does:** Records expiry dates on packaged perishables (dairy, bread, packaged snacks) and issues proactive alerts 7, 14, and 30 days prior to expiration.
- **Why it matters:** Kirana stores lose an estimated ₹5,000–₹10,000 per month due to expired stock; proactive warnings allow timely clearance.
- **How a shopkeeper uses it:** An alert advises: *"3 ketchup bottles expire in 5 days; place them at the front counter."*
- **Dependency / Limitation:** Shopkeepers must input expiry dates during stock intake; unpackaged or loose goods lack expiry timestamps.

### 3.4 Seasonal & Festival Demand Insights
- **What it does:** Uses Indian regional festival calendars and seasonal shifts to highlight expected spikes in specific goods (e.g., coconut/sugar before festivals).
- **Why it matters:** Rural demand spikes sharply during festivals (Diwali, Sankranti, Eid); shopkeepers historically guess quantities without historical guidance.
- **How a shopkeeper uses it:** Two weeks before a local festival, the assistant notes: *"Ganesh festival in 10 days; jaggery and camphor demand usually increases."*
- **Dependency / Limitation:** Initial versions rely on calendar heuristics; reliable mathematical forecasting requires multi-year historical datasets.

### 3.5 Budget-Aware Agentic Restocking Engine
- **What it does:** Generates an optimal purchasing recommendation tailored to the shopkeeper's stated cash budget (e.g., ₹2,500), prioritizing critical goods.
- **Why it matters:** Prevents over-purchasing and distributor-driven overselling by capping recommendations strictly at available cash on hand.
- **How a shopkeeper uses it:** The shopkeeper states: *"I have ₹3,000 to spend with the distributor today"*; the assistant generates an itemized list fitting within ₹3,000.
- **Dependency / Limitation:** Budget calculations are strictly deterministic; requires accurate recorded wholesale/purchase prices.

---

## 4. Supporting & Operational Features

### 4.1 Optional Barcode Scanning
- **What it does:** Scans standard packaging barcodes (EAN-13, UPC) using the mobile device camera to pull up catalog product records.
- **Why it matters:** Speeds up product onboarding for standard branded FMCG packaged goods.
- **How a shopkeeper uses it:** Points the phone camera at a soap box barcode to automatically identify the product.
- **Dependency / Limitation:** Camera quality on low-end devices and poor lighting in village shops can cause scan delays; remains an optional, non-mandatory input.

### 4.2 Manual Selection for Loose / Unpackaged Goods
- **What it does:** Provides dedicated visual categories for unpackaged staples (e.g., loose rice, pulses, sugar, grains by kilogram).
- **Why it matters:** A significant percentage of village kirana sales consists of loose commodities that have no barcodes or manufacturer packaging.
- **How a shopkeeper uses it:** Taps the "Grains/Pulses" category and increments loose weight quantities (e.g., +10 kg).
- **Dependency / Limitation:** Requires flexible unit tracking (kg, grams, liters, packets).

### 4.3 Supplier & Distributor Contact Records
- **What it does:** Maintains basic contact cards for regular wholesale distributors, including delivery days and notes.
- **Why it matters:** Helps shopkeepers track when specific distributors (e.g., dairy, biscuit, detergent vendors) are scheduled to visit.
- **How a shopkeeper uses it:** Checks which distributor is visiting tomorrow to review restocking needs for their specific product line.
- **Dependency / Limitation:** Manual data entry by the shopkeeper.

### 4.4 Audit Trail & Historical Log
- **What it does:** Immutable log recording all stock additions, deductions, AI recommendations, and shopkeeper approval timestamps.
- **Why it matters:** Ensures complete operational transparency and dispute resolution if discrepancies arise.
- **How a shopkeeper uses it:** Can review past transactions if stock numbers don't match shelf counts.
- **Dependency / Limitation:** Stored securely in database tables; must be compact to avoid excessive storage bloat.
