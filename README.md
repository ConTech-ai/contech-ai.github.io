# contech-ai

> **The public-facing website for ConTech.ai** — hosted at [https://contech-ai.github.io](https://contech-ai.github.io)

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/ConTech-ai/contech-core/blob/main/LICENSE)
[![Org: ConTech-ai](https://img.shields.io/badge/org-ConTech--ai-1A3C34)](https://github.com/ConTech-ai)
[![Live Site](https://img.shields.io/badge/site-contech--ai.github.io-40916C)](https://contech-ai.github.io)

---

## What Is This Repository?

This repository contains the static landing page for ConTech.ai. It is a single `index.html` file served by GitHub Pages at `https://contech-ai.github.io`. The site communicates the mission, product overview, agent architecture, and development roadmap of the ConTech.ai platform to external visitors — contributors, collaborators, and the broader construction-tech community.

This repository is intentionally minimal. It holds only the public-facing website. All technical documentation, agent specifications, architecture diagrams, the shared SDK, and deployment orchestration live in the organization's core repository — see below.

---

## The Technical Backbone: `contech-core`

If you arrived here from the website and want to understand the system in depth, the right place to go is [`contech-core`](https://github.com/ConTech-ai/contech-core) — the central hub of the entire ConTech.ai platform.

`contech-core` contains five categories of content that define how the whole system is built and governed:

The **Operational Guide** (`docs/`) is the authoritative blueprint for the startup — covering mission, product overview, all agent specifications, the multi-agent decision framework, and the full proof-of-concept flow. If you want to understand *why* each agent exists and *how* it makes decisions, start there.

The **Shared SDK** (`sdk/`) contains common Python and JavaScript packages for inter-agent communication, RAG pipeline setup, vector database clients, authentication, and logging. Every agent repository in the organization imports from here — it is what keeps all 11 repositories coherent despite being developed independently.

The **Deployment Orchestration** (`deploy/`) holds Docker Compose files, Kubernetes manifests, and CI/CD pipeline definitions for running the full system locally or deploying individual agents to cloud infrastructure.

The **Architecture Diagrams** (`diagrams/`) provide versioned visual references for the system overview, agent interaction flows, and data layer topology.

**Project Management** is also centralized in `contech-core` via GitHub Issues and Milestones, so cross-repository progress across all 11 repos can be tracked in one place.

---

## The Full Repository Map

The ConTech.ai system spans 11 repositories. This table is the quickest way to understand what each one does and where it fits in the architecture.

| Repository | Layer | Role |
|---|---|---|
| [contech-core](https://github.com/ConTech-ai/contech-core) | Foundation | Blueprint, shared SDK, deployment orchestration, architecture diagrams |
| [contech-ui](https://github.com/ConTech-ai/contech-ui) | User Interaction | React/Next.js chat interface and sustainability dashboard |
| [contech-query-router-agent](https://github.com/ConTech-ai/contech-query-router-agent) *(planned)* | User Interaction | Intent classification and agent delegation |
| [contech-rag-ai-agent](https://github.com/ConTech-ai/contech-rag-ai-agent) | AI Processing | Vector DB querying backbone — LEED, BREEAM, ISO 14001, material specs |
| [contech-design-optimization-agent](https://github.com/ConTech-ai/contech-design-optimization-agent) | AI Processing | Climate-aware parametric building design generation |
| [contech-carbon-tracking-agent](https://github.com/ConTech-ai/contech-carbon-tracking-agent) | AI Processing | CO₂ calculation, predictive forecasting, threshold-triggered workflows |
| [contech-material-selection-agent](https://github.com/ConTech-ai/contech-material-selection-agent) | AI Processing | Multi-objective material scoring and trade-off negotiation |
| [contech-bim-modification-agent](https://github.com/ConTech-ai/contech-bim-modification-agent) | Execution & BIM | Applies AI decisions into Rhino + Grasshopper models |
| [contech-iot-data-platform](https://github.com/ConTech-ai/contech-iot-data-platform) *(planned)* | Execution & BIM | IoT sensor simulation via ThingsBoard, Node-RED, Apache NiFi |
| [contech-regulatory-and-compliance-agent](https://github.com/ConTech-ai/contech-regulatory-and-compliance-agent) | Compliance & Reporting | LEED, BREEAM, ISO 14001 validation with override authority |
| [contech-reporting-agent](https://github.com/ConTech-ai/contech-reporting-agent) | Compliance & Reporting | Certification-ready sustainability reports and carbon analyses |
| **contech-ai.github.io** *(this repo)* | Public Web | Static landing page served via GitHub Pages |

---

## Running the Site Locally

The site is a single self-contained HTML file with no build step, no dependencies, and no package manager required. To preview it locally, clone the repository and open the file directly in any browser.

```bash
git clone https://github.com/ConTech-ai/contech-ai.github.io.git
cd contech-ai.github.io
open index.html        # macOS
# or: start index.html  (Windows)
# or: xdg-open index.html (Linux)
```

If you prefer a live-reload development server, any static file server works. For example, using Python's built-in server:

```bash
python -m http.server 8080
# Then visit http://localhost:8080 in your browser
```

---

## Making Changes

The entire site lives in `index.html`. All styles are written as inline `<style>` CSS (no external stylesheets beyond Google Fonts), and all interactivity is plain JavaScript. This keeps the repository dependency-free and the deployment path as simple as possible — a `git push` to `main` is all it takes to update the live site.

When making edits, the sections to be aware of are the hero statistics (which should stay in sync with the platform's actual capabilities), the agent card descriptions (which should reflect the current spec in `contech-core`), and the roadmap phase status (the `active` CSS class on the current phase card should be updated as development progresses).

---

## Contributing

Contributions to the website follow the same branch-and-PR workflow defined in [`contech-core/CONTRIBUTING.md`](https://github.com/ConTech-ai/contech-core/blob/main/CONTRIBUTING.md). For changes that affect how the platform is described — agent roles, workflow steps, or the architecture diagram — please ensure your PR is consistent with the current state of `contech-core`'s Operational Guide.

---

## Contact & Links

The organization email is [contech.ai@outlook.com](mailto:contech.ai@outlook.com). The full GitHub organization is at [github.com/ConTech-ai](https://github.com/ConTech-ai). For the complete technical documentation, architectural specs, and agent decision framework, start with [`contech-core`](https://github.com/ConTech-ai/contech-core).

---

## License

MIT — see [LICENSE](https://github.com/ConTech-ai/contech-core/blob/main/LICENSE) in `contech-core` for details.

---

*ConTech.ai — Making sustainability the default in construction.*
