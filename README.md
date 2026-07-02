# Fuse.AI Controller — Proposed Architecture

An interactive, single-page architecture proposal for the **Fuse.AI Controller**, an AI-enabled
vehicle-grid integration platform that lets EV fleets operate as dispatchable grid resources
(bidirectional charge ⇅ discharge / V2G).

**Live:** https://venkateswarisudalai.github.io/fuse-ai-controller-architecture/

Self-contained `index.html` — no build step, no external assets. Click any block to open a detail
panel; run the failure scenarios; print for a static copy.

## The thesis

**AI only forecasts.** A deterministic solver builds the schedule, a rules gate re-checks every
command at issue time, and certified site hardware is the last line. AI never touches a command path.

## What's in it

- **Layered diagram** — external world → AI forecasts → optimizer (MILP/MPC) → rules gate →
  site edge → field hardware, with data & M&V and security rails down each side, and a certified
  hardware floor (UL 1741 SB / IEEE 1547).
- **Interactive detail panels** on every block (protocols, sizing, tiered constraint model).
- **Failure walk-throughs** — *Cloud dies*, *60-second DERMS dispatch*, *Impossible night*
  (infeasibility handled with an irreducible infeasible subset, not an AI retry loop).
- **"One van, three moments"** mini-demo — charge / discharge / protect-departure.
- **Design honesty** — assumptions taken, scope cuts for the deadline, and why AI-in-a-loop was
  rejected as the primary mechanism.

Discussion draft for the Fuse Power Management Senior AI Engineer exercise.
