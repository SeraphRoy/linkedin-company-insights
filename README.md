# LinkedIn: Blind Reviews + Levels SWE (Per-level Totals)

A lightweight userscript that adds a **Company Insights panel** when you browse LinkedIn job or company pages.  
It shows:

- ⭐ **Blind** headline company rating (overall score + review count) with a quick link to Blind.
- 💰 **Levels.fyi** per-level average total compensation for **Software Engineer (US)** roles.

This saves you from opening multiple tabs to check a company’s reputation and salary bands while looking at jobs on LinkedIn.

---

## 📸 Features

- **Blind reviews**
  - Extracts the **overall company rating** (e.g. `4.2 ⭐`) and **review count** (e.g. `(616)`).
  - Direct link to the Blind company reviews page.
- **Levels.fyi salaries**
  - Shows a table of **levels (L3–L10, etc.)** and their **average total compensation** for SWE (US).
  - Data parsed directly from Levels.fyi’s embedded JSON.
- **LinkedIn integration**
  - Works on job search results, job detail pages, and company profile pages.
  - Panel updates automatically when navigating inside LinkedIn’s SPA.

---

## 🛠 Installation

1. Install a user script manager:
   - [Tampermonkey](https://www.tampermonkey.net/) (Chrome/Edge/Firefox recommended)  
   - or Violentmonkey / Greasemonkey.
2. Install the script:
   - **Greasy Fork:** [link once published]  
   - **GitHub:** [raw userscript link once in repo]

Once installed, visit any LinkedIn job or company page — the **Company Insights** panel appears in the bottom-right corner.

---

## 🔒 Permissions

- `@grant GM_xmlhttpRequest` – fetch data cross-domain (LinkedIn → Blind/Levels).
- `@connect teamblind.com` / `www.teamblind.com` – allow Blind requests.
- `@connect levels.fyi` / `www.levels.fyi` – allow Levels.fyi requests.
- `@match https://www.linkedin.com/*` – only runs on LinkedIn.
- `@grant GM_addStyle` – injects the floating panel styles.

No analytics, no external libraries, no tracking.

---

## ⚠️ Notes

- **Blind subcategory scores (Career Growth, Compensation, WLB, etc.) are not exposed publicly** unless logged in, so the script shows only the headline rating + review count.
- If Blind shows `n/a`, try opening the company’s Blind page directly to verify it has a public rating.
- Some companies on Levels.fyi may have missing or incomplete SWE salary data.

---

## 📦 Development

- Script file: [`linkedin-blind-levels.user.js`](./linkedin-blind-levels.user.js)  
- Console debug logs are prefixed with `[LI-Insights]`.

---

## 🗺 Roadmap

- [ ] Drag-to-move or pin the panel left/right.  
- [ ] Cache results in `localStorage` for faster navigation.  
- [ ] Support other roles (e.g., PM, DS) from Levels.fyi.  
- [ ] Enhance Blind parsing when logged-in APIs are available.

---

## 📜 License

[MIT](./LICENSE) – free to use, modify, share. No warranty.

---

## 🔄 Changelog

### 1.0
- Initial release
- Shows Blind headline review score & count
- Shows Levels.fyi SWE (US) per-level average total compensation
- Works across LinkedIn job and company pages
