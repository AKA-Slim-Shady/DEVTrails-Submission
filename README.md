# Safety SIP: AI-Powered Parametric Income Protection

Safety SIP (Systemic Insurance Plan) is a next-generation financial safety net designed specifically for India’s platform-based delivery partners. Moving away from traditional high-premium insurance, this model utilizes a "Micro-Contribution" approach to safeguard gig workers against income loss caused by external disruptions such as extreme weather, pollution, and socio-political events.

---

## Table of Contents
1. [Core Assumptions](#1-core-assumptions)
2. [The Premium Model: Mathematical Framework](#2-the-premium-model-mathematical-framework)
3. [User Onboarding Workflow](#3-user-onboarding-workflow)
4. [Parametric Disruption Triggers](#4-parametric-disruption-triggers)
5. [Anti-Gaming and Loyalty Logic](#5-anti-gaming-and-loyalty-logic)
6. [Technical Architecture Overview](#6-technical-architecture-overview)

---

## 1. Core Assumptions
To ensure the viability of the Safety SIP startup model, the following baseline assumptions have been established:
* **Persona Focus:** Active delivery partners on platforms like Swiggy, Zomato, and Zepto.
* **Earnings Baseline:** Average gross weekly earnings of ₹4,000 to ₹8,000 in urban centers.
* **Participation Goal:** 50% enrollment among active drivers in Tier-1 urban hubs (Chennai, Bangalore, Mumbai, etc.).
* **Operational Mode:** Parametric-only. Payouts are triggered by verifiable external data (weather/government alerts) rather than individual damage assessments.
* **Exclusions:** This model strictly excludes health, life, accident, or vehicle repair coverage. It is an income-replacement product only.

---

## 2. The Premium Model: Mathematical Framework
The weekly premium (P) is dynamically calculated based on the worker’s earnings and specific risk profile variables.

### The Formula
$$P = [B \times W_{loc} \times W_{risk}] \times (1 - L)$$

### Variable Definitions
* **Base Rate (B):** Determined by the worker's weekly earnings as identified via the Account Aggregator (AA) framework.
    * Bracket 1 (₹1,000 – ₹5,000 earnings): B = ₹100
    * Bracket 2 (₹5,000 – ₹10,000 earnings): B = ₹200
    * Bracket 3 (₹10,000+ earnings): B = ₹300
* **Location Weight (W_loc):**
    * Urban Hubs (High Density/Risk): 1.5
    * Semi-Urban/Tier-2 Hubs: 1.0
* **Risk Profile (W_risk):** A multiplier (0.8 to 1.2) adjusted by AI based on vehicle type (EV vs. Petrol) and historical safety of the worker's primary operating zone.
* **Loyalty Discount (L):** A factor ranging from 0.0 to 0.3. For every 4 weeks of consecutive active status, a 0.05 discount is applied (capped at 30%).

---

## 3. User Onboarding Workflow
The onboarding process is designed to be "Zero-Touch," taking less than 60 seconds by leveraging existing Indian financial infrastructure.

1. **Identity Verification:** Secure OTP login linked to the driver’s bank-registered mobile number.
2. **Persona Profiling:** Worker selects their primary platform (e.g., Swiggy) and vehicle details.
3. **Account Aggregator (AA) Integration:** The user grants time-bound, read-only consent to the AA framework. This allows the system to auto-detect "Payout" strings from platforms to verify earnings.
4. **UPI Autopay Mandate:** User approves a recurring weekly mandate. The system only pulls the exact calculated premium based on that week's earnings.
5. **Activation:** Policy becomes active following the mandatory 30-day "Vesting Period."

---

## 4. Parametric Disruption Triggers
Payouts are automated based on "Oracles" (verified third-party data). A payout of ₹500/day is triggered when:
* **Environmental:** IMD declares a "Red Alert" or rainfall exceeds 50mm in a 24-hour window.
* **Heatwave:** Wet Bulb Temperature or Heat Index exceeds 44°C for more than 3 consecutive hours.
* **Socio-Political:** Government-mandated school/market closures or district-wide curfews are announced.

---

## 5. Anti-Gaming and Loyalty Logic
To prevent "Seasonal Gaming" (workers joining only during monsoons), the following safeguards are in place:
* **Vesting Period:** New users must contribute for 30 days before becoming eligible for payouts.
* **Cooldown Period:** Following a claim, a 15-day cooldown is applied before the next claim can be triggered.
* **Chain of Disruption:** Payouts for consecutive days (e.g., 3 days of flooding) are treated as a single event; the Loyalty Score does not reset during the chain.
* **Loyalty Reset:** The Loyalty Score (L) resets only after the successful conclusion of a disruption chain and a return to "Normal" status.

---

## 6. Technical Architecture Overview
* **Data Layer:** RBI-regulated Account Aggregator (AA) APIs for earnings verification.
* **Risk Layer:** AI/ML predictive models hosted on Google Cloud (GCP) for hyper-local weather risk scoring.
* **Settlement Layer:** NPCI e-Mandate and UPI 2.0 for automated premium collection and instant claim disbursements.
* **Fraud Engine:** Cross-referencing "Connectivity Signatures" (ensuring the worker was actually in the city during the disruption) with official weather alerts.
