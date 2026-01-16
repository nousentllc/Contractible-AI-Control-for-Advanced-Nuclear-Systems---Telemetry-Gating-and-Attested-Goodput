# Contractible AI Control for Advanced Nuclear Systems  
## Telemetry, Gating, and Attested Goodput

This repository contains the paper **“Contractible AI Control for Advanced Nuclear Systems: Telemetry, Gating, and Attested Goodput.”**  
It proposes a **conceptual, auditor-facing control and settlement framework** for SMR–AI co-control, where compute is treated as a millisecond-scale actuator (“sprints”) whose failure modes are cyber–physical, not merely IT.

The central objective is **contractibility**: define what must be **measured**, what must be **proven**, what must be **logged**, and what must be **priced** such that a third-party reviewer can replay gating decisions without access to proprietary model weights.

> **Epistemic status:** this is a *framework and contract-spec template*, not a validated safety case or operating procedure. Any deployment claim remains conditional on independent verification (simulation, hardware-in-the-loop, cybersecurity red-teaming, and audit replication).

---

## What’s inside

The paper formalizes a contractible SMR–AI co-control stack:

- **Observability contract:** minimum telemetry, sampling/synchronization, time-quality, and replay requirements for auditability.
- **Zero-trust admissibility gate:** compute commands “earn permission” via identity, segmentation, feasibility checks, and hard-deck constraints.
- **Physics-informed guardian:** DeepONet-style surrogate + anomaly logic to reject authenticated-but-physically-dangerous commands.
- **Operational hardening (Appendix):**
  - **Model Collateral Account (MCA):** oracle/guardian imperfections are priced state variables; premiums follow hazard and tail risk.
  - **Manifold projection:** outputs are projected onto physically consistent sets to reduce black-box/ODD risk.
  - **OTOC/echo-inspired instability proxy:** leading indicator for divergence that triggers **YELLOW** before thermal margin is consumed.
  - **Thermodynamic checksum:** anti-gaming anchor for goodput claims (goodput must reconcile against energy/work envelopes).
- **Attested Goodput PPA:** settlement on verified productive compute output (tokens/steps), not merely MWh.

---

## Related work / companion repo

This paper is designed to pair with **Compute-ASCDE** (reliability valuation + planning interface):

- **Compute-ASCDE repository:**  
  https://github.com/nousentllc/Compute-ASCDE-SMR---A-Reliability-Valuation-Planning-Interface

├── paper/
│   ├── Convergence.tex
│   ├── references.bib
├── pdf/
│   └── Contractible_AI_Control_for_Advanced_Nuclear_Systems___Telemetry__Gating__and_Attested_Goodput.pdf
├── LICENSE
└── README.md


Scope & non-goals

In scope
	•	Contractible interface definitions (telemetry → predicates → logs → replay → pricing).
	•	Auditor-facing operational primitives (collateral, certificates, degradation semantics).
	•	Settlement logic for goodput with anti-gaming anchors.

Not in scope
	•	NRC-grade safety case / certified operating procedure.
	•	Full plant transient validation suite or calibrated ROC curves.
	•	Implementation-ready cryptosystem or vendor-specific control integration.

  
If you want the clean “standard” setup for research repos, here are the two common patterns:

1) **Single-license repo (simple):**
- Everything (paper + code) uses the repository **LICENSE**.

2) **Dual-license repo (recommended):**
- **Code:** MIT (or Apache-2.0)
- **Paper/figures:** CC BY 4.0 (or CC BY-NC 4.0 if you want noncommercial restriction)
---
