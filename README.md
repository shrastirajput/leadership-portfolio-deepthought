# Leadership Portfolio — DeepThought PM Internship Assignment

**Candidate:** Shrasti Rajput  
**Role Applied:** Product Management Intern — PDGMS  
**Assignment:** Leadership Portfolio Page Redesign  
**Submitted:** June 2026

---

## What This Is

This is a working HTML prototype of the **Leadership Portfolio** page for PDGMS (People Development & Growth Management System) — DeepThought's AI-powered operating platform for Indian manufacturing MSMEs.

The assignment brief: *redesign the Leadership Portfolio so it feels like a personal career pitch deck, not a monitoring dashboard.*

**Live prototype →** [View here](https://shrastirajput.github.io/leadership-portfolio-deepthought)

---

## The Design Problem

The original Leadership Portfolio looked like a dashboard — metric widgets arranged in a grid, equal visual weight, anonymous, optimized for monitoring.

The goal was to transform it into a **career artifact** — narrative-first, story-driven, something an employee would be proud to show a mentor or future employer.

| Dashboard (before) | Pitch Deck (target) |
|---|---|
| Metric soup, equal weights | One clear signal at the top |
| Anonymous — could be anyone | Personal — your name, your story |
| Data first, story as footnote | Story first, data as evidence |
| Feels like Jira | Feels like a document you own |

---

## Design Decisions

### 1. Narrative leads, data supports
Every section opens with a written paragraph before any numbers appear. The numbers exist to prove the narrative — not replace it. This directly addresses the core brief: "story-driven, not dashboard-driven."

**Tradeoff:** Supervisors who want numbers first have to read one paragraph before reaching data. Accepted this tradeoff because the primary audience is the employee themselves, not the reviewer.

### 2. Single continuous scroll — no tabs
The previous design used tabs (sidebar navigation) to switch between 6 sections. I replaced this with a **continuous vertical scroll** — each section is a card stacked below the previous one.

**Why:** The portfolio is a monthly career document, not a monitoring tool. Tabs encourage cherry-picking metrics. Continuous scroll encourages reading the whole story. A mentor reviewing the portfolio reads it top to bottom — not by jumping between tabs.

**Tradeoff:** Longer page. Mitigated by strong progressive disclosure — headline and 4 key stats visible immediately without scrolling.

### 3. The signal is a sentence, not a number
The hero section leads with an italic serif headline: *"Rajan had his strongest month since joining"* — not a score widget.

The composite score (71) appears as one of four supporting stat pills below the headline, not as the dominant element.

**Why:** A sentence communicates meaning. A number requires interpretation. The employee should feel something when they open their portfolio — not reach for a calculator.

**Tradeoff:** Less scannable for supervisors who want to quickly benchmark scores. Addressed by keeping the 4 stat pills (71 / 64→71 / V2 / Feb 2027) clearly visible immediately below the headline.

### 4. Progressive disclosure for detail
The 7 IP commit items are hidden behind a **"View 7 knowledge contributions"** toggle — not shown by default.

**Why:** The employee has 30 seconds between meetings. The top of the page answers "how did I do?" in one scan. Detail is available but not forced. This is directly specified in the assignment's soft constraints.

### 5. Constraint section as honest professional communication
Constraints (blockers) are presented with 3 large stat cards (8 Raised / 5 Resolved / 3 Open) and a narrative that frames them as problem-solving evidence — not a complaint list.

**Why:** The assignment explicitly identified this as the hardest section to design. Making the numbers prominent (8 raised) with the resolution rate equally prominent (5 resolved = 62.5%) reframes constraints as accountability and initiative, not failure.

---

## Data Fidelity

Every number in this prototype maps to a real field in the PDGMS data model (`data-model.ts`) and mock data (`mock-portfolio-data.json`). No numbers were invented.

| Value | Source field |
|---|---|
| Composite score: 71 | `compositeScore` |
| Previous month: 64 | `previousMonthScore` |
| Current level: V2 | `currentLevel` |
| Projected V3: Feb 2027 | `projectedDate` |
| Deliverables: 16/20 | `completed` / `totalDeliverables` |
| IP commits: 7 | `ipCommitCount` |
| Engagement: 85 | `ritualScore` |
| Delivery: 80 | `deliveryRate` |
| Original Work: 74 | `ipScore` |
| Program Targets: 68 | `kpiScore` |
| Process Adoption: 58 | `processScore` |
| Framework Use: 52 | `frameworkScore` |
| Constraints: 8 raised, 5 resolved, 3 open | `totalConstraints`, `resolved` |
| KPI table: all 5 rows | `details[]` in kpi_impact section |
| Career milestones: V1–V5 | `milestones[]` |

---

## Design Challenges Addressed

From Part 10 of the assignment brief:

| Challenge | Position taken |
|---|---|
| **The Signal** | Italic serif sentence headline — not a score ring or grade |
| **Story vs Data ordering** | Narrative always leads; data follows as evidence |
| **Six sections — too many?** | KPI and Constraints merged into Target Outcomes / Operating Context; all 6 axes preserved |
| **Constraint section** | Framed as accountability (resolved vs raised) not complaint list |
| **Portability and Identity** | Name, role, org, and UID prominent in sticky topbar; UID in footer; no internal jargon |

---

## Hard Constraints Followed

- ✅ Read-only surface — no inputs or forms
- ✅ All data maps to backend fields in `data-model.ts`
- ✅ No LLM on frontend — narratives rendered server-side (simulated)
- ✅ UID visible — in topbar and footer
- ✅ Month-scoped — month selector in topbar
- ✅ No jargon — "IP Commits" → "Knowledge Contributions", "Rituals" → "Engagement", "Pending QA" → "Awaiting Review"

---

## File Structure

```
leadership-portfolio-deepthought/
├── leadership_portfolio.html    # Complete working prototype (single file)
└── README.md                    # This file
```

The entire prototype is a single self-contained HTML file — no dependencies, no build step, no framework. Opens directly in any browser.

---

## Reference Materials Used

- `context.md` — Assignment brief and design constraints
- `data-model.ts` — PDGMS TypeScript type definitions
- `mock-portfolio-data.json` — Rajan Iyer, V2, Vayura Lifesciences, March 2026
- MoneyLion credit score UI — reference for animated score bar and morphing ring
- DeepThought internship presentation slides — reference for section layouts

---

*Built with HTML, CSS, and vanilla JavaScript. No frameworks. No libraries. No external dependencies.*
