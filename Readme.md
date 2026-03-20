# GigCrest
GigCrest — Smart Protection for the Modern Hustle. As income protection insurance for food delivery partners, GigCrest aims to provide financial protection to food delivery gig workers (like Zomato, Swiggy, and many more) against income loss due to circumstances beyond their control.

## 1. Project Overview
GigCrest is a parametric insurance platform built specifically for gig economy workers (delivery
partners, ride-hailing drivers, etc.). Unlike traditional insurance, it eliminates manual claim filing by
automatically detecting real-world disruptions (extreme rain, heatwaves, high pollution, strong
winds), calculating fair compensation using AI, and instantly disbursing payouts.

## 2. Core Workflow
| Step | Process | Description|
|-------|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| 1 | Worker | Onboarding Registration, login, and submission of location, earnings, and work details.|
| 2 | Policy Purchase | AI calculates a dynamic premium. Worker purchases a weekly policy; coverage activates instantly. |
| 3 | Continuous Monitoring | Event engine polls weather & environmental APIs in real-time against predefined thresholds. |
| 4 | Event Detection | When thresholds are breached, a disruption event is created and assigned a severity tier (T1–T4). |
| 5 | Auto Claim Generation | System identifies affected workers, calculates payouts, runs fraud checks, and assigns status: Auto-Approved, Manual Review, or Denied. |
| 6 | Instant Payout | Approved claims trigger automatic mock UPI transfers to the worker’s account. |
| 7 | Admin Monitoring | Live dashboard updates with events, claims, financial metrics, and fraud alerts. |
| 8 | Simulation (Demo) | Admins can simulate disruptions by zone/type/severity to test claim generation, payouts, and fraud scoring. |

## 3. System Architecture & Technology Stack

### ◆ Frontend Layer

| Component | Tech Stack | Purpose |
|-----------|-----------|---------|
| Worker App | React.js, Tailwind CSS, Axios | Mobile-first UI for registration, dashboard, policy purchase, claims history, and profile management. |
| Admin Dashboard | React.js, Chart.js, Leaflet.js | Desktop-first interface for platform stats, event monitoring, fraud alerts, claim approvals, and interactive risk mapping. |

### ◆ Backend & Core Services

| Component | Tech Stack | Purpose |
|-----------|-----------|---------|
| API & Business Logic | Node.js, Express.js | RESTful APIs, authentication, data aggregation, and cross-module coordination. |
| Real-Time Communication | Socket.IO | Live updates for event detection, claim status changes, and admin dashboard sync. |
| Database | MongoDB (JSON/BSON) | Stores workers, zones, policies, claims, events, weather logs, payments, and fraud alerts. |

### ◆ AI / ML Engine (Python)

| Module | Libraries | Function |
|--------|-----------|----------|
| Premium Pricing | Scikit-learn, Pandas, NumPy | Dynamic pricing based on zone risk, seasonality, worker profile, and behavior. |
| Payout Calculation | Pandas, NumPy | Computes compensation using income data, disruption severity, duration, and policy limits. |
| Fraud Detection | Scikit-learn | Multi-layer risk scoring (0–100), pattern validation, and alert generation for suspicious claims. |

### ◆ External Data Sources

| API | Data Provided |
|-----|--------------|
| OpenWeather API | Rainfall, temperature, wind speed |
| AQICN API | Real-time Air Quality Index (AQI) |

### ◆ Security & Authentication

- JWT for secure session management
- bcrypt for password hashing & encryption
- Role-based access control (Worker vs. Admin)

---

## 4. Key Features & Innovations

| Feature | Description |
|---------|-------------|
| Parametric Insurance | Trigger-based payouts with zero manual claim filing. Faster, transparent, and frictionless. |
| Real-Time Event Detection | Continuous monitoring of weather & environmental conditions with automatic system response. |
| AI-Driven Decisions | Smart premium pricing, dynamic payout calculation, and automated fraud prevention. |
| Multi-Layer Fraud Detection | Risk scoring (0–100), behavioral validation, and real-time admin alerts for suspicious activity. |
| Zone-Based Risk Model | City divided into micro-zones; risk levels vary by location, directly impacting pricing & payouts. |
| Interactive Risk Map | Visual dashboard showing active zones, risk tiers, and live disruptions using Leaflet.js. |
| Income Protection Tracking | Tracks lost income vs. recovered income via payouts, displaying overall protection percentage. |

---

## 5. Design Principles

| Layer | Guiding Principles |
|-------|-------------------|
| Worker App | Mobile-first, minimal text, clear CTAs, fast interactions, accessible UI for low-literacy users. |
| Admin Dashboard | Desktop-first, data-dense layout, real-time analytics, visual charts & maps, actionable insights. |
| System Architecture | Modular, API-driven, loosely coupled components, scalable microservice-ready design. |

---

## 6. Data Flow Summary

Worker → Backend → AI Engine → Policy Created
Weather/Env Data → Event Engine → Disruption Detected
Event → AI Engine → Payout Calculation + Fraud Check
→ Claims Generated → Payments Processed (Mock UPI)
→ Admin Dashboard & Worker App Updated (Socket.IO)


---

## 7. Deployment & Infrastructure

| Component | Hosting / Tool |
|-----------|---------------|
| Frontend | Vercel / Netlify |
| Backend & APIs | Render / AWS / DigitalOcean |
| Database | MongoDB Atlas |
| Version Control | GitHub |
| Containerization (Optional) | Docker for consistent dev/prod environments |
| Caching & Pub/Sub (Optional) | Redis for real-time event buffering & rate limiting |

---

## 8. Future Enhancements (Roadmap)

- Integration with real payment gateways (Razorpay, Stripe, UPI Autopay)
- On-device lightweight ML for offline disruption detection
- Dynamic policy tiers (daily, weekly, monthly)
- Partner integrations (Zomato, Swiggy, Uber, Rapido) for automated earnings verification
- SMS/WhatsApp fallback notifications for low-connectivity areas

## Adversarial 
