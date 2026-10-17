# Euler Vacuum Seed

Frozen blind-tested galactic dynamics + vacuum-seed cosmology: papers, data, and replication package.

A conditional cosmological framework (Euler Vacuum Seed) with a frozen zero-parameter galactic partition law, blind-validated on SPARC (126/160, p = 6.3e-14, 7.2σ) and LITTLE THINGS dwarfs (per-radius, 337 pts), with full failure tables, intrinsic-scatter discipline, per-point residuals, and a frozen parameter set. Includes the quantum companion (Φ_q, g−2), the Koide audit, the kill series, and a step-by-step replication protocol.

## Contents

| File | What it is |
|---|---|
| `papers/euler_vacuum_seed_v8.pdf` (+ `.tex`) | Main working paper v8 (radial suppression, phenomenological) |
| `papers/universe_foundations_v5.pdf` (+ `.tex`) | Foundations companion (postulates, budget, reading) |
| `papers/quantum_phi_draft.pdf` (+ `.tex`) | Quantum companion (same kernel, ħ,G free; g−2) |
| `supplement/supplement_protocol.md` | Replication protocol — rerun the frozen law in ~50 lines |
| `supplement/supplement_residuals.csv` | Per-point residuals, all 3391 SPARC points |
| `supplement/supplement_FROZEN.json` | Frozen parameter set (machine-readable) |
| `supplement/koide_audit.md` | Koide relation audit + exclusions + status |
| `supplement/kill_series.md` | The null forms that were tried and killed |

## Frozen protocol (one paragraph)

Features: `lL = log10(L3.6/Lsun)`, `eta_HI = (MHI/Msun)/(L3.6/Lsun)`, Υ* = 0.5.
Model, zero per-galaxy parameters:
`V = sqrt(Vbar^2 + C(L)·Φ·(1 − e^(−r/λ)))`,
`Φ = sigmoid(a·lL + b·η_HI + c)`, `C(L) = 2800·L9^0.525`,
with `a = 0.525`, `b = 0.242`, `c = 1.07`, `λ = 1 kpc`.
Data: public SPARC/VizieR J/AJ/152/157.

## Headline results (honest version)

- Frozen flat form vs Vbar-only: **126/160** unseen galaxies, p = 6.3e-14 (7.2σ).
- Radial Yukawa suppression (λ = 1 kpc, picked once): blind RMSE **9.45** vs 10.02, wins **133/160** — disclosed as quasi-blind (form family selected on the same trainval).
- LITTLE THINGS per-radius (independent sky, pre-registered form, no refit): Yukawa **13.0** vs flat 14.9 — same direction.
- vs RAR (SPARC-full): **10.43 vs 12.67**; on LITTLE THINGS dwarfs RAR wins (11.6 vs 13.0) — sample-dependent contest, both directions filed.
- vs per-galaxy NFW: **0/30 losses kept** (350 vs 4 params).
- All comparisons hold modulo ~24 km/s intrinsic scatter (median): the law fits exactly nowhere; it points the right direction.
- Quantum companion: e −1.50%, μ +1.38%, blind τ +1.34% (one global constant, no QED loops).
- Koide: audited, exclusions filed, origin treated as brute fact (see `koide_audit.md`).

## Reproduction

See `supplement/supplement_protocol.md`. Requires only Python + numpy + the public SPARC table. Expected reproduction: all numbers in `supplement_residuals.csv`.

## License

- **Papers, figures, and supplementary text**: CC-BY-4.0
- **Code snippets in the protocol**: MIT

## Contact

Lucas E. J. da Silva (n4rus) — independent researcher — GitHub: [n4rus](https://github.com/n4rus)
