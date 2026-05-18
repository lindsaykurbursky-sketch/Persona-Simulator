# Aristocrat Technologies – Product Knowledge Repository

> Source documents: `/Users/lk109266/Desktop/Productdocumentation/`
> Use this file as context when designing, prototyping, or discussing Aristocrat casino management software.

---

## 1. Product Ecosystem Overview

Aristocrat Technologies (ATI / ATA) builds a suite of casino management software products that work together across the casino floor, back-office, and player-facing channels.

| Product | Layer | Purpose |
|---|---|---|
| **Oasis 360+** | Back-office / CMS | Core Casino Management System — player records, gaming & non-gaming transactions |
| **ONE LINK** | Floor network | Campaign management & content delivery to EGMs |
| **nCompass** | EGM device | In-machine player interface device; connects EGMs to Oasis & ONE LINK |
| **Oasis Loyalty** | Loyalty engine | Rewards rule management within the Oasis suite |
| **Kiosk Manager** | Kiosk / promotions | Promotion management platform for casino kiosks |
| **PlayerMax (MAM)** | Mobile app | Player-facing mobile app; operators manage via Mobile Application Manager |
| **Drinks on Tap** | Floor service | Beverage ordering and service management on the casino floor |

---

## 2. ONE LINK (v15.2)

**What it is:** Campaign and content delivery platform that pushes media, promotions, and configurations to nCompass devices installed in EGMs across the casino floor.

**Primary driver of v15.2:** Integration of SMA (Slot Machine Accounting) Functionality.

### Compatibility Matrix
| System | Supported Versions |
|---|---|
| Oasis Suite | 12.11.6xxx, 12.14.1xxx, 15.2 |
| Loyalty | 1.3, 1.4, 2.1, 15.2 |
| nCompass Linux | 15.0.3.1 / 15.0.4.x (limited), 15.2 |
| **Not supported** | nCompass Media Window (MW), nCompass Linux on Lite (LoL) |

### Key Feature Modules
- **Announcements & Totalizer** — Floor-wide jackpot and event announcements
- **Media Only Mode** — Run media content independently of other ONE LINK features
- **SpeedMedia Integration** — High-speed media delivery to EGMs
- **Campaign Management** — Schedule and push targeted promotions
- **Skinning** — Customise the visual theme of nCompass screens
- **SpeedMedia Promotions / SpeedGames** — Promotion delivery via SpeedMedia
- **Play X Get Y (PxGy) Bonusing** — Trigger-based bonus promotions
  - Configure Bonus Levels, Bonus Machine Groups, Budget Levels
  - Add Multiple Minors (payment method, award type/amount, criteria)
  - Set odometer colors via ProgressOdometer > ProgressBar settings
  - Scheduling must start at 12:00 AM
- **Firmware & Config Management** — Push firmware updates and config files to devices
- **Custom Card Reader Bezels** — Property-specific card reader bezel configurations

---

## 3. nCompass (v15.2)

**What it is:** A physical device inserted into EGMs that serves as the player interface. It collects EGM data and transmits it to the Oasis 360 network via FloorLogix™. It is also the content delivery mechanism for ONE LINK and third-party player-targeted media.

### Key Player-Facing Features (Player Buttons)
| Feature | Description |
|---|---|
| **Account Button** | Player accesses their casino account from the EGM |
| **Call Attendant** | Player calls a floor attendant; new in v15.2 |
| **PersonalBanker** | Cash management — transfer funds to/from the game |
| **PIN** | Player PIN authentication |
| **Rewards** | View and interact with loyalty rewards |
| **Transfer To Game** | Move cash funds into the EGM |
| **Transfer From Game** | Cash out from the EGM |
| **Bill Stuffing** | Voucher-Out trigger logic |
| **nCompass LCD** | 6.2" LCD display; front/back/top view hardware specs |

### Bonus & Promotion Display
- Criteria Trigger Bonus Level (new in v15.2)
- Progress Odometer with customizable bar colors and celebration screens
- Mass Marketing screens (Just Qualified, Congrats, Enter Phone, Create PIN)
- Promo Winner screen

### v15.2 / v15.2.1 Notable UI Enhancements
- Flat button design and theming improvements
- Easier background image/color customization
- CSS-based UI elements for faster load times
- Auto-resizing bonus name and prize description text
- New extensible settings: `OneLinkGameZero`, `Display Progressive Award`, `RestartUIAfterDropAfterXDays`, `RestartUIDailyTime`

### Integration Points
- Oasis 360 → FloorLogix™ (data transmission)
- ONE LINK (campaign and media delivery)
- Oasis Loyalty (rewards display)
- Room Charge, After-Tax Adjustment, UTJ (Universal Transaction Jack)

---

## 4. Oasis Loyalty (v2.1) – Manage Rewards Rule

**What it is:** The loyalty management module within the Oasis suite. Enables casino operators to define and manage reward rules for player loyalty programs.

**Document:** Oasis Loyalty™ v2.1 Manage Rewards Rule (July 2023, doc# 20-01502-00)

### Key Concepts
- **Rewards Rules** — Logic that determines how players earn and receive loyalty rewards
- Integrated with the broader Oasis 360 CMS and nCompass player interface
- Rewards rules can be configured for specific player tiers, behaviors, or events

---

## 5. Kiosk Manager (2026)

**What it is:** A web-based promotion management system that operators use to configure and run casino kiosk promotions. Connects to ONE LINK for media delivery.

### Promotion Types
| Type | How It Works |
|---|---|
| **Drawing Promotions** | Players earn entries; drawings held at events; winners selected from submissions |
| **Earn and Get** | Players earn points/actions to qualify for rewards |
| **Swipe and Win** | Player swipes card at kiosk for instant win |
| **Bonus Promotions** | Configured reward periods with earning schedules and available rewards |
| **Pick and Win** | Weekly game schedule; players pick for cash or non-cash rewards |
| **Interactive Game Promotions** | Branded interactive game with win levels and creative assets |
| **Static Promotions** | Non-interactive promotional displays |

### Key Functional Areas
- **Inventory** — Manage rewards and reward kits (create, edit, track redemptions)
- **Templates** — Voucher template creation and management
- **Players Menu** — Player lookup, eligible promotions, submission details, vouchers, ratings
- **Quickscan** — Quick voucher redemption at kiosk
- **Kiosks** — Add/manage kiosk hardware and printers
- **Reporting** — Kiosk reports, account user activity, report builder, player rating downloads
- **Users & Roles** — Create users, assign roles, clone roles
- **Settings** — Property, kiosk interface options, PIN pad, creative elements, win/loss reports, mail server, ONE LINK integration, hotel availability

### ONE LINK / Kiosk Integration
- Kiosk channel integrates with ONE LINK via Appendix A settings
- ONE LINK Program Setup → ONE LINK Channel Setup → Mediasign Setup

---

## 6. PlayerMax (v24.0) – Mobile Application Manager (MAM)

**What it is:** The operator-facing admin tool for managing the PlayerMax™ player mobile app. MAM connects to the Casino Management System (CMS) for player records, gaming/non-gaming transactions, and campaign promotions.

### MAM Interface Tabs
| Tab | Purpose |
|---|---|
| **Branding** | Customize app sign-in/sign-up text, splash screen, start screen assets per property/tier |
| **Content** | Configure menu icons, menu items, descriptions, and images for dining, events, promotions |
| **Engagement** | Primary landing page for operators; player engagement campaign tools |
| **Reports** | Analytics and reporting |
| **Settings** | App-wide configuration |

### Key Concepts
- Operators must be in the **PlayerMax™ group** in Active Directory to access MAM
- App Preview available in MAM to see live player-facing view
- Customization is scoped to property, member, or tier level
- Site name is required on first login (stored per device/browser)

---

## 7. Drinks on Tap (v24.0)

**What it is:** A casino floor beverage management system within the Oasis 360+ suite. Enables players to order drinks from their EGM slot machine; operators manage drink service workflows.

**Document:** Drinks on Tap™ v24.0 User Guide (March 2024, doc# 20-01551-01)

- **v24.0** initial release: 08 March 2024
- **v24.0 patch**: Active toggle update (12 March 2024)

---

## 8. Personas

These personas represent the UX team's standard reference characters for casino operator and player user testing. Used in the **Casino Persona Simulator** tool.

### Operator Personas

| Name | Role | Type | Location | Key Tools |
|---|---|---|---|---|
| **Maya Maeda** | Loyalty Manager | Proto | — | Oasis Loyalty, CMS |
| **Regina Rose** | Casino Host | Proto | — | CMS, player records |
| **Margie Moonstone** | Cage Manager | Hybrid | Oklahoma (age 51) | Reconciliation, cash management tools |
| **Tony Hayes** | Security Manager | Proto | Las Vegas, NV (age 52, 25 yrs exp) | Floor Logix, Incident Tracker, Diagnostic Manager, Surveillance Monitor |
| **Jerry Buttowski** | Slot Manager | Hybrid | — | Slot management systems |
| **Maria Lopez** | Slot Attendant | Standard | Las Vegas, NV (age 37, 3+ yrs exp) | Jackpot Fill, Quickets, walkie-talkie (60% of use) |
| **Justin Kim** | Slot Technician | Hybrid | — | Diagnostic tools |
| **Reese Miller** | Casino Floor Supervisor | Proto | — | Floor monitoring |
| **Gertie Dubroski** | Player's Club Representative | Proto | — | Loyalty/player club systems |

### Persona Detail: Tony Hayes (Security Manager)
- **Needs:** 100% system uptime, rapid incident response, easy incident reporting, predictive alerts, efficient team comms, detailed surveillance access
- **Pain points:** Communication breakdown during high traffic, slow incident report generation, multiple systems with inconsistent UI, delayed threat notifications, unpredictable shift schedules
- **Motivations:** Patron/staff safety, prevention, security excellence, tech adoption, team engagement
- **Device split:** Radio 45%, Cellphone 35%, Windows Desktop 20%
- **Tools:** Incident Tracker, Diagnostic Monitor, Floor Logix, Excel, Access, Outlook, Surveillance Software, CAD

### Persona Detail: Maria Lopez (Slot Attendant)
- **Needs:** Fast hand pay response, player satisfaction, ticket paper restocking, cross-dept communication
- **Pain points:** Delays in machine refill/payout approval, limited visibility into machine issues, walkie-talkie clutter during peak hours, long floor shifts, unclear ownership of support tasks
- **Motivations:** Player happiness, response time, supervisor rapport, minimizing floor downtime
- **Device split:** Android phone 30%, Walkie Talkie 60%, Windows Desktop 10%
- **Keywords:** Hand pay, Refill, Ticket jam, Voucher, Paper out, "Call light on", "Reprinted ticket"

### Persona Detail: Margie Moonstone (Cage Manager, Hybrid)
- **Core activities:** Auditing cash drawers, running reconciliation reports, training cashiers, collaborating with security on suspicious transactions, monitoring surveillance during cash disputes, managing vault transfers, verifying bank deposits
- **Fears:** Audits by outside entities, employee turnover, not understanding new tech, being blamed for staff mistakes
- **Keywords:** Reconciliation, cash count discrepancies, variance report, customer dispute, transaction log, schedule compliance

---

## 9. Key Terminology Glossary

| Term | Definition |
|---|---|
| **EGM** | Electronic Gaming Machine (slot machine) |
| **CMS** | Casino Management System (Oasis 360) |
| **ONE LINK** | Aristocrat's campaign management & content delivery network for EGMs |
| **nCompass** | Physical device inserted into EGMs; player interface + data relay |
| **Oasis 360** | Aristocrat's core back-office CMS platform |
| **FloorLogix** | Program through which nCompass transmits data to the Oasis 360 network |
| **MAM** | Mobile Application Manager — operator tool for managing PlayerMax mobile app |
| **PlayerMax** | Aristocrat's player-facing mobile app |
| **PxGy** | Play X Get Y — a trigger-based bonus promotion type |
| **SMA** | Slot Machine Accounting |
| **SpeedMedia** | High-speed media delivery system for EGMs |
| **SpeedGames** | Games delivered via SpeedMedia promotions |
| **Hand Pay** | Manual jackpot payment made by casino staff |
| **Quickets** | Slot attendant tool for ticket/voucher management |
| **Jackpot Fill** | Process of refilling/processing jackpot payouts |
| **PersonalBanker** | nCompass feature for player cash management at the EGM |
| **Reward Kit** | Bundled reward package managed in Kiosk Manager |
| **Drawing** | Lottery-style promotion where players earn entries and winners are drawn |

---

## 10. Product Relationships Map

```
Oasis 360 (CMS — core player records, transactions)
  ├── Oasis Loyalty (reward rules engine)
  ├── Drinks on Tap (floor beverage service)
  └── Kiosk Manager (kiosk promotion management)
        └── ONE LINK (campaign & media delivery network)
              └── nCompass (in-EGM device — player interface)

PlayerMax (player mobile app)
  └── MAM (operator admin for PlayerMax)
        └── Connects to CMS (Oasis 360) for player data & promotions
```

---

## 11. Source Documents Index

| File | Product | Version | Date |
|---|---|---|---|
| `ITK - ONELINK 15.2 Overview v1.3.pdf` | ONE LINK | 15.2 | 2024 |
| `LoyaltyGuides.pdf` | Oasis Loyalty | 2.1 | July 2023 |
| `Oasis360+.pdf` | Drinks on Tap | 24.0 | March 2024 |
| `nVisionOnelinknCompass+More.pdf` | nCompass | 15.2 | 2024–2026 |
| `PlayerMax_MAM.pdf` | PlayerMax MAM | 24.0 | April 2024 |
| `avid.aristocrat.com…pdf` | Kiosk Manager | 2026 | 2026 |
| `Personas (All).pdf` | UX Personas | All | — |
| `BonusPoints User Guide.pdf` | BonusPoints | 15.2 | 2024 |
| `Marketing Manager User Guide.pdf` | Marketing Manager | 15.2 | 2024 |

---

## 12. BonusPoints™ (v15.2)

**What it is:** An Oasis 360 module that creates and schedules bonus points promotion events on the casino floor. Operators configure bonus events that award players extra points during defined time windows, targeting specific machines and player groups.

**Document:** BonusPoints™ User Guide (Oasis 360 v15.2, doc# 20-01558-00)

### Bonus Event Types
| Type | How It Works |
|---|---|
| **Frequency** | Awards a fixed point amount per qualifying trigger (e.g., 500 pts per $10 coin-in) |
| **Multiplier** | Multiplies the player's base point earn rate (e.g., 2x, 3x, up to 100x) |

### Key Concepts
- **Concurrent Events:** Up to 16 bonus events can be active simultaneously; points from all active events stack additively on top of base earn rate
- **Machine Groups:** EGMs must be grouped before events can be configured; groups are created by machine/location criteria (managed via BlackBart integration)
- **Player Targeting:** Events can be scoped to:
  - All players or specific interest groups
  - Date-based targeting: birthday, anniversary, enrollment date (±N days / week / month window)
- **Bonus Configuration Options:** Multiplier (integer, up to 100x) or Fixed Amount (per day / week / month / year caps)
- **Scheduling:** Events have defined start/end dates and times; multiple events can overlap

### Functional Areas
| Area | Purpose |
|---|---|
| **Machine Groups** | Define which EGMs participate in a bonus event |
| **Events** | Create, schedule, and activate bonus point promotions |
| **Reports** | Analyze event performance and player activity |

### Reports
- **Machine Criteria** — Which machines are in each group
- **Event Analysis** — Points awarded, player participation per event
- **Event Listing** — Summary of all configured events
- **Duplicate BonusPoints** — Flag players earning from duplicate triggers
- **Event Diagnostics** — Troubleshoot event configuration issues
- **Audit** — Full change log for compliance

### Integration Points
- **Administrator** — Access control for BonusPoints module
- **BlackBart** — Machine and location data for Machine Group setup
- **Super-PlayMate** — Player interest groups for targeted events
- **Oasis 360 CMS** — Core player earn/redemption ledger

---

## 13. Marketing Manager™ (v15.2)

**What it is:** An Oasis 360 module with two primary functions: **Coupon Management** (create and distribute promotional coupons to players) and **Event Monitoring** (track redemption activity in real time). Connects directly to player records and machine data.

**Document:** Marketing Manager™ User Guide (Oasis 360 v15.2, doc# 20-01566-00)

### Campaign Hierarchy
```
Campaign
  └── Offer / Event
        ├── Coupon Series   (Marketing coupons — redeemed at player's club or cage)
        └── Redemption Series (Slot coupons — inserted into EGM bill validator)
```

### Coupon Types
| Category | Subtype | Redemption Location | Notes |
|---|---|---|---|
| **Marketing** | Cash | Player's club / Cage | Redeemable for cash value |
| **Marketing** | Comp | Player's club / Cage | Comp credit (food, hotel, etc.) |
| **Marketing** | Prize | Player's club / Cage | Physical or non-cash prize |
| **Slot** | Voucher Promo | EGM bill validator | Cashable — adds to player's cashable balance |
| **Slot** | Coupon Promo | EGM bill validator | Promotional — non-cashable promo credit |

### Validation Numbers
| Prefix | Type | Used For |
|---|---|---|
| 5 | Unique | Marketing coupons |
| 6 | Unique | Marketing events |
| 9 | Unique | Slot coupons |
| 2 | Non-unique | Marketing coupons (reused across prints) |
| 8 | Non-unique | Marketing events |

### Implement (Finalize) Workflow — 4 Steps
1. **Select Players** — Query by interest group, tier, date criteria, or import list
2. **Reserve Validation Numbers** — System allocates unique or non-unique numbers
3. **Print** — Print coupon batch (physical or digital)
4. **Finalize** — Locks the print run; status moves to *Printed*

### Coupon Status Flow
```
Printed → Redeemed (final)
Printed → Expired → Redeemed (requires authority override)
Printed → Voided (final — cannot be redeemed)
```

### Redemption Methods
- **Find** — Look up by validation number or player ID
- **Rapid Redemption** — Fast single-scan workflow for high-volume redemption
- **Manual Event Redemption** — Staff-initiated redemption for walk-up events

### Import Formats
- Tab-delimited `.txt` — Standard player list import
- `.xml` (NYL) — New York Lottery integration format

### Key Functional Areas
| Area | Purpose |
|---|---|
| **Campaigns** | Create and organize marketing campaigns |
| **Offers / Events** | Define promotion rules, dates, and coupon series |
| **Coupon Series** | Configure Marketing coupon batches |
| **Redemption Series** | Configure Slot coupon batches |
| **Implement** | Run the 4-step finalize workflow to produce coupons |
| **Redemption** | Find, rapid-redeem, or manually redeem coupons |
| **Event Monitoring** | Real-time dashboard of redemption activity |
| **Reports** | Activity, Analysis (offer/event/GL), Exceptions, Status, Audit |

### Integration Points
- **ONE LINK / Play X Get Y** — PxGy bonus levels can trigger marketing offers
- **FreePlay / HotSeat** — NYL format campaigns for FreePlay and HotSeat promotions
- **Super-PlayMate** — Player database for targeting and group selection
- **BlackBart** — Machine data for slot coupon targeting
- **Oasis 360 CMS** — Player records, transaction ledger, comp balances
