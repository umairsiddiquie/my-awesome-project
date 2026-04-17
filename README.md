# MAP
# 🔐 Pairing-Friendly Curves — Security Audit Suite

**Live app:** https://8080-ij88gam1xn1uiog7q5eru-c81df28e.sandbox.novita.ai

Built from all three of your uploaded sources (comparison PDF, Optimizing Pairing Security PDF, and the Pairing Curves & zk-SNARKs video).

## 📋 Project Structure

This repository contains a comprehensive security audit suite for pairing-friendly elliptic curves used in cryptographic applications, particularly in zk-SNARKs and other zero-knowledge protocols.

### Tabs Overview

#### Tab 1 — 🔍 Audit Checklist
A one-page red/yellow/green matrix with 13 cards across severity tiers, featuring:
- Traffic-light indicators (🔴 Critical / 🟡 Warning / 🟢 Pass)
- Live risk meter
- Filter buttons by:
  - **Severity**: 🔴 Critical / 🟡 Warning / 🟢 Pass
  - **Group**: G₁ / G₂ / G_T
  - **Curve**: BN254 / BLS12-381

**Key Critical Findings:**
| 🔴 CRITICAL (6) | Key Issue |
|---|---|
| G₁ On-Curve Membership | Never trust deserialized point without curve equation check |
| G₂ Subgroup Test | Use `ψ(Q)=[u]Q`, NOT `[r]Q` (4× faster, proven safe) |
| G_T Cyclotomic Test | `w·w^(p⁴) = w^(p²)` before any G_T element is trusted |
| BLS12-381 Cofactor Clearing | Use `u-1` not full `(u-1)²/3`; abort if result is 𝒪 |
| BN254 Exceptional Seed | Compute INTEGER gcd at seed u — polynomial gcd alone is a security failure |
| BN254 TNFS Downgrade | ~100 bits, NOT 128 — update all security docs immediately |

#### Tab 2 — 📊 Call Graph
Interactive SVG call graph showing:
- Transaction Bytes → Parse → Queue → Rust FFI → Batch Validate → Consensus Failure
- Hover tooltips with description + exact file/line references
- Click to pin a node
- Layer filter dropdown (Parse / Queue / Rust FFI / Validate / Consensus)
- Failure edges highlighted in red

#### Tab 3 — 📋 Curves Table
Sortable/searchable comparison of 10 curves (BLS12-381, BN254, BW13-P310, BW19-P286, Pallas, Vesta, KSS16, BLS24, BLS48) with embedding degree chips, security levels, and cofactor info.

#### Tab 4 — ⚔️ Attack Models
8 threat cards: Small Subgroup, Exceptional Seed, TNFS Downgrade, Twist Confusion, Cache Replay, Batch Poisoning, Hash-to-Curve Skip, GLV Endomorphism — each with mitigations.

#### Tab 5 — ∑ Math Reference
Rendered equations for all 6 core constructions:
- Group structure polynomials
- GLV/Frobenius membership tests
- Cyclotomic G_T test
- Construction 6.6 cofactor clearing table
- The HGP Criterion

## 🛠️ Setup & Development

### Prerequisites
- Node.js (v18+)
- npm or yarn
- Git

### Installation
```bash
git clone https://github.com/umairsiddiquie/my-awesome-project.git
cd my-awesome-project
npm install
```

### Running the App
```bash
npm run dev
```

### Deployment
The live app is hosted at: https://8080-ij88gam1xn1uiog7q5eru-c81df28e.sandbox.novita.ai

## 📚 License
This project is licensed under the **Creative Commons Attribution 4.0 International License** (CC BY 4.0), as used in my academic publications.

Copyright © 2026 Umair Abbas Siddiquie. All rights reserved.

## 📬 Contact
For questions or collaboration opportunities, please contact:
- Email: umair.siddiquie@gmail.com
- GitHub: https://github.com/trizist/chronal-ruler
- LinkedIn: Umair Abbas — AI Ethics & Web3 Architect
- Twitter: @umairsiddiquie_

---

**Note:** This project is part of my broader research on quantum engineering, secure communication networks, and foundational physics. It integrates concepts from my dissertation "Quantum Tunnelling and the Architecture of the Cosmos" and my ongoing work on "The Chronal Ruler: Mapping the Geometry of Time."
