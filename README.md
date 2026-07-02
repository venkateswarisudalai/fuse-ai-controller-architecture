# Fuse.AI Controller — High-Level Reference Architecture

A single-page, high-level reference architecture for the **Fuse.AI Controller**, an AI-enabled
vehicle-grid integration (VGI) platform that lets EV fleets — and, over time, residential EVs —
operate as dispatchable distributed energy resources (bidirectional charge ⇅ discharge / V2G).

**Live diagram:** https://venkateswarisudalai.github.io/fuse-ai-controller-architecture/

The page is a self-contained `index.html` (no build step, no external assets). Every block is
click-to-expand to reveal what it does.

## What it covers

- **Field & edge** — EVs, chargers, site equipment, fleet operations
- **Ingestion** — OCPP (chargers) and telematics (vehicles), one adapter per asset type
- **Controller core** — rules engine, warranty-constraint manager, SoC tracking, dispatch engine,
  and the AI / optimization layer — separated by a **Control Authority Gate**
- **Real-time vs. planning loops** — a fast deterministic safety loop and a slower AI planning loop
- **Data & model platform** — time-series telemetry, feature/data lake, training & inference, audit log
- **Utility integration** — DERMS, OpenADR, IEEE 2030.5 (CSIP), demand-response, dispatch confirmation
- **Security** — identity/access, PKI/mTLS, segmentation, monitoring, vulnerability testing
- **Reporting** — operator/fleet dashboards and measurement & verification (M&V)

## Design intent

Conceptual and design-discussion grade — not implementation-ready. The organizing principle is the
boundary between **deterministic control (authority)** and **AI-based optimization (advisory)**:
the AI proposes plans; deterministic rules and OEM warranty constraints validate them before any
command reaches a charger; if the AI is unavailable or a plan is rejected, control falls back to a
safe rule-based schedule.
