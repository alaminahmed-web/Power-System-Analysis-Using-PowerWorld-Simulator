# Power-System-Analysis-Using-PowerWorld-Simulator
Modeled multi-bus systems and performed load-flow studies Analyzed voltage profiles, real/reactive power flow, and system stability
# 7-Bus Power System Load Flow Analysis — PowerWorld Simulator

**Course:** SKEE 3443 Power System Analysis | Universiti Teknologi Malaysia  
**Semester:** 1 — 2025/2026  
**Lecturer:** Dr. Mohd Fadli Bin Rahmat

---

## Objective
Simulate a 7-bus power system to analyze steady-state behavior under heavy loading,
identify voltage violations, and design a corrective solution to improve voltage 
at the most critical bus (Bus 4) by 5%.

---

## System Description
- **7 buses** — generation and transmission zones
- **2 Generators:** Bus 1 (Slack Bus) | Bus 7 (PV Bus)
- **2 Step-up Transformers** + **5 Transmission Lines**
- **Loads:** Buses 2–6 | System Base: 100 MVA
- **Method:** Newton-Raphson Power Flow

---

## Case 1 — Base Case Results

| Parameter | Value |
|-----------|-------|
| Total Load | 250 MW / 150 Mvar |
| Total Generation | 250.54 MW / 160.68 Mvar |
| Active Power Loss | 0.54 MW |
| Reactive Power Loss | 10.68 Mvar |
| Critical Bus (Bus 4) Voltage | **0.9411 p.u.** ⚠️ |

**Root Cause of Voltage Drop at Bus 4:**
- Bus 4 is electrically furthest from both generators
- Heavy reactive demand (30 Mvar/bus) causes large I²X voltage drops
- Voltage drop governed by: ΔV = (RP + XQ) / V

---

## Case 2 — Voltage Improvement (Shunt Capacitor)

**Target:** 0.9411 × 1.05 = **0.9882 p.u.**

| Parameter | Value |
|-----------|-------|
| Solution | 92 Mvar Shunt Capacitor at Bus 4 |
| Achieved Voltage | **0.9879 p.u.** ✅ |
| Error vs Target | 0.03% |
| Reactive Generation (before) | 160.68 Mvar |
| Reactive Generation (after) | 62.48 Mvar |

---

## Key Findings
- Capacitor locally supplies reactive demand, reducing I×X drop across lines L2, L3, L5
- Generator reactive output reduced by ~61% — significant relief on the system
- Shunt capacitor compensation is an efficient, cost-effective voltage correction method

---

## Files

| File | Description |
|------|-------------|
| `Case1_Input_Bus.csv` | Load data: 50 MW / 30 Mvar per bus |
| `Case1_Input_Line&Transformer.csv` | R, X, B line parameters |
| `Case1_Output_Bus.csv` | Bus voltages — Base Case |
| `Case1_Output_Line&Transformer.csv` | Line flows — Base Case |
| `Case2_Input_Bus.csv` | Input with 92 Mvar capacitor at Bus 4 |
| `Case2_Input_Line&Transformer.csv` | Line parameters — Improved Case |
| `Case2_Output_Bus.csv` | Bus voltages — Improved Case |
| `Case2_Output_Line&Transformer.csv` | Line flows — Improved Case |

---

## Tools Used
- **PowerWorld Simulator** — System modeling & load flow
- **Newton-Raphson Method** — Power flow solution

---

## Authors
| Name | Matric No |
|------|-----------|
| Mohamed Alamin Ahmed Yousif Ahmed | A23KE0499 |
| Mohamad Haikal Bin Syuhaime | A23KE0194 |
| Shabiq Kasyfi Bin Sofhi | A23KE0472 |
| Muhammad Danish Bin Abd Halim | A23KE0223 |

