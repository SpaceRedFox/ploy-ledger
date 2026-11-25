# 👾 Ploy's Ledger (v1.0.9) — Personal Cash Flow & Expense Tracker

A single-file, offline-first personal income and expense tracker built with a **Classic 16-Bit Retro Pixel** aesthetic. Designed specifically around real-world salary cycles, strict category taxonomy, and secure two-way cloud synchronization with Google Sheets.

🔗 **Live App:** [https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/](https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/)

---

## 💡 Problem Statement & Design Philosophy
Most personal finance apps force users into rigid 1st–31st calendar cycles, bloat the interface with unnecessary bank-syncing features, or lack strict category controls. **Ploy's Ledger** solves this with:
1. **Custom 26th Pay-Cycle Engine:** Automatically calculates financial months starting on the **26th** of the preceding month, shifting to the preceding Friday if the 26th falls on a weekend.
2. **Offline-First Single-File Architecture:** Built with zero external framework bloat in a single portable `index.html` file—ensuring instant load times, 100% offline logging, and seamless PWA (Add to Home Screen) installation.
3. **Zero-Server Cloud Sync & Privacy:** Syncs across devices (iOS, Android, Desktop) via a private Google Apps Script backend connected to Google Sheets, protected by client-side **AES-GCM encryption** and a **PIN lock**.

---

## ✨ Key Features

### 1. 3-Tab Streamlined Workflow
* **➕ Quick Entry (Default Screen):** Ordered for fast daily logging—**Date** (with `Today` shortcut & `21 Nov 2026` display format) $\rightarrow$ **4 Main Categories** $\rightarrow$ **25 Locked Sub-Categories** $\rightarrow$ **Amount** (with quick-add `+50`, `+100`, `+500`, `+1,000` buttons) $\rightarrow$ **Note**.
* **📅 Daily View:** Real-time KPI summary, category proportion bars, filterable transaction history, and instant toggle between **26th Pay Cycle** and **Calendar Month (1–31)**.
* **📊 Annual Dashboard:** 12-month cash-flow visualization with auto-highlighting for the active/selected month and a symmetric **2×2 Sub-Category Drill-Down** grid.

### 2. Strict Category Taxonomy (4 Main Groups • 25 Sub-Categories)
* **Income (5):** `Salary`, `Bonus`, `Dividend`, `Interest`, `Others`
* **Savings (5):** `Retirement_PVD`, `Emergency_Cash`, `Emergency_AOTCOOP`, `Travel`, `Investment`
* **Fixed_Expense (6):** `WHT`, `Life/Health Insurance`, `Car Insurance`, `Condo Maintenance Fee`, `Personal Trainer`, `Debt Repayment`
* **Variable_Expense (9):** `Food & Beverage`, `Non Food`, `Utilities`, `Gasoline`, `Subscription`, `Credit Card Installment`, `Books & Education`, `Bread-Making`, `Others`

### 3. Precision, Security & Portability
* **Precision Integer Math:** Stores currency values in integer *satang* (`amount_satang`) to eliminate JavaScript floating-point rounding errors.
* **Two-Way Google Sheets Sync (`POST` API):** Secure synchronization via Google Apps Script using `Script Properties` (`API_SECRET_KEY`), `LockService` concurrency control, and optional **AES-GCM** encrypted payload envelopes.
* **Client-Side PIN Lock:** 4–6 digit PIN hashed locally via Web Crypto API (`SHA-256`).
* **Data Backup & Export:** One-click `.csv` export (UTF-8 BOM) and schema-validated `.json` backup/restore (`Schema v1.0.0`).
* **2-Mode Retro Theme:** Crisp 16-bit pixel borders with `JetBrains Mono` typography and 1-click switching between **☀️ Day (Pastel)** and **🌙 Night (Modern Black)**.

---

## 🛠️ Tech Stack & Architecture
* **Frontend:** Semantic HTML5, CSS3 (Custom Properties, Mobile-First Responsive Grid), Vanilla JavaScript (ES6+)
* **Local Storage:** Browser `LocalStorage` with strict JSON Schema Validation (`v1.0.0`)
* **Cloud Backend:** Google Apps Script Web App (`doPost` JSON API) + Google Sheets (`Transactions` database)
* **Security:** Web Crypto API (`SHA-256` PIN hashing & `AES-GCM` payload encryption)
* **Hosting:** GitHub Pages (Static HTTPS + Mobile PWA Shortcut)

---

## 🚀 Setup & Deployment Guide

### 1. Frontend Hosting (GitHub Pages)
1. Clone or fork this repository (keep `index.html` at the root directory).
2. Go to **Settings** $\rightarrow$ **Pages** $\rightarrow$ set Branch to `main` (`/root`) and click **Save**.
3. Open your GitHub Pages URL on mobile (**Safari** on iOS or **Chrome** on Android) and tap **Add to Home Screen**.

### 2. Cloud Sync Setup (Google Sheets + Apps Script)
1. Create a Google Sheet and open **Extensions** $\rightarrow$ **Apps Script**.
2. Paste the backend script (`Code.gs`), go to **Project Settings** $\rightarrow$ **Script Properties**, and add `API_SECRET_KEY`.
3. Click **Deploy** $\rightarrow$ **New deployment** $\rightarrow$ **Web app** (Execute as: *Me*, Who has access: *Anyone*) and copy the `/exec` URL.
4. In the **Ploy's Ledger** web app, tap **💾 (Top Right)** $\rightarrow$ enter your **Web App URL** and **Secret Key** $\rightarrow$ tap **Save & Sync**.

---

## 📋 Changelog
* **v1.0.9:** Refined cloud sync stability, UI polish, and repository documentation alignment.
* **v1.0.8:** Upgraded Google Apps Script sync to `POST`-only with `API_SECRET_KEY`, `LockService`, and client-side `AES-GCM` payload encryption.
* **v1.0.4 – v1.0.5:** Added two-way Google Sheets sync and refined form layout / Night Mode contrast.
* **v1.0.1 – v1.0.3:** Locked 4 main / 25 sub-category taxonomy, reordered Entry form (Date first), simplified theme toggle to 2 modes (Day/Night), and aligned Dashboard drill-down cards into a 2×2 grid.
* **v1.0.0:** Initial release with 26th pay-cycle engine, integer satang storage, PIN lock, and JSON/CSV portability.
