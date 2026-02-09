# Benchmark Reservoir Geomechanics
**Integrating SCAL Derived Flow Properties, MEM at Screening Level, and Fault Reactivation Sensitivity (SPE3–SPE9)**

---

## Overview

This repository presents a **reproducible screening level reservoir geomechanics workflow** built on SPE benchmark models. The project integrates:

- **SCAL parameterization and uncertainty screening**
- **Pressure driven Mechanical Earth Modeling (MEM)**
- **Stress sensitive rock property response**
- **Fault reactivation screening under stress regime and friction uncertainty**

This project is to demonstrate how flow uncertainty, stress evolution, and structural stability can be evaluated coherently using public benchmark data and physics based assumptions.

> **Key idea:**  
> SCAL uncertainty primarily controls multiphase flow behavior, while MEM and fault stability screening constrain geomechanical risk under pressure perturbations.

---

## Why this project matters

In practice, many reservoir studies begin without sufficient data or resources for fully coupled flow geomechanics simulation. Industry workflows therefore rely on screening level analysis to:

- identify dominant sensitivities,
- bound uncertainty,
- and decide whether more complex coupling is justified.

This project mirrors that reality using **SPE3 (flow & pressure)** and **SPE9 style (faulted structure)** benchmark concepts, making it directly relevant to reservoir engineering and geomechanics workflows used in industry.

---

## Workflow summary

SCAL Tables (SWOF / SGOF)
│
├─► Quality control
│ - Corey parameterization (endpoints, exponents)
│ - Monotonic interpolation (PCHIP)
│
├─► SCAL uncertainty screening
│ - Endpoint & exponent perturbations
│ - Mobility indices (I_WO, I_GO)
│
├─► Pressure history (benchmark-derived)
│
├─► Screening Mechanical Earth Model (MEM)
│ - Stress gradients (Sv, SHmax, Shmin)
│ - Effective stress evolution (σ′ = σ − αPp)
│ - Stress-sensitive k / φ (pseudo-coupling)
│
└─► Fault stability screening (SPE9-style)
- Coulomb failure & slip tendency
- Stress regime bracketing (normal vs strike-slip)
- Orientation sweep (dip/strike)
- Friction sensitivity (μ)
- Critical pressure for reactivation (ΔPcrit)

---

## Key results

### 1.SCAL sensitivity (flow-dominated uncertainty)

- Water–oil mobility (I_WO) is dominated by SWOF parameters (Sor, nw).
- Gas–oil mobility (I_GO) is dominated by SGOF parameters (Sorg, ng).
- Cross-system influence is negligible in screening metrics.

SCAL uncertainty is a **first order control on flow behavior**.

---

### 2.Screening MEM response (pressure then stress)

- Effective vertical stress variation from SPE3 pressure history is < 1 MPa.
- Stress sensitive permeability and porosity changes are < 0.003% under screening coefficients.

For this benchmark pressure range, geomechanical property changes are secondary to SCAL uncertainty.

---

### 3.Fault stability screening (structural risk)

- Fault reactivation risk is governed by:
  - stress regime,
  - fault orientation,
  - friction coefficient μ,
  - pore pressure change.
- Strike-slip regime consistently yields lower ΔPcrit than normal faulting.
- Worst-case ΔPcrit (strike-slip):
  - ~19 MPa for μ = 0.6
  - ~10 MPa for μ = 0.4

Friction uncertainty is first order, and regime bracketing is essential in screening studies.

---

## Repository structure
benchmark-reservoir-geomechanics/
- `notebooks/` : SCAL_SPE3.ipynb, SCAL_SPE9.ipynb  
- `figures/` : Final figures used in paper
- `results/` : CSV summaries (RMSE, mobility, ΔPcrit)
- `data/` : Small reference tables (no binaries)
- `README.md`

---

## Assumptions & scope

This project is intentionally **screening-level**:

- Stress magnitudes are derived from **assumed gradients**, not field calibration.
- Fault pressure is treated as **uniform** for stability screening.
- SCAL sensitivity uses **mobility indices**, not full production forecasts.
- **Fully coupled flow–geomechanics** is identified as future work.

All assumptions are documented in `docs/assumptions.md`.

---

## Reproducibility

- All calculations are performed in **Python / Jupyter**.
- No proprietary data or software required.
- Environment files provided for local execution.
- All figures are generated directly from notebooks.

---

## Future work

- Fully coupled Flow–Geomechanics (e.g., SPE9 with OPM Flow)
- Spatial stress gradients and compartmentalized pressure
- Caprock integrity and fracture gradient screening
- Field-calibrated MEM inputs

---

## Author
**Imas Viestawati**
Geological Engineering
Interests: reservoir geomechanics, structural geology, geoenergy data science
give star!!
