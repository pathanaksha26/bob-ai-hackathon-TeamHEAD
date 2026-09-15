# 🚀 Supply Chain Disruption Assistant & Fleet Utilisation Optimizer

> ⚠️ **Replace everything in `[ ]` brackets with your actual content before submission.**

---

## 👥 Team

| Field | Value |
|---|---|
| **Team Name** | Team HEAD |
| **Track** | AI |
| **Team Lead** | Esha Machhi — 26pgceo10@charusat.edu.in |
| **Members** | Dinal Thakkar, Aksha Pathan, Himani Patel |

---

## 🎯 Problem Statement

> In 2–3 sentences: What problem does your project solve? Who experiences this problem?

Supply chain disruptions — weather events, port strikes, geopolitical
crises — cascade across hundreds of active shipments in ways that are
impossible to track manually. Fleet assets (trucks, containers, vessels)
sit idle on unaffected routes while other routes are overloaded. Cold chain
shipments (vaccines, perishables) are especially vulnerable: a single
temperature excursion on any leg can spoil cargo worth $500K+, but breaches
are typically only discovered at delivery — when it's already too late.

---

## 💡 Solution

> In 2–3 sentences: What did you build? How does it solve the problem above?

We built a decision-support tool that gives a logistics shift supervisor a
single view across four problems that are normally handled in separate
spreadsheets and phone calls:

1. **Disruption Impact** — select an active disruption (port strike,
   weather, geopolitical) and instantly see every shipment it affects,
   ranked by a risk score (severity × cargo value × cold-chain sensitivity).
2. **Re-routing** — for every affected shipment, get a recommended alternate
   carrier and, where available, an idle fleet asset in the same region
   that can absorb the cargo without waiting for the disruption to clear.
3. **Fleet Redeployment** — a live view of idle trucks, vessels, and reefer
   container sets, automatically matched against disrupted regions that
   need extra capacity.
4. **Cold Chain Monitor** — sensor logs for every cold-chain shipment,
   automatically scanned for temperature excursions and classified by
   severity (Minor / Major / Critical) so QA can intervene before spoiled
   cargo reaches its destination.

All four views feed into an **AI-generated BLUF (Bottom-Line-Up-Front)
operations brief** — the same format defense and logistics commanders use
to get the full picture in under a minute.

---

## ✨ Key Features

- **Feature 1:** Risk-scored disruption impact analysis across route and region
- **Feature 2:** Automated carrier + fleet re-routing recommendations
- **Feature 3:** Idle-asset redeployment planner
- **Feature 4:** AI advisor layer pluggable to **IBM watsonx.ai**, with a deterministic fallback so the app is fully demoable with zero API keys'

---

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
- **Frontend/App:** Streamlit (Python)
- **Logic/Backend:** Python (pandas for data processing)
- **AI Layer:** IBM watsonx.ai (Granite instruct model) via REST API, with
  a rule-based BLUF generator as an offline fallback
- **Built with:** IBM Bob (see `docs/architecture.md` for how Bob was used
  in development)

---

## 📁 Repository Structure

```
├── src/                  # All source code
├── docs/                 # Written documentation
│   ├── problem-statement.md
│   ├── solution-overview.md
│   ├── architecture.md
│   └── setup-guide.md
├── demo/                 # Demo artifacts
│   ├── screenshots/      # App screenshots
│   └── demo-video-link.txt  # Link to demo video
├── presentation/         # Slide deck
└── submission.yaml       # Structured submission metadata
```

---

## ⚡ How to Run

> **Copy these exact steps from your [`docs/setup-guide.md`](docs/setup-guide.md)**

```bash
cd src
pip install -r requirements.txt
streamlit run app.py
```

Then open the URL Streamlit prints (usually `http://localhost:8501`).
No API key is required — the app ships with synthetic sample data and a
deterministic AI-brief fallback. See `docs/setup-guide.md` for full details
and `src/.env.example` for optional watsonx.ai credentials.

---

## 🖥️ Demo

| Artifact | Link |
|---|---|
| 📹 Demo Video | [See demo/demo-video-link.txt]("C:\Users\AKSHA\Downloads\bob-ai-hackathon-L2-starter\demovideo\Video.mp4") |
| 🌐 Live Demo | [See demo/live-demo-url.txt](not deployed) |
| 🖼️ Screenshots | [See demo/screenshots/]("C:\Users\AKSHA\Downloads\bob-ai-hackathon-L2-starter\screenshots") |
| 📊 Presentation | [See presentation/slides.pdf]("C:\Users\AKSHA\Downloads\bob-ai-hackathon-L2-starter\presentation\slides.pptx"/) |

---

## ⚠️ Known Limitations

> Be honest — judges appreciate transparency over overclaiming.

- Uses synthetic sample data (shipments, disruptions, fleet, sensor logs)
  rather than live vessel-schedule/IoT feeds — in production these would be
  ingested from AIS/vessel tracking APIs, TMS systems, and real IoT
  temperature loggers.
- Re-routing recommendations use a simple in-region idle-asset match rather
  than full multi-leg route optimisation.
- The watsonx.ai integration requires the team's own API credentials to
  demo live generative reasoning; the deterministic fallback is what runs
  by default in the video.

---

## 🏅 What We're Most Proud Of

The cold-chain excursion detector and the fleet redeployment matcher run on
the exact same underlying data model as the disruption-impact engine —
meaning a single disruption event automatically triggers all four types of
recommendations without any manual hand-off between spreadsheets, which is
exactly the workflow the problem statement describes as "impossible to
track manually" today.

---
