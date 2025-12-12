# Demand Management

## Table of Contents

- [Demand Management](#demand-management)
  - [Table of Contents](#table-of-contents)
  - [Demand-to-Delivery](#demand-to-delivery)
    - [How a New Demand (Request) Arises in a Company](#how-a-new-demand-request-arises-in-a-company)
    - [Typical End-to-End Flow of Demand Management (Demand-to-Delivery)](#typical-end-to-end-flow-of-demand-management-demand-to-delivery)
    - [Key Roles You Mentioned and Their Responsibilities](#key-roles-you-mentioned-and-their-responsibilities)
    - [Where Was This Way of Organizing Taught?](#where-was-this-way-of-organizing-taught)

## Demand-to-Delivery

### How a New Demand (Request) Arises in a Company

In most medium-to-large companies (especially in technology, digital products, manufacturing with software, or any industry with an internal factory/model of custom development or production), a new demand typically starts in one of these ways:

1. **Strategic/top-down request**  
   – A VP, Director, C-level, or the Prioritization/Steering Committee decides that something is a company priority (new revenue stream, regulatory requirement, cost reduction, etc.).

2. **Business area request**  
   – Marketing, Sales, Operations, Finance, Compliance, Customer Success, etc., identify a need and formally open a demand.

3. **Customer/external request**  
   – A large client, partner, or regulator demands a new feature, report, integration, or product.

4. **Internal improvement or tech debt**  
   – Technology, Security, Infrastructure, or the factory itself raises the need for refactoring, migration, security hardening, performance, etc.

5. **Innovation or experimentation**  
   – Comes from a lab, innovation squad, hackathon, or product owner with a new idea.

### Typical End-to-End Flow of Demand Management (Demand-to-Delivery)

Here is the most common operating model used globally in 2024–2025 (IT, software factories, shared services, GBS, etc.):

| Stage | Who is usually the owner/SPOC | Main activities | Key ceremonies/artifacts |
| --- | --- | --- | --- |
| 1. Idea / Demand creation | Requesting area (VP, Director, Product Manager) | The requester fills out a standard form (Demand Intake Form, Epic Brief, One-Pager) with business case, ROI, effort estimate (t-shirt or high-level points), deadline, regulatory flag, etc. | Template in ServiceNow, Jira, Azure DevOps, SAP Signavio, internal portal |
| 2. Initial screening & registration | Demand Management team (or Portfolio Office) | Validate that the form is complete, register the demand with a unique ID, classify (project vs BAU, strategic vs tactical), initial risk analysis | Demand ID (e.g., DEM-2025-0123) |
| 3. Prioritization | Prioritization/Steering Committee (usually monthly) – formed by VPs of requesting areas + VP of the Factory + Finance + Technology | Score demands (WSJF – Weighted Shortest Job First, business value × time criticality × risk reduction / job size), decide what enters the next planning window (quarter, PI – Program Increment in SAFe) | Prioritization meeting, ranked backlog, “approved”, “rejected”, or “parked” status |
| 4. High-level analysis / Initiation | Demand Manager + Solution Architect + Product Owner | Detailed business case, feasibility study, very high-level solution, effort in story points or man-days, identification of affected squads/factory cells | Initiation/Kick-off workshop, ROM (Rough Order of Magnitude) estimate |
| 5. Detailed analysis & requirements | Business Analyst + Product Owner + QA lead | Functional and non-functional requirements, user stories, acceptance criteria, UX wireframes, data mapping, integration points | Refinement sessions, DoR (Definition of Ready) met |
| 6. Quality gate 1 – Approval to build | Demand Manager + Prioritization Committee (light version) or Change Advisory Board | Validate that scope, cost, and deadline are still aligned; approve funding and start of construction | Go/No-Go meeting |
| 7. Development / Execution | Squads or factory cells (Dev + QA) | Agile sprints (Scrum/Kanban), daily stand-ups, code, automated tests, peer review | Sprint Planning, Backlog Grooming, Sprint Review |
| 8. Quality gate 2 – QA and homologation | QA Lead + Demand Manager + Requestor | System testing, UAT (User Acceptance Testing), performance, security, accessibility testing | UAT sign-off document |
| 9. Deployment to production | Release Manager + DevOps + Infra | CI/CD pipeline, canary/blue-green deployment, rollback plan | Go-Live checklist, post-deployment validation |
| 10. Closure & lessons learned | Demand Manager | Measure delivered business benefit vs initial business case, close demand, document lessons | Closure report, update capacity model |

### Key Roles You Mentioned and Their Responsibilities

| Role | Typical responsibility in the flow above |
| --- | --- |
| Demand Management team | Stages 1–4 and 6, 10 – single point of contact (SPOC) for the entire life cycle of the demand |
| Owner/SPOC of the order | Usually the Demand Manager assigned to that specific demand – the one person the requester calls when they want status |
| QA | Involved from stage 5 (helps write acceptance criteria), owner of stage 8 |
| Factories / Cells / Squads | Execute stage 7 (and part of 5) |
| Prioritization Committee | Stage 3 (and light validation in stage 6) |
| VP / Requesting management | Creates the demand (stage 1), defends it in committee (stage 3), participates in UAT and go-live (stages 8–9) |

### Where Was This Way of Organizing Taught?

Yes, this model is formalized and taught in several global frameworks and certifications:

1. **SAFe (Scaled Agile Framework)** – version 6.0 (2023–2025)  
   – Portfolio → Solution → Program → Team levels  
   – “Portfolio Backlog”, “Intake Process”, “WSJF prioritization”, “PI Planning”

2. **ITIL 4** – Demand Management + Request Management + Portfolio Management practices

3. **PMI – Portfolio Management (PfMP)** and **Managing Successful Programmes (MSP)**

4. **Cobit 2019** – APO08 Manage Demand

5. **Specific courses you will find with exactly this model**  
   – “SAFe for Architects” / “SAFe Product Owner/Product Manager”  
   – “ITIL 4 Specialist: Drive Stakeholder Value”  
   – “Demand Management & BRM (Business Relationship Management)” from BRM Institute  
   – Internal courses from consultancies (McKinsey, BCG, Deloitte, Accenture) called “IT Demand Management Operating Model” or “Global Business Services Factory Model”

In Brazil many large companies (banks, retailers, oil & gas, industry) implemented this exact model between 2018 and 2024, almost always based on SAFe + ITIL 4 + some home-grown prioritization committee.

If you need the complete RACI, a ready template of the Demand Intake Form in Portuguese, or the standard presentation deck that consultancies use to implement this (the famous 30–40 slides), just let me know and I’ll send it! 😄