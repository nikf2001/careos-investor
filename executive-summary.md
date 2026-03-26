---
layout: default
title: Executive Summary
nav_order: 3
---

# CareOS — Investor Memo: Executive Summary

**Prepared:** March 2026  
**Stage:** Pre-Seed  
**Ask:** 3–5M NOK  
**Contact:** Nikolai Fasting, Founder & CEO

---

## 1. The Opportunity in 60 Seconds

Norway faces an irreversible demographic shift: the 80+ population will more than double by 2040, from roughly 230,000 to over 500,000, while the healthcare workforce cannot grow proportionally. NOU 2023:4 ("Tid for satisfying") confirmed that the current staffing model is unsustainable. Municipal nursing homes spend 8–18M NOK per facility annually on temporary agency staff. Care workers waste 30–40% of their time on logistics, administration, and navigating fragmented IT systems that don't communicate with each other.

CareOS is the healthcare operations OS — a horizontal data platform, workflow engine, and AI decision support layer with pluggable connectors. We don't compete with VR training tools, scheduling software, or robotic logistics vendors. We connect them all into coordinated, intelligent operations. The result: fewer staff delivering safer care, because their tools finally work together.

We're raising 3–5M NOK to validate the platform through 3 municipal pilot deployments, prove measurable ROI, and build the engineering team. The Norwegian municipal care market represents 4–6B NOK in addressable operations spend — and nobody owns the OS layer.

---

## 2. Market Opportunity

### 2.1 The Demographic Wall

Norway's healthcare system is heading for a structural crisis that no amount of incremental improvement can solve. The statistics from SSB (Statistics Norway) and the government's own reports paint an unambiguous picture:

- **80+ population:** From ~230,000 (2024) to ~500,000+ by 2040 — a 117% increase
- **Healthcare worker shortage:** NOU 2023:4 projects a deficit of 28,000 healthcare workers by 2035 under current models
- **Dependency ratio:** The ratio of working-age adults (20–66) to elderly (80+) will fall from approximately 10:1 today to roughly 5:1 by 2040
- **Municipal burden:** Healthcare already consumes 30–40% of municipal budgets, and costs are rising faster than tax revenues

The government's response has been a mix of technology mandates, municipal reform, and workforce planning. Helse- og omsorgsdepartementet (Ministry of Health and Care Services) increasingly emphasises technology as a necessary component of future care delivery, not a nice-to-have. Helsedirektorat's national e-health strategy explicitly calls for better interoperability and data-driven decision support in primary care.

### 2.2 Current Spending and Waste

Municipal nursing homes in Norway operate under severe budget pressure, yet spend enormous sums on reactive, uncoordinated operations:

| Cost Category | Per-Facility Annual Spend | Notes |
|---|---|---|
| Temporary staffing (vikarbyrå) | 8–18M NOK | Varies by size and location |
| Staff training (fragmented) | 500K–1.5M NOK | Multiple platforms, no coordination |
| Adverse events (falls, medication errors) | 1–3M NOK | Direct costs; indirect costs 2–3x higher |
| Administrative overhead | 2–4M NOK | Manual scheduling, reporting, compliance |

Much of this spend is a direct consequence of system fragmentation. When competency data lives in Dossier, training records live in Making View, scheduling lives in a separate system, and compliance reporting is manual, the result is reactive operations: problems are discovered after they happen, not before.

### 2.3 Market Sizing

**Total Addressable Market (TAM): 4–6B NOK**

The total operations technology spend for Norwegian municipal care facilities, including all software, staffing optimisation, training platforms, automation, and compliance tooling. This covers approximately 1,000 municipal nursing homes and 10,000+ home care units.

**Serviceable Addressable Market (SAM): 500M–1B NOK**

The segment addressable by a horizontal operations platform: medium-to-large nursing homes (50+ beds) in municipalities with the budget and mandate to invest in interoperability and data-driven operations. Approximately 400–600 facilities across Norway's largest municipalities.

**Serviceable Obtainable Market (SOM): 50–100M NOK**

Our realistic capture target within 3–5 years: 30–60 facilities running CareOS with core platform licensing plus 2–4 connectors each, generating 1–2M NOK annual revenue per facility. This assumes successful pilot validation and regional expansion through municipal procurement networks (interkommunale samarbeid).

### 2.4 Market Segments

| Segment | Size | Characteristics | CareOS Fit |
|---|---|---|---|
| Large Nursing Homes (100–200+ beds) | ~150 facilities | Highest budget pressure, most temp agency spend, most IT fragmentation | Highest — ROI is immediate and measurable |
| Medium Nursing Homes (50–100 beds) | ~400 facilities | Budget-constrained but increasingly mandated by municipal strategy | Strong — platform + 2 connectors covers core needs |
| Municipal Health Administrations | 356 municipalities | Control procurement for all facilities; increasingly centralising IT decisions | Strategic buyer — one contract covers multiple facilities |

### 2.5 Regulatory Tailwinds

Several regulatory and policy developments create favourable conditions for CareOS:

- **Norm for informasjonssikkerhet i helse- og omsorgssektoren:** Mandates data governance standards that favour unified platforms over point solutions
- **HL7 FHIR adoption mandate:** Norway is progressively requiring FHIR-based interoperability, which CareOS's integration framework is built to support natively
- **Helsepersonellkommisjonen (NOU 2023:4):** Explicitly recommends technology-driven workforce transformation, creating political cover for municipal buyers
- **Kommunal digital strategi:** Municipal digitalization strategies increasingly mandate cross-system interoperability and data-driven decision-making
- **Statsbudsjett allocations:** Growing earmarked funding for healthcare technology innovation through programs like Helsedirektorat's Velferdsteknologiprogrammet

---

## 3. Product & Differentiation

### 3.1 The CareOS Architecture

CareOS is a 4-layer horizontal platform designed to sit underneath every vertical tool a care facility uses. It is not a training tool, not a robotics platform, not a scheduling system — it is the operating system layer that makes all of them work together.

**Layer 1: Data & Identity**

The foundation layer provides a unified operational data model that normalizes data from every connected system. At its core is the canonical staff identity: a real-time, comprehensive profile for every care worker that aggregates competency records from Dossier, training completion from Making View, scheduling data, certification status, and performance indicators into a single source of truth.

This layer also models facility-level data: ward structure, patient acuity levels, equipment inventories, and compliance requirements. The data model is designed around healthcare-specific ontologies (HL7 FHIR where applicable) and Norwegian regulatory frameworks (Helsepersonelloven, Forskrift om ledelse og kvalitetsforbedring).

Key technical characteristics:
- Event-sourced data model with full audit trail (required for healthcare compliance)
- Real-time synchronization across connected systems
- Role-based access control aligned with Norwegian healthcare data privacy requirements
- Aggregate views that no single source system can provide

**Layer 2: Workflow & Automation**

The event-driven workflow engine transforms disconnected tools into coordinated operations. When a competency gap is detected, a training assignment is automatically triggered. When a training module is completed, the staff member's readiness score is recalculated and their shift eligibility is updated. When a staffing change occurs, risk scores across the affected ward are recalculated.

This layer operates on a publish-subscribe event architecture: every connected system emits events, and CareOS orchestrates responses across the entire ecosystem. Workflows are configurable per facility, allowing each nursing home to define its own automation rules while benefiting from shared best practices across the CareOS network.

Example workflow chains:
- Competency gap detected → VR training assigned → Training completed → Readiness score updated → Shift eligibility recalculated → Risk score adjusted
- Staff absence reported → Coverage gap identified → Qualified replacements ranked → Shift offer dispatched → Acceptance confirmed → All systems updated
- Patient acuity change → Required competency profile updated → Current shift assessed → Gap alert raised → Mitigation actions triggered

**Layer 3: Intelligence & Decision Support**

The AI layer consumes the aggregated operational data to surface insights that no single system can produce:

- **Predictive risk scoring:** Identifies wards and shifts at elevated risk for adverse events (falls, medication errors, skill mismatches) before they occur
- **Staffing optimization:** Recommends optimal staff-to-patient matching based on real-time competency profiles, patient acuity, and historical outcomes
- **Training prioritization:** Identifies which competency gaps have the highest impact on patient safety and recommends targeted training interventions
- **Trend analysis:** Detects deteriorating patterns (increasing near-misses, rising temp agency dependency, training completion delays) and alerts leadership

This layer is where the data gravity moat becomes most powerful: the more systems connected, the more data flows through CareOS, and the more accurate and valuable the AI insights become. A facility with 4 connectors gets exponentially better predictions than one with 2.

**Layer 4: Integration Framework (Pluggable Connectors)**

The connector framework is what makes CareOS a platform rather than a product. Each connector is a standardized adapter that translates between a specific external system's API and the CareOS data model and event bus.

The connector architecture provides:
- **Standardized adapter pattern:** Each connector implements a defined interface (data mapping, event emission, action execution)
- **Connector SDK:** Third-party vendors and integration partners can build their own connectors
- **HL7 FHIR native support:** Healthcare-standard interoperability built into the framework
- **REST and webhook support:** Covers the full spectrum of integration patterns used by Norwegian healthcare IT vendors

First connectors (vertical wedge):
- **Dossier Connector:** Syncs competency profiles, certifications, and HR data into the unified staff identity
- **Making View Connector:** Integrates VR training completion events, module assignments, and skill assessments

Planned connectors:
- Scheduling system connectors (GAT, Visma, MinVakt)
- Robotic logistics connectors (when robotic systems reach deployment maturity)
- EPJ (electronic patient journal) connectors for patient acuity data

### 3.2 Why This Architecture Wins

**Vendor-neutral by design.** CareOS does not compete with any tool vendor. VR training providers, robot manufacturers, scheduling systems, and EPJ vendors are all potential connector partners — not competitors. This means CareOS is complementary to every tool purchase a facility makes, and every vendor has an incentive to build a connector because it makes their product more valuable.

**Data gravity creates compounding moats.** Once a facility's operational data flows through CareOS, the accumulated cross-system intelligence becomes the switching cost — not vendor lock-in through proprietary formats. Competitors would need to replicate the full data model and all connector mappings simultaneously.

**Workflow intelligence is impossible to replicate with point solutions.** No VR training vendor can optimise scheduling. No scheduling vendor can trigger training. No robotics vendor can assess competency. Only the OS layer can orchestrate across all of them, and the value of that orchestration grows with each connected system.

**Platform economics favour the OS layer.** As the Norwegian healthcare IT market grows and more specialised tools emerge (new VR platforms, new robotics vendors, new scheduling tools), CareOS becomes more valuable — each new tool is a potential connector, not a competitive threat.

### 3.3 The Connector Model vs. Build-Everything

The critical strategic insight is that healthcare tools will continue to fragment and specialise. There will be many VR training vendors, many scheduling systems, many robotic logistics providers. Trying to build all of these is capital-intensive, domain-specific, and guarantees competition with every vendor.

CareOS takes the opposite approach: we build the thin, horizontal layer that all of these tools need, and let specialised vendors do what they do best. This is the iOS/Android model applied to healthcare operations — we don't make the apps, we make the platform they run on.

---

## 4. Competitive Analysis

### 4.1 Competitive Landscape

CareOS operates in a market where the closest "competitors" are actually potential ecosystem partners. There is no direct competitor building a horizontal operations OS for Norwegian municipal care.

| Player | What They Do | Relationship to CareOS |
|---|---|---|
| **Dossier** | Competency management and HR platform for healthcare | Connector partner — provides staff data that CareOS aggregates and enriches |
| **Making View** | VR training simulations for healthcare workers | Connector partner — provides training events that CareOS orchestrates |
| **Visma / GAT** | Scheduling and workforce management | Future connector partner — scheduling data feeds CareOS workflow engine |
| **Tieto / CGM** | Electronic patient journal (EPJ) systems | Future connector partner — patient acuity data enriches CareOS risk models |
| **Temp agencies** (Adecco, Manpower) | Temporary healthcare staffing | Disruption target — CareOS reduces dependency through proactive operations |
| **Municipal IT departments** | Custom integrations and spreadsheet-based coordination | Replacement target — CareOS replaces manual integration work |

### 4.2 Why No One Owns the OS Layer Yet

Several structural factors explain why this category is unoccupied:

1. **Domain complexity:** Building a healthcare data model that correctly maps Norwegian regulations, competency frameworks, and facility operations requires deep domain expertise. Generic platform vendors (Salesforce Health Cloud, Microsoft Cloud for Healthcare) offer infrastructure but not the domain-specific data model or workflows.

2. **Market timing:** The convergence of VR training maturity, robotic logistics emergence, and government mandate for interoperability is happening now. Five years ago, there weren't enough connected tools to make an OS layer valuable. Five years from now, incumbents will have built proprietary integrations that create switching costs.

3. **Incentive misalignment:** Tool vendors (Dossier, Making View, scheduling providers) have no incentive to build an open OS layer — it would commoditize their data and reduce lock-in. They are rationally focused on deepening their vertical moats.

4. **Small market perception:** Norway's municipal care market appears small to international platform vendors, but it is large enough to build a dominant position and profitable enough to sustain a focused startup. The regulatory and linguistic barriers provide natural protection from international entrants.

### 4.3 Defensive Positioning

CareOS's competitive defense operates on three levels:

- **Network effects:** Each new connector makes the platform more valuable for every connected facility. Each new facility makes the connector ecosystem more attractive for tool vendors. This two-sided network effect accelerates with scale.
- **Data gravity:** The accumulated operational intelligence (workflow rules, risk models, benchmarking data) represents years of domain learning that cannot be replicated by a new entrant.
- **Ecosystem partnerships:** Signed partnership agreements with tool vendors create structural advantages — vendors who have invested in building CareOS connectors have an incentive to promote CareOS adoption, creating a distribution channel that a competitor would need to replicate vendor by vendor.

---

## 5. Business Model

### 5.1 Revenue Model: Platform + Connector Pricing

CareOS uses a SaaS model with two revenue streams that align incentives with customer value:

**Core Platform License (Annual)**

| Tier | Facility Size | Annual License (NOK) | Includes |
|---|---|---|---|
| Standard | 50–100 beds | 300,000–500,000 | Data & Identity layer, Workflow engine, 1 connector, Dashboard |
| Professional | 100–200 beds | 500,000–800,000 | Full platform, AI decision support, 2 connectors, Priority support |
| Enterprise | 200+ beds / Multi-facility | 800,000–1,500,000 | Full platform, all connectors, Custom workflows, Dedicated success manager |

**Per-Connector Licensing (Annual)**

| Connector Category | Annual Fee (NOK) | Notes |
|---|---|---|
| Competency (Dossier) | 50,000–100,000 | First vertical wedge — included in Professional+ |
| Training (Making View) | 50,000–100,000 | First vertical wedge — included in Professional+ |
| Scheduling (GAT, Visma, etc.) | 75,000–150,000 | Phase 2 connectors |
| Automation / Robotics | 100,000–200,000 | Phase 3 connectors |
| EPJ Integration | 100,000–200,000 | Phase 3 connectors |

### 5.2 Budget Hacking: Fitting Municipal Procurement

Norwegian municipal procurement has specific characteristics that CareOS's model is designed to exploit:

- **Annual budget cycles:** Municipalities allocate budgets annually. CareOS pricing fits within existing line items for "IT and digitalisation" or "quality and patient safety," avoiding the need for special budget allocations.
- **Cost-neutral positioning:** At 500K–1M NOK per facility, CareOS costs 3–6% of what a facility spends on temp agency staff alone. We position the platform as a cost reduction tool — the ROI covers the license in months, not years.
- **Interkommunalt samarbeid (inter-municipal cooperation):** Norwegian municipalities frequently collaborate on procurement. A single contract can cover 5–15 facilities across cooperating municipalities, reducing sales cycle cost and creating regional network effects.
- **Earmarked innovation funding:** Helsedirektorat's Velferdsteknologiprogrammet and Kommunal- og distriktsdepartementet's digitalization grants provide earmarked funding that can partially cover CareOS deployment costs during the pilot phase.

### 5.3 Unit Economics (Target State)

| Metric | Target |
|---|---|
| Average Revenue Per Facility (ARPF) | 600,000–1,200,000 NOK/year |
| Gross Margin | 75–85% (SaaS model, minimal per-facility marginal cost) |
| Customer Acquisition Cost (CAC) | 150,000–300,000 NOK (municipal procurement cycles are long but contracts are multi-year) |
| CAC Payback Period | 3–6 months |
| Net Revenue Retention | 120%+ (driven by connector expansion — facilities add connectors over time) |
| Annual Churn | <5% (municipal contracts are typically 3–5 year terms) |

The connector expansion model is the key to strong unit economics: a facility starts with the core platform and 1–2 connectors, then adds connectors as new tools are deployed or as they see ROI from the initial deployment. This creates natural revenue expansion without additional sales effort.

---

## 6. Strategic Roadmap

### 6.1 Phase 1: Foundation & Validation (2026–2027)

**Objective:** Build the core CareOS platform and validate through the competency/training vertical wedge in 3 pilot municipalities.

Key milestones:
- **Q2 2026:** Unified staff identity data model aggregating from Dossier and Making View into a canonical employee record
- **Q3 2026:** Event-driven workflow engine processing real-time events from connected systems with sub-minute event-to-action latency
- **Q4 2026:** Connector framework with standardized adapter pattern and 2 live connectors (Dossier, Making View)
- **Q1 2027:** Dossier connector live with real-time staff profile sync
- **Q2 2027:** Making View events flowing through workflow engine, readiness scores updated within 5 minutes
- **Q3 2027:** Operational dashboard deployed in 3 pilot municipalities showing competency gaps and shift-readiness scores

Success criteria:
- 3 pilot municipalities signed with platform deployment agreements
- Platform-plus-connector pricing accepted by pilots with sustainable unit economics
- At least 1 municipality documenting measurable savings from the CareOS competency/training vertical

Validated assumptions at end of Phase 1:
- Municipalities will share data across systems through a third-party platform
- The unified data model produces insights that individual systems cannot
- Workflow automation delivers measurable time savings for nursing directors
- Platform pricing is accepted within municipal budget constraints

### 6.2 Phase 2: Intelligence & Expansion (2027–2028)

**Objective:** Add AI decision support, expand connector ecosystem, and scale from 3 to 15–30 facilities.

Key milestones:
- **AI-powered risk scoring** based on aggregated operational data, targeting 15%+ reduction in adverse events at pilot facilities
- **Scheduling system connectors** (GAT, Visma, MinVakt) proving platform extensibility beyond the training vertical
- **Regional expansion** through interkommunale samarbeid — leveraging pilot municipality results to sign neighbouring municipalities
- **Connector SDK release** enabling third-party vendors to build their own connectors
- **Ecosystem partnerships** with Dossier and Making View formalized as platform partners with co-marketing agreements

Target metrics at end of Phase 2:
- 15–30 facilities on the platform
- 4+ live connector types
- 746K NOK Year 1 training savings per unit demonstrated
- 1.2M NOK savings from 10% adverse event reduction documented
- 5–15M NOK ARR

### 6.3 Phase 3: Scale & Category Leadership (2028–2029)

**Objective:** Establish CareOS as the dominant healthcare operations OS in Norway and prepare for Nordic expansion.

Key milestones:
- **50–100 facilities** on the platform across 20+ municipalities
- **Autonomous logistics connectors** as robotic systems reach deployment maturity
- **EPJ integrations** connecting patient acuity data to staffing optimization
- **National benchmarking data** — the CareOS network provides anonymised operational benchmarks that no individual facility can produce
- **Nordic market preparation** — adapting the platform for Swedish, Danish, and Finnish municipal healthcare (similar demographic challenges, similar municipal structures)
- **Temp agency cost reduction at scale** — targeting 18M NOK savings per facility at full connector deployment

Target metrics at end of Phase 3:
- 50–100M NOK ARR
- Category leadership recognized in Norwegian healthcare IT
- Nordic expansion initiated
- Series A readiness demonstrated

### 6.4 Long-term Vision (2029+)

CareOS becomes the standard operating layer for Nordic municipal care. Every VR vendor, scheduling vendor, robotics vendor, and EPJ vendor builds a CareOS connector because it makes their product more valuable. Facilities choose their best-of-breed tools knowing they'll work together through CareOS. AI-driven operations reduce adverse events by 25%+ and eliminate unsustainable temporary staffing dependency.

---

## 7. Team & Execution

### 7.1 Current Team

CareOS is currently a solo-founder operation, which is both a risk and a deliberate strategic choice.

**Nikolai Fasting — Founder & CEO**

Leading product strategy, architecture design, and commercial development. The solo-founder phase is focused on validating the core thesis (the OS layer has value) before scaling the team. This approach maximizes learning per krone spent during the pre-seed phase.

### 7.2 AI-First Development Philosophy

CareOS is built with an AI-first development methodology that dramatically reduces the engineering headcount required for early-stage platform development:

- **AI-assisted architecture:** System design, data model specification, and integration mapping are accelerated through AI tooling
- **AI-augmented development:** Code generation, testing, and documentation leverage AI assistants, targeting 2–3x individual engineering velocity
- **AI-native product:** The product itself uses AI for decision support, making AI capability a core competency rather than an add-on

This AI-first approach means a 3–5 person engineering team can deliver platform capabilities that would traditionally require 8–12 engineers. It also means the team we hire must be AI-native — comfortable working with AI tools as multipliers rather than replacements.

### 7.3 Hiring Plan (Pre-Seed)

The pre-seed round funds the first critical hires:

| Role | Timing | Focus |
|---|---|---|
| Senior Platform Engineer | Month 1–2 | Core data model, event bus, connector framework |
| Healthcare Domain Engineer | Month 2–4 | Dossier/Making View connectors, HL7 FHIR compliance |
| Full-Stack Product Engineer | Month 3–5 | Dashboard, workflow builder, user-facing tools |
| Customer Success Lead | Month 4–6 | Pilot onboarding, municipality relationships, feedback loops |

Target team at end of pre-seed: 5 people (founder + 4 hires), operating at the output level of a traditional 10–15 person team through AI-first practices.

### 7.4 Execution Advantages

- **Domain access:** Existing relationships with Norwegian municipal healthcare stakeholders provide pilot access that a foreign entrant cannot replicate
- **Regulatory familiarity:** Deep understanding of Norwegian healthcare IT regulations, procurement processes, and data privacy requirements (Personvernforordningen / GDPR, Helsepersonelloven, Normen)
- **Speed:** AI-first development combined with a focused platform architecture means faster iteration than either incumbents (burdened by legacy) or generalists (lacking domain specificity)

---

## 8. Financial Highlights

### 8.1 Revenue Projections (5-Year)

| Year | Facilities | ARR (NOK) | Growth | Notes |
|---|---|---|---|---|
| 2026 | 0–3 (pilots) | 0–500K | — | Pilot validation; may be subsidized or free-tier |
| 2027 | 3–8 | 2–5M | — | First paid deployments post-pilot |
| 2028 | 8–25 | 8–20M | 200–300% | Regional expansion via interkommunalt samarbeid |
| 2029 | 25–60 | 25–60M | 200% | National coverage beginning, full connector suite |
| 2030 | 60–100+ | 60–120M | 100% | Category leadership, Nordic expansion initiated |

These projections assume an average revenue per facility (ARPF) starting at 600K NOK (platform + 2 connectors) and growing to 1.2M NOK as facilities add connectors and upgrade tiers.

### 8.2 Cost Structure

| Category | Year 1 (NOK) | Year 2 (NOK) | Year 3 (NOK) | Notes |
|---|---|---|---|---|
| Engineering team (salaries) | 2,500,000 | 4,500,000 | 7,000,000 | 4 hires Year 1, growing to 8–10 |
| Cloud infrastructure | 150,000 | 400,000 | 800,000 | Scales with facility count |
| Customer success | 300,000 | 800,000 | 1,500,000 | 1 hire Year 1, growing to 3 |
| Sales & marketing | 200,000 | 600,000 | 1,200,000 | Conference presence, municipality outreach |
| Legal & compliance | 300,000 | 200,000 | 300,000 | Healthcare data compliance, contracts |
| Office & admin | 200,000 | 300,000 | 400,000 | Minimal — remote-first team |
| **Total** | **3,650,000** | **6,800,000** | **11,200,000** | |

### 8.3 Path to Profitability

CareOS targets gross margin of 75–85% at scale (pure SaaS model with minimal per-facility marginal cost). The path to profitability depends on facility acquisition rate:

- **Conservative scenario:** Break-even at 20–25 facilities (~Year 3), requiring one additional funding round (seed or Series A of 10–20M NOK in Year 2–3)
- **Base scenario:** Break-even at 15–20 facilities (~late Year 2), with the seed round extending runway to profitability
- **Optimistic scenario:** Strong municipal adoption through interkommunale samarbeid accelerates facility acquisition, reaching break-even at 12–15 facilities in Year 2

### 8.4 ROI for Customers

The financial case for municipal buyers is compelling and measurable:

| Value Driver | Annual Savings Per Facility (NOK) | Basis |
|---|---|---|
| Training efficiency | 746,000 | Reduced duplication, targeted training assignment |
| Adverse event reduction (10%) | 1,200,000 | Falls, medication errors, unnecessary hospitalizations |
| Temp agency cost reduction | 2,000,000–18,000,000 | From 10% reduction (early) to 50%+ at full scale |
| Administrative time savings | 500,000–1,000,000 | Automated reporting, compliance, scheduling |
| **Total Year 1 savings** | **~2–3M NOK** | Conservative estimate (training + adverse events) |
| **Total savings at full scale** | **~5–20M NOK** | All value drivers realized |

At a platform cost of 500K–1.2M NOK per facility, the ROI is 2–4x in Year 1 and 5–15x at full connector deployment. This makes CareOS one of the highest-ROI investments a municipal nursing home can make.

### 8.5 SkatteFUNN and Innovation Grants

CareOS qualifies for several Norwegian innovation funding programs:

- **SkatteFUNN:** Up to 19% tax credit on R&D expenses (up to 25M NOK eligible base) — potentially 700K–1.5M NOK per year in tax credits
- **Innovasjon Norge:** Technology development grants for healthcare innovation
- **Forskningsrådet:** Research project funding for AI in healthcare operations
- **Velferdsteknologiprogrammet:** Earmarked funding for municipal health technology adoption (can subsidize customer-side deployment costs)

---

## 9. Investment Ask

### 9.1 The Round

**Raising:** 3–5M NOK pre-seed  
**Instrument:** Convertible note or priced equity (SAFE-equivalent adapted for Norwegian corporate law)  
**Valuation guidance:** 15–25M NOK pre-money (to be discussed)  
**Target close:** Q2 2026

### 9.2 Use of Funds

| Allocation | Amount (NOK) | % of Round | Purpose |
|---|---|---|---|
| Engineering team | 1,800,000–2,500,000 | 50–55% | 3–4 engineers (platform, connectors, frontend) |
| Pilot operations | 400,000–600,000 | 10–15% | Municipality onboarding, data migration, training |
| Infrastructure & tools | 300,000–400,000 | 8–10% | Cloud hosting, development tools, security |
| Customer success | 200,000–400,000 | 5–10% | Pilot support, feedback loops, documentation |
| Legal & compliance | 200,000–300,000 | 5–7% | Healthcare data compliance, contracts, IP |
| Buffer / contingency | 300,000–500,000 | 8–12% | Runway extension, unexpected costs |
| **Total** | **3,200,000–4,700,000** | **100%** | |

### 9.3 Milestones This Round Funds

The pre-seed round is designed to retire the core risk: does the OS layer create measurable value in a real municipal care environment?

1. **Core platform built:** Unified data model, workflow engine, and connector framework operational
2. **Two live connectors:** Dossier (competency) and Making View (VR training) connectors deployed
3. **Three pilot municipalities:** Signed agreements with committed deployment timelines and data sharing
4. **Measurable ROI demonstrated:** At least 1 municipality documenting quantified savings from CareOS
5. **Pricing validated:** Platform-plus-connector pricing accepted within municipal budget constraints
6. **Category positioning established:** CareOS presented at 2+ Norwegian healthcare conferences

These milestones position CareOS for a seed or Series A round of 10–20M NOK in 2027–2028, funding the scaling phase from 3 pilots to 15–30 facilities.

### 9.4 Why Now

Three forces are converging to create the window for CareOS:

1. **Tool maturity:** VR training (Making View), robotic logistics, and competency platforms (Dossier) have reached deployment maturity in Norwegian nursing homes. For the first time, there are enough connected tools to make an OS layer valuable.

2. **Government mandate:** NOU 2023:4 and subsequent policy responses have created explicit political and regulatory mandate for technology-driven workforce transformation in municipal care. Municipal buyers now have both the motivation and the political cover to invest.

3. **AI readiness:** The AI capabilities required for predictive decision support have reached a cost and quality threshold that makes them viable for municipal-scale deployments. Two years ago, the AI layer would have been prohibitively expensive. Two years from now, a competitor will have started.

The window to define the healthcare operations OS category in Norway is open now. CareOS is positioned to own it.

---

*This document contains forward-looking projections based on current market analysis and assumptions. All financial figures are estimates and subject to change based on market conditions and pilot validation results.*

*CareOS — The Healthcare Operations OS*  
*Contact: Nikolai Fasting — Founder & CEO*
