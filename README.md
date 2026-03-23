# Guideware-Hackaton
# 🛵 GigShield — Automated Parametric Insurance for Quick Commerce Delivery Workers

> **Guidewire DEVTrails 2026 | Phase 1 Submission**  
> Platform: Web App | Stack: React + Node.js | Persona: Zepto / Blinkit Delivery Partners

---

## 📌 Problem Statement

India's quick commerce delivery partners (Zepto, Blinkit, Swiggy Instamart, etc.) operate under extreme time pressure — promising 10-minute deliveries in all conditions. Yet when external disruptions hit — heavy rain, extreme heat, dense fog, or sudden local curfews — these workers are forced off the road and lose 20–30% of their weekly earnings with zero safety net.

Unlike salaried workers, gig workers have no employer-backed income protection. When disruptions occur, they absorb 100% of the financial loss. **GigShield** exists to change that.

---

## 👤 Persona: The Quick Commerce Delivery Partner

**Meet Ramesh, 27, Blinkit delivery partner, Delhi NCR**

- Works 10–12 hours/day, 6 days/week
- Earns ₹12,000–₹18,000/month (paid weekly)
- Rides a 2-wheeler through rain, smog, and traffic
- Has no insurance beyond basic vehicle coverage
- Loses 2–4 working days per month due to weather/environmental disruptions

**Key Disruptions for Quick Commerce Persona:**

| Disruption Type | Specific Examples | Income Impact |
|---|---|---|
| Environmental | Extreme heat (>42°C), Heavy rain (>50mm/hr) | Cannot ride safely; deliveries halted |
| Air Quality | AQI > 400 (severe smog) | Health risk forces work stoppage |
| Civic | Unplanned local curfews or zone lockdowns | Cannot access pickup/drop locations |

> **Coverage Scope:** GigShield insures INCOME LOST during these events — not vehicle repair, health, or accidents.

---

## 💡 Solution: GigShield

**GigShield** is an automated parametric insurance web platform that:

- Monitors disruption events using simple external APIs (Weather, AQI)
- Triggers payouts **without the worker needing to file a claim**
- Prices coverage on a **weekly model** aligned to gig worker earnings cycles
- Uses simple rule-based algorithms to validate claims and prevent fraud

### How It Works (Core Flow)

```
Worker Enrolls → Selects Weekly Plan → Disruption Event Occurs
      ↓
GigShield Monitors (Weather API + AQI API) continuously
      ↓
Parametric Trigger Fired (e.g., AQI > 400 for 4+ hours in worker's zone)
      ↓
Rule-based Validation (checks location + duplicate claims)
      ↓
Status updated to "Approved", Mock Payout credited to Wallet
```

---

## 💰 Weekly Premium & Payout Model

### Why Weekly?

Gig workers are paid weekly by platforms. A weekly insurance model matches their cash flow — they pay from what they earn, not from savings.

### Pricing Tiers (Weekly)

| Plan | Weekly Premium | Max Weekly Payout | Coverage |
|---|---|---|---|
| Basic Shield | ₹25/week | ₹500 | Environmental disruptions only |
| Pro Shield | ₹49/week | ₹1,200 | Environmental + AQI + Civic |

### Parametric Trigger Thresholds

| Parameter | Trigger Condition | Data Source |
|---|---|---|
| Rainfall | > 50mm in 3 hours | OpenWeatherMap API |
| Temperature | > 43°C for 4+ hours | OpenWeatherMap API |
| AQI | > 400 (Severe category) | AQI India API (or any free AQI API) |

---

## ⚙️ Smart Rules & Validation (Simplified)

Instead of complex AI/ML models, GigShield relies on easy-to-understand **Rule-Based Algorithms** to keep the platform fast and easy to build.

### 1. Simple Risk Pricing
- Base premium is standard.
- **Rule:** If the user selects a traditionally high-risk zone (e.g., high flood zone), add a flat ₹10 to the premium. 

### 2. Basic Fraud Prevention
- **One Claim Per Day:** A worker can only receive one payout per 24 hours.
- **Pincode Matching:** Disruption must happen in the user's saved Pincode.
- **Maximum Weekly Cap:** Payouts stop once the plan's maximum weekly coverage limit is reached.

---

## 🏗️ Tech Stack & Architecture

We are using a beginner-friendly MERN stack (MongoDB, Express, React, Node).

### Frontend
- **React.js** — Worker dashboard, plan selection, coverage status.
- **Tailwind CSS / Standard CSS** — For building a clean, responsive mobile-first UI.

### Backend
- **Node.js + Express** — Simple REST API for handling users and triggers.
- **MongoDB (via Mongoose)** — Easy-to-use NoSQL database to store User Profiles, Active Policies, and Payout Records.

### Integrations (Free/Easy Tools)
- **OpenWeatherMap API** (free tier) — To check rainfall and temperature.
- **WAQI API** (free tier) — To check Air Quality Index.
- **Mock Payments** — Instead of Razorpay, we will simulate a "Wallet" balance for the hackathon demo.

### Infrastructure
- **Vercel / Netlify** — Frontend deployment (Drag and drop or GitHub sync).
- **Render** — Backend deployment (Easy free tier).

---

## 🗂️ Application Workflow

### Worker Journey

```
1. ONBOARDING
   → Worker registers with name, phone number, and home pincode.
   → Selects average weekly earnings.

2. PLAN SELECTION
   → Views weekly plans (Basic / Pro)
   → Simulates payment (adds active policy to their account)

3. ACTIVE COVERAGE & DASHBOARD
   → Dashboard shows: active policy, wallet balance, and current weather/AQI in their zone.

4. AUTOMATIC CLAIM (Demo Mode)
   → Admin or User can click a "Simulate Bad Weather" button for the demo.
   → System checks rules (Is policy active? Has a claim been made today?)
   → Wallet balance increases automatically.
```

---

## 📁 Repository Structure

```
gigshield/
├── frontend/                  # React.js web app
│   ├── src/
│   │   ├── pages/             # Login, Dashboard, Plans
│   │   ├── components/        # Cards, Navbar, Modals
│   │   └── App.js             # Main routing
├── backend/                   # Node.js + Express API
│   ├── index.js               # Main server entry point
│   ├── routes/                # authRoutes.js, claimRoutes.js
│   ├── models/                # User.js, Policy.js, Claim.js (Mongoose)
│   └── controllers/           # Logic for handling triggers
└── README.md
```

---

## 🗓️ Development Plan

### Phase 1 — UI & Setup 
- [ ] Initialize React frontend and Node backend.
- [ ] Build basic UI pages (Login, Dashboard, Select Plan).
- [ ] Setup MongoDB connection.

### Phase 2 — Core Functionality
- [ ] User registration and login (JWT or simple sessions).
- [ ] Mock a payment and save user's policy choice to database.
- [ ] Build the Dashboard showing real-time weather using OpenWeather API.

### Phase 3 — The Claim Engine (Hackathon Demo)
- [ ] Build a "Simulate Disruption" button for the demo.
- [ ] Create a backend function that validates the rules and updates the user's wallet balance.
- [ ] Show payout history on the dashboard.

---

## 👥 Team STACKSTORM

> Divita Rajawat
> Khushi Srivastva
> Aditya Rai

---

*Built for Guidewire DEVTrails 2026 — Smart Insurance for India's Gig Economy*
