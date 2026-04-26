# Portfomily — Family Wealth Tracker

> Track your family's net worth, investments, property, CPF, and FIRE progress — all in one place. Runs 100% in your browser. Your data never leaves your device.

**[🚀 Try it live →](https://portfomily.netlify.app/)**  &nbsp;|&nbsp; **[GitHub Pages →](https://anduslim.github.io/Portfomily/FamilyWealthTracker.html)**  &nbsp;|&nbsp; **[Marketing page →](https://anduslim.github.io/Portfomily/)**

---

## What it does

Portfomily is a single-file personal finance app built for Singapore families. No sign-up, no server, no subscriptions — open it in a browser and start tracking.

| View | What you get |
|---|---|
| **Dashboard** | Net worth, liquid assets, unrealised P&L, FIRE progress, asset allocation chart |
| **SGX Holdings** | Singapore Exchange stocks with auto price refresh, broker filter |
| **US Holdings** | US stocks and ETFs with USD→SGD conversion |
| **Other Markets** | HK, LSE, Euronext, ASX, TSE holdings with per-row currency and editable FX rates |
| **FIRE Tracker** | Multi-scenario retirement readiness — liquid-only vs post-property-sale, 4% and 3% SWR |
| **Properties** | Equity tracking, joint ownership %, CPF deployed, rental/mortgage cash flow |
| **Cash & Expenses** | Savings accounts with interest rates, recurring expense tracker, monthly burn & cash runway |
| **Family** | Side-by-side comparison across all members with stacked bar chart |
| **History** | Snapshots over time with a net worth line chart |

---

## Features

- **Multi-member** — track each family member separately (spouse, children's education funds)
- **Live prices** — auto-refreshes via Yahoo Finance → Stooq → Finnhub fallback chain
- **CPF & SRS** — OA, SA, MA, and SRS balances, correctly separated from investable assets
- **FIRE calculator** — two scenarios, two safe withdrawal rates, honest liquid-only numbers
- **Property** — primary home is excluded from FIRE calcs (you can't retire into your house)
- **AI analysis** — generates a full portfolio prompt to paste into Claude or ChatGPT, or connects directly via your Anthropic API key
- **Export / Import** — full JSON backup with schema versioning
- **Onboarding wizard** — 5-step guide on first load, re-accessible via Help & Guide
- **Private by design** — all data stored in `localStorage` with prefix `fwt_clean_`, nothing sent anywhere

---

## Getting started

1. Open [portfomily.netlify.app](https://portfomily.netlify.app/) **or** download `docs/FamilyWealthTracker.html` and open it in any browser
2. Complete the onboarding wizard (or skip it)
3. Add a family member → set CPF balances, cash, and FIRE goal
4. Add holdings — ticker symbols follow Yahoo Finance convention:
   - SGX: `D05.SI` (DBS), `C38U.SI` (CICT REIT)
   - US: `VOO`, `AAPL`
   - Other markets: `0700.HK` (Tencent), `VWRL.L` (Vanguard FTSE All-World LSE)

---

## Self-hosting

It's a single HTML file with no build step. Just serve it statically:

```bash
# Python
python3 -m http.server 8080

# Node
npx serve .
```

Or drag `docs/FamilyWealthTracker.html` straight into your browser.

---

## Tech stack

| | |
|---|---|
| **Runtime** | Vanilla JS, single HTML file, no build tools |
| **Charts** | [Chart.js 4.4.0](https://www.chartjs.org/) (CDN) |
| **Fonts** | Playfair Display · IBM Plex Sans · IBM Plex Mono (Google Fonts CDN) |
| **Prices** | Yahoo Finance v8 API → Stooq CSV → Finnhub (via CORS proxies) |
| **AI** | Anthropic Claude API (`claude-sonnet-4-20250514`) — optional, key stored locally |
| **Storage** | `localStorage` keys prefixed `fwt_clean_` |

---

## Version

**v1.0.1** · Built in Singapore · [MIT License](LICENSE)
