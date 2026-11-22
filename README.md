# 👾 Ploy's Ledger — Personal Finance & Cash Flow Tracker

A single-file, offline-first personal income and expense tracker built with a **Classic 16-Bit Retro Pixel** aesthetic. Designed specifically around real-world salary cycles rather than rigid calendar months.

🔗 **Live Demo:** [https://SpaceRedFox.github.io/ploy-ledger/](https://SpaceRedFox.github.io/ploy-ledger/)

---

## 💡 Problem Statement & Design Philosophy
Most personal finance apps force users into a standard 1st–31st calendar cycle and bury simple daily logging behind bloated bank-syncing menus. **Ploy's Ledger** solves this by:
1. **Custom Pay-Cycle Engine:** Automatically calculates financial months starting on the **26th** (shifting to the preceding Friday if the 26th falls on a weekend).
2. **Zero-Latency Single-File Architecture:** Built with vanilla HTML, CSS, and JavaScript in a single portable file—no external framework bloat, instant load times, and 100% offline capability.
3. **Privacy by Default:** All financial records stay strictly on the user's device via `LocalStorage`, making the public live demo safe for anyone to test without exposing personal data.

---

## ✨ Key Features
* **3-Tab Streamlined Workflow:**
  * **Entry Tab:** Fast mobile-first transaction logging with dynamic sub-categories across 4 core cash-flow groups (`Income`, `Savings`, `Fixed_Expense`, `Variable_Expense`).
  * **Daily View:** Real-time KPI summary, category breakdown, and transaction filtering[cite: 1].
  * **Annual Dashboard:** 12-month cash-flow visualization with auto-highlighting for the active month and drill-down analytics[cite: 1].
* **Precision Integer Math:** Stores currency values in integer *satang* (`amount_satang`) to eliminate floating-point rounding errors[cite: 1].
* **Adaptive Retro UI:** Crisp pixel borders, `JetBrains Mono` typography, and automatic **Day Pastel / Night Modern Black** theme switching[cite: 1].
* **Data Portability & Security:**
  * Export to `.csv` (UTF-8 BOM) for Excel/Google Sheets[cite: 1].
  * Schema-validated `.json` backup and restore[cite: 1].
  * Client-side PIN lock (4–6 digits hashed with SHA-256)[cite: 1].

---

## 🛠️ Tech Stack & Architecture
* **Frontend:** Semantic HTML5, CSS3 (Custom Properties & Responsive Mobile-First Grid), Vanilla JavaScript (ES6+)
* **Storage:** Browser `LocalStorage` with JSON Schema Validation (`v1.0.0`)[cite: 1]
* **Security:** Web Crypto API (`SHA-256` PIN hashing)[cite: 1]
* **Hosting:** GitHub Pages[cite: 1]

---

## 🚀 How to Run Locally or Deploy
1. Clone or download `index.html` from this repository.
2. Open `index.html` directly in any modern web browser—no build step or server required.
3. For mobile app experience: Open the GitHub Pages link in **Safari (iOS)** or **Chrome (Android)** and select **Add to Home Screen**[cite: 1].
