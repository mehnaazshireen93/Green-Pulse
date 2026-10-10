# GreenPulse 🌱 — Campus Climate Impact & Sustainability Dashboard

> **"Measure. Improve. Sustain."**  
> Developed for **PSCMR Smart Internal Hackathon 2026** (Problem Statement 9: Climate Impact & Sustainability Dashboard).

---

## 📌 Project Overview
**GreenPulse** is a clean, modern, responsive Climate Impact & Sustainability Dashboard tailored for universities, engineering colleges, and institutional campuses. It transforms siloed utility records (electricity bills, water consumption, waste logs, and commute surveys) into verified sustainability intelligence.

### Key Capabilities:
1. **0–100 Sustainability Score**: Transparent, 5-pillar weighted rating with per-capita normalization and adjustable slider weights.
2. **5 Monitored Areas**: Energy (kWh), Water (kL), Waste (kg), Green Commute (%), and Carbon (tCO₂e) with data-confidence completeness badges.
3. **Automated Anomaly Detection**: Statistical Z-score outlier detection identifying real-world campus issues (e.g., Block C night-time water leaks, Library HVAC off-hours over-runs).
4. **Predictive & Prescriptive Analytics**: 90-day linear regression carbon forecast (dashed line) and Top 5 recommendations ranked by monthly ₹ savings, tCO₂e avoided, and payback period.
5. **Interactive What-If Simulator**: Live simulation sliders (Rooftop Solar kW, % EV shuttle buses, Composting %, AC thermostat setpoint) updating ₹ savings and emissions in real time.
6. **Smart Data Ingestion**:
   - Client-side OCR Bill Scanner (PDF/Images) with side-by-side **Verification & Correction Modal** prior to committing data.
   - Robust RFC-4180 CSV Parser (supports commas inside quoted strings, multi-line values).
   - Manual entry form that recalculates all dashboard metrics instantly.
7. **Audit-Ready Reports**: Client-side branded PDF report generator pulling active verified data for NAAC, NIRF, and ESG compliance.
8. **Hackathon Pitch Deck**: Built-in 12-slide interactive presentation with speaker notes and judge Q&A preparation (`pitch-presentation.html`).

---

## 🚀 How to Run Locally (Windows & VS Code)

GreenPulse is built as a zero-overhead, pure web application. **No Node.js, backend server, or database installation is required.**

### Option 1: Direct Browser Launch (Simplest)
1. Open Windows File Explorer.
2. Navigate to: `C:\Users\XPS\.gemini\antigravity\scratch\greenpulse`
3. Double-click `index.html` to open it in Google Chrome, Microsoft Edge, or Mozilla Firefox.

### Option 2: VS Code Live Server (Recommended for Development)
1. Open VS Code.
2. Go to **File → Open Folder...** and select `C:\Users\XPS\.gemini\antigravity\scratch\greenpulse`.
3. If not already installed, install the **Live Server** extension (by Ritwick Dey).
4. Right-click `index.html` and click **"Open with Live Server"**.
5. The dashboard will launch at `http://127.0.0.1:5500/index.html`.

---

## 🧪 Testing Checklist & Verification Guide

Follow these steps to verify all features:

| Test Case | Steps to Execute | Expected Outcome |
| :--- | :--- | :--- |
| **1. Initial Dashboard Load** | Open `index.html` in browser. | Score gauge shows 82 (Grade A). 5 KPI cards render sparklines and confidence tags. No console errors. |
| **2. Role Switcher** | In topbar, change Role to "Student". | Data input and Settings tabs are hidden for students. Switching back to "Administrator" restores full access. |
| **3. Pillar Weight Sliders** | Go to **Score Breakdown** page. Move Energy slider from 30% to 50%. | Overall score recomputes instantly in real time. |
| **4. What-If Simulator** | Go to **What-If Simulator**. Move Solar slider to 250 kW and AC to 26°C. | Projected CO₂ avoided, ₹ savings, and score update live. |
| **5. Anomaly Detection** | Observe the Alerts panel on Dashboard. | Displays Block C night leak (₹14,200/mo) and Library off-hours HVAC spike. |
| **6. CSV Upload** | Go to **Data Input**, click "Choose CSV", select `data/sample-electricity.csv`. | Status updates, data imports, and dashboard switches to "User Data Verified" banner. |
| **7. Manual Reading Entry** | On **Data Input**, fill manual form (e.g., 9500 kWh, ₹76,000) and click Save. | Record appears in Active Repository table and dashboard recalculates immediately. |
| **8. Bill OCR Scanner** | In Bill Scanner, upload any bill image or click Scan. | OCR executes; **Verification Modal** pops up allowing user review before committing. |
| **9. PDF Report Export** | Click **"⬇ Export PDF"** in topbar or Reports page. | Clean, branded `GreenPulse-Audit-Report.pdf` downloads containing live active data. |
| **10. Dark Mode Toggle** | Click Dark Mode in sidebar bottom. | Whole UI switches to dark theme; all Chart.js axes adapt their text and grid colors. |
| **11. Mobile Responsiveness** | Press `F12` and switch to 375px mobile device view. | Sidebar collapses to hamburger menu; cards stack into clean single column. |
| **12. Pitch Deck** | Click "📑 Pitch Deck" in topbar or open `pitch-presentation.html`. | 12 full slides with speaker notes and judge Q&A prep viewable and printable. |

---

## 🔬 Scientific Methodology & Emission Factors

All greenhouse gas calculations strictly follow verified standards:

| Emission Source | Factor Value | Official Source Reference |
| :--- | :--- | :--- |
| **Grid Electricity** | **0.820 kg CO₂e / kWh** | Central Electricity Authority (CEA), Ministry of Power, Govt. of India (Baseline Database v19.0) |
| **Diesel Fuel** | **2.680 kg CO₂e / Litre** | IPCC 2006 Guidelines for National GHG Inventories |
| **Commercial LPG** | **2.980 kg CO₂e / kg** | IPCC Stationary Combustion Standards |
| **Municipal Water Pumping** | **0.340 kg CO₂e / kL** | National Pumping Energy & Water Treatment Standard |
| **Solid Waste Landfill** | **1.250 kg CO₂e / kg** | Central Pollution Control Board (CPCB) Methane Generation Model |

---

## 📁 Repository Directory Structure

```
greenpulse/
├── index.html                   # 11 Semantic views, accessible modals, responsive SaaS layout
├── style.css                    # Design system: Deep green (#166534), teal accents, dark mode
├── script.js                    # Pure JS business logic, engines, CSV parser, Chart.js managers
├── pitch-presentation.html      # 12-Slide Hackathon Pitch Deck with speaker notes & Q&A
├── README.md                    # Installation, testing checklist, methodology
└── data/
    ├── sample-electricity.csv   # 12-Month campus electricity records (with summer & exam peaks)
    ├── sample-water.csv         # 12-Month campus water records (with Block C leak anomaly)
    ├── sample-emissions.csv     # Scope 1, 2, and 3 activity records with CEA factors
    ├── sample-sensors.csv       # IoT telemetry smart meter & temperature logs
    └── sample-transport.csv     # Campus modal commute survey & shuttle fleet records
```

---

## 🏆 Hackathon Alignment (Problem Statement 9)
- **Zero Hallucinations:** Recommendations and conclusions derive exclusively from parsed mathematical structures.
- **Actionable ROI:** Focuses on monthly ₹ savings and payback periods rather than abstract platitudes.
- **Zero-Hardware Barrier:** Ingests standard paper utility bills via assisted OCR without requiring expensive smart meters.
