# Semiconductor Junction Simulation — Phase 3

An interactive, browser-based semiconductor physics simulation covering **PN Junction** and **BJT Transistor** behavior. Built with vanilla HTML/CSS/JS — no external libraries or frameworks required.

Open `phase3_junction_sim.html` directly in any modern browser. No installation or server needed.
---
https://metehanalp07.github.io/Semiconductor-Junction-Simulation/phase3_junction_sim.html
---

## ✨ Features

### PN Junction Mode
- **Equilibrium** — drift/diffusion balance, zero net current
- **Forward Bias** — minority carrier injection, barrier reduction, W_d decrease
- **Reverse Bias** — barrier increase, W_d expansion, leakage current only
- **Breakdown** — Avalanche (N < 5×10¹⁷ cm⁻³) and Zener (N > 5×10¹⁷ cm⁻³) with temperature coefficients
- Animated majority/minority carrier particles with recombination flashes

### BJT Transistor Mode (NPN & PNP)
- **Forward Active** — amplification, I_C ≈ βI_B
- **Saturation** — both junctions forward biased, V_CE ≈ 0.2V
- **Cutoff** — both junctions reverse biased, leakage only
- **Reverse Active** — swapped roles, reduced β_R
- Real-time Ebers-Moll terminal currents (I_E, I_B, I_C)
- Adjustable base width W_B (0.1 μm – 5.0 μm)

### Real-Time Graphs (clickable to expand)
| Graph | Description |
|-------|-------------|
| I-V Curve | Shockley diode equation with operating point |
| Energy Band Diagram | Ec, Ev bending, quasi-Fermi levels under bias |
| Charge Density ρ(x) / BJT Transfer | Depletion charge profile / I_C vs V_BE |
| Electric Field E(x) / BJT Output | Triangular E-field profile / I_C vs V_CE |

### Adjustable Parameters
- **Nₐ, Nᴅ** — acceptor/donor doping (10¹⁵ – 10¹⁸ cm⁻³)
- **Vₐ** — applied voltage (−10 V to +1 V for PN)
- **V_BE, V_CB** — BJT junction voltages (fine-tunable sliders)
- **W_B** — base width
- **Temperature** — 300 K / 450 K toggle
- **Animation speed** — 0.25× to 5×

---

## 🧮 Physics & Formulas

All formulas are from standard Si device physics textbooks (Neamen, Streetman).

| Quantity | Formula |
|----------|---------|
| Thermal voltage | V_T = kT/q |
| Built-in voltage | V₀ = V_T · ln(NₐNᴅ/nᵢ²) |
| Depletion width | W_d = √(2εₛε₀(Nₐ+Nᴅ)(V₀−Vₐ) / qNₐNᴅ) |
| Max electric field | E_max = 2(V₀−Vₐ) / W_d |
| Junction capacitance | C_j = εₛε₀ / W_d |
| Saturation current | J₀ = qnᵢ²(Dₙ/LₙNₐ + Dₚ/LₚNᴅ) |
| Shockley equation | J = J₀(e^(V/V_T) − 1) |
| Einstein relation | D = μ · kT/q |
| Base transport factor | α_T = 1/cosh(W_B/L_nB) |
| Ebers-Moll I_C | I_C = αF·J₀E·(e^(V_BE/V_T)−1) − J₀C·(e^(V_CB/V_T)−1) |
| Intrinsic carrier conc. | nᵢ(T) = 1.5×10¹⁰·(T/300)^1.5·exp(−Eg/2k·(1/T−1/300)) |
| Mobility (Arora model) | μ = μ_min + (μ_max−μ_min)/(1+(N/N_ref)^0.88) |
| Breakdown voltage | V_BR ≈ 60·(Eg/1.1)^1.5·(N/10¹⁶)^−0.75 |

**Silicon constants used:**
- εₛ = 11.7 · ε₀
- nᵢ(300K) = 1.5 × 10¹⁰ cm⁻³
- Eg(300K) = 1.12 eV
- τ (carrier lifetime) = 1 μs

---

## 📁 File Structure

```
phase3_junction_sim.html   ← entire simulation (single file, self-contained)
README.md
```

---

## 🔗 Related

- **Phase 1 & 2** — Drift/diffusion currents, doping profiles, basic PN junction visualization

---

## 🛠️ Development

Built with:
- Vanilla HTML5 Canvas (2D rendering)
- CSS custom properties + JetBrains Mono / Space Grotesk fonts
- Zero dependencies — runs entirely in-browser

> **Note on AI tooling:** Claude (Anthropic) was used as a development tool throughout this project. Physics formulas, design decisions, and debugging were handled collaboratively.

---

## 📄 License

MIT License — free to use, modify, and share with attribution.

---

*Developed by Metehan Alp Ünal — Sabancı University, Electronics & Mechatronics Engineering*
