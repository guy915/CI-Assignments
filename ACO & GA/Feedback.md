# Submission Feedback

## Overall Feedback
Strong technical work on both the genetic algorithm and ACO parts: the GA is well motivated in text and matches the code, and you go beyond the minimum by cross-checking the TSP tour with Held–Karp. The ACO section shows real engineering effort—intelligent ant variants, parameter sweeps, plots, and unit tests. The main gaps are **written** answers where the rubric expects explicit discussion (**Q19**, **Q22**) and a few places where notation or internal consistency could be tighter (**Q13–Q14**, **Q17** vs your own sweep story). Tighten the AI-use statement so it reflects *this* assignment, and revisit synthesis ACO settings if you want Part 2.7 to be scientifically convincing.

### Tops
- **Part 1:** Clear chromosome and operator story (permutation, inverse-distance fitness, roulette wheel, OX, swap mutation, elitism) aligned with [Main.ipynb](src/Main.ipynb).
- **Q10:** Reported tour length **1325**, convergence plot, and **Held–Karp** verification matching **1325**—excellent handling of “is it optimal?”
- **Part 2:** Multiple meaningful ACO upgrades (memory, loop pruning, smoothing, momentum, elitist reinforcement) with **before/after** style visuals and tests.
- **Q16:** Structured **OFAT** tuning, sweep plots, and honest note on missing parameter interactions.
- **Reproducibility:** Fixed **random seed** early; hyperparameters grouped at the top of cells; **`unittest`** coverage for core behaviour.
- **Deliverables:** Route files present for group **61** (`61_easy.txt`, `61_medium.txt`, `61_hard.txt` under `data/`).

### Tips
- **Q19:** Add a short markdown answer **after** the question: compare **optimal_tsp** vs **your ACO-built** distance matrix—tour length, visit order, and which you trust more (noise in ACO estimates, symmetry, etc.). Right now the heading jumps straight to code.
- **Q22:** The rubric asks for **text**: what to maximise/minimise, **all Pareto fronts**, and **NSGA-II** with four products—an image alone is hard to mark; embed the reasoning in the notebook.
- **Q13–Q14:** Clean up notation (e.g. consistent $\tau_{ij}$ on edges, avoid mixing $\tau_i$ and $\tau_{ij}$ in the same update). Fix small wording glitches (“depends is”, “total amount pheromones on link $i$”).
- **Q17:** Your **Q16** discussion favours **low** $\rho$ on medium/hard; **Q17** then suggests **moderate ~0.3** for complex mazes—reconcile or explain the apparent contradiction.
- **Q2 (point 3):** If Part 1 uses a precomputed symmetric matrix, justify asymmetry **only** for **your** ACO-estimated distances; otherwise the third difference may look weak to a strict grader.
- **AI statement:** Remove or rewrite references that do not apply here (e.g. **one-hot**, generic **“network”**); match Section 0’s transparency requirement to *this* submission (Held–Karp helper, plots, tests, etc.).
- **Synthesis block:** `gen = 1` and `no_gen = 1` for `AntColonyOptimization` when building `my_tsp` is almost certainly too weak to learn reliable pairwise distances—raise these if you want Part 2.7 to be credible.
- **Deliverable naming:** The brief asks for `<group>_actions_TSP.txt`; you write `tsp_solution.txt`—confirm with the course whether that name is acceptable.
- **Language pass:** Typos in Q3 (“compuatation”, “tacking”, “regiaons”) and a redundant sentence fragment—quick edit for professionalism.

---

## Question Scores

| Section | Score |
|---------|-------|
| 1.1 Problem analysis (Q1–Q3) | 6/6 |
| 1.2 Genetic algorithm (Q4–Q10) | 15/15 |
| 2.2–2.4 ACO observation & upgrades (Q11–Q15) | 9/11 |
| 2.5–2.7 Tuning, routes & synthesis (Q16–Q19) | 5/8 |
| 3.1–3.2 Open & pen-and-paper (Q20–Q22) | 5/8 |

**Questions total:** 40/46

*Notes: Q13–Q14 each −1 for notation/clarity vs “fully correct equation”; Q19 −2 (no comparative discussion); Q22 −3 (image-only vs required written justification); Q17 −1 (ρ discussion inconsistent with your sweep narrative). Q18 is 0 pt in the rubric (working code / routes—treated as satisfied given outputs and route files).*

---

## General Rubric

### Quality of the report
| Criterion | Score |
|-----------|-------|
| Report structure | 6/6 |
| Quality of answers | 5/6 |
| Quality of discussions | 5/6 |
| Quality of language | 4/6 |

**Points 1:** 5.0

### Quality of the code
| Criterion | Score |
|-----------|-------|
| Code structure | 6/6 |
| Quality of formatting | 5/6 |
| Quality of documentation | 5/6 |
| Quality of implementation | 6/6 |
| Adherence to constraints (NumPy-only core, no disallowed search) | 6/6 |

**Points 2:** 5.6

### Scientific method
| Criterion | Score |
|-----------|-------|
| Approach | 6/6 |
| Soundness | 4/6 |
| Testing | 6/6 |
| Verification | 6/6 |
| Argumentation | 4/6 |

**Points 3:** 5.2

### Visual aids
| Criterion | Score |
|-----------|-------|
| Plotting methods | 6/6 |
| Readability of plots | 5/6 |
| Correctness of plots | 6/6 |

**Points 4:** 5.7

### Reproducibility
| Criterion | Score |
|-----------|-------|
| Reliability of results | 5/6 |
| Reliability of plots | 5/6 |
| Provenance of results | 5/6 |

**Points 5:** 5.0

---

## Totals

| Component | Points |
|-----------|--------|
| Questions (Q1–Q22) | 40/46 |
| General rubric | 26.5/30 |
| **Total** | **66.5/76** |

*General rubric subtotal = sum of Points 1–5 (each the mean of its sub-criteria, on a 0–6 scale): 5.0 + 5.6 + 5.2 + 5.7 + 5.0 = 26.5.*
