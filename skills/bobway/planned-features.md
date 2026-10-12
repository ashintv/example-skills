# BobWay: Planned Features & Evolution Roadmap

This document outlines the planned capabilities, platform milestones, and architectural evolution for **BobWay**—the AI Skills & Inference Marketplace built specifically for the Bob coding assistant.

---

## 🗺️ Vision & Roadmap Overview

BobWay is designed to bridge the gap between autonomous AI coding assistants and real-world engineering standards. As development teams adopt Bob, BobWay serves as the centralized control plane that delivers verified skills, enforces security guardrails, and simplifies onboarding.

```
┌────────────────────────────────────────────────────────────────────────┐
│                        BobWay Evolution Stages                         │
├──────────────────┬──────────────────┬──────────────────┬───────────────┤
│     Phase 1      │     Phase 2      │     Phase 3      │    Phase 4    │
│  Team Sync &     │   Governance &   │  Ecosystem &     │  Intelligent  │
│  Propagation     │   Guardrails     │  Marketplace     │  Context      │
└──────────────────┴──────────────────┴──────────────────┴───────────────┘
```

---

## 🚀 Phase 1: Team Synchronization & Workspace Propagation

### 1. Workspace Propagation
- **Automated Team Sync**: When a lead engineer publishes or updates a workspace skill set, all connected team members automatically receive updated skill packages without manual intervention.
- **Repository Manifest (`bobway.json`)**:
  - Teams can check in a root configuration file:
    ```json
    {
      "$schema": "https://bobway.io/schema/v1.json",
      "workspace": "acme-corp/fintech-backend",
      "autoSync": true,
      "enforceCompliance": true
    }
    ```
  - When a newly onboarded engineer clones the repository and opens Bob, the BobWay extension detects the manifest, verifies the project key, and configures the environment with zero friction.

### 2. Live Collaborative Skill Sharing
- **In-Editor Publishing**: Export and share custom skills directly from Bob with a single command (`BobWay: Share Skill to Workspace`).
- **Diff & Version Review**: Compare modifications between the local skill copy and the workspace upstream version.

---

## 🛡️ Phase 2: Enterprise Governance & Guardrail Policies

### 1. Role-Based Access Control (RBAC)
- **Hierarchy of Roles**:
  - **Owner**: Full workspace management, billing, and member access.
  - **Maintainer**: Can publish, update, and deprecate skills.
  - **Member / Contributor**: Can subscribe, use, and suggest skill enhancements.
- **Organization-Wide Workspaces**: Workspaces accessible only to verified corporate SSO users (`@company.com`).

### 2. Mandatory Compliance Guardrails
- **Non-Bypassable Policies**: Admins can tag skills as "Mandatory", preventing individual developers from disabling them locally.
- **Pre-Commit AI Audits**:
  - Automatic scan for hardcoded secrets, tokens, and API credentials.
  - OWASP Top 10 compliance audits on all AI-suggested code blocks.
  - Licensing checks ensuring no GPL code is introduced into commercial projects.

### 3. Observability & Audit Trails
- Centralized dashboard displaying:
  - Active workspaces and installed skill distributions across engineering squads.
  - Frequency of triggered engineering guardrails and blocked security hazards.
  - Anonymized token efficiency and inference performance metrics.

---

## 🌐 Phase 3: Marketplace Ecosystem & Community Registry

### 1. Public Community Registry
- Open marketplace where authors, open-source communities, and framework creators can publish skills (e.g., official Next.js, FastAPI, or Kubernetes capability modules).
- **Verified Badges**: High-trust badges for skills created and audited by verified ecosystem maintainers.

### 2. Semantic Versioning & Release Channels
- Skills versioned using Semantic Versioning (`v1.0.0`, `v1.1.0`).
- Configurable update streams: `latest` (auto-update) or `stable` (pinned).
- Changelogs and migration notes displayed directly in the Web Dashboard and Bob sidebar.

### 3. Community Ratings & Reviews
- Feedback system allowing developers to review, upvote, and discuss skills.
- Usage counter displaying total active developers and team subscribers.

### 4. Private / Air-Gapped Registries
- Self-hosted or air-gapped registry support for highly regulated financial and defense environments.

---

## 🧠 Phase 4: Intelligent Context & Adaptive Activation

### 1. Automated Stack Detection
- BobWay inspects root dependency files (`package.json`, `go.mod`, `pom.xml`, `requirements.txt`) upon project launch.
- Bob suggests recommended curated workspaces that match the exact language and library versions.

### 2. Dynamic Context Routing
- Context-sensitive skill activation:
  - If a developer opens a `.sql` or database schema file, database reliability skills activate automatically.
  - If an authentication or middleware file is opened, security guardrail skills take immediate priority.
- Keeps LLM context windows lean and focused on the relevant task.

---

## 📊 Summary Comparison

| Capability | Current Status | Planned Evolution |
| :--- | :--- | :--- |
| **Workspace Selection** | Manual via Web UI | Auto-detected from repository manifest (`bobway.json`) |
| **Team Distribution** | Individual key configuration | Automated Workspace Propagation across team |
| **Skill Publishing** | Web Dashboard | Directly inside Bob editor + Web UI |
| **Compliance Enforcing** | Opt-in per workspace | Mandatory enterprise guardrails via RBAC |
| **Marketplace Scope** | Curated platform skills | Open community registry with semantic versioning |
| **Skill Activation** | All workspace skills active | Smart dynamic routing based on open files |

---

*For suggestions or feature requests, visit the [BobWay Web Dashboard](https://skillsaas-web-route-skillsaas.apps.itz-gf8tqt.hub04-lb.techzone.ibm.com) or join our community discussions.*
