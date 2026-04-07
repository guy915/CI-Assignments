# Submission Feedback — Group 61 (Self-Assessment)

## Overall Feedback

Strong submission overall. The implementations are correct, the discussions are detailed and well-structured, and the scientific method is mostly solid. The main weaknesses are: (1) spelling/typo issues in several answers, (2) a formula notation error in Q5 and Q7 (minus sign instead of plus in the Q-learning equation written in text, even though the code is correct), (3) Q12 markdown was likely written based on buggy experimental results (alpha was not actually varied — the global override had no effect before the recent fix). Pen-and-paper answers (Q20–22) are submitted as images and could not be fully assessed here.

### Tops
- Excellent scientific rigour in Q16 (experimentally found and analytically derived the exact γ threshold)
- Very thorough discussions throughout Q6, Q7, Q9, Q10, Q11 with good comparison tables
- Both mazes consistently shown for all optimization questions (Q8, Q10, Q11, Q12)

### Tips
- Fix the typos in the text: "automonous", "th reward", "igrnore", "corectness", "theoritical", "demonstating" (Q18, Q52, Q64)
- Fix the formula in Q5 and Q7 answers: written as `Q(s,a) + α(r − γ·max Q(s',a') − Q(s,a))` but should be `Q(s,a) + α(r + γ·max Q(s',a') − Q(s,a))` — the code is correct but the text has a sign error
- Q12 results/discussion need to be re-run after the alpha bug fix — the claim that α=0.01 converges fastest is likely an artifact of the bug where alpha was always 0.1 regardless of the set value

---

## Question Scores

| Question | Max | Estimated Score | Notes |
|----------|-----|-----------------|-------|
| Q1 | 4 | 4/4 | All 3 strategies well explained, exploration strategy justified |
| Q2 | 3 | 3/3 | Cycle correctly described, each step motivated |
| Q3 | 2 | 2/2 | Stopping criterion verified with printed overshoot |
| Q4 | 4 | 4/4 | Non-learning shown, uncertainty bands, good discussion |
| Q5 | 2 | 1.5/2 | Implementation correct, but text uses wrong sign in formula |
| Q6 | 4 | 4/4 | Clear learning curves, uncertainty, thorough discussion |
| Q7 | 2 | 2/2 | Good comparison, references equations (same sign issue as Q5) |
| Q8 | 3 | 3/3 | 5 ε values, both mazes, good explanation |
| Q9 | 1 | 1/1 | Clear trade-off table + discussion |
| Q10 | 2 | 2/2 | 5 T values, both mazes, trade-offs discussed |
| Q11 | 2 | 2/2 | Rigorous comparison with bar chart, ε-greedy justified as winner |
| Q12 | 2 | 1/2 | Plots present, but discussion based on buggy results (α was not actually varied); needs re-run |
| Q13 | 1 | 1/1 | Correct explanation of smaller reward bias |
| Q14 | 2 | 2/2 | Correct SARSA analysis, good explanation why it makes things worse |
| Q15 | 3 | 3/3 | ε-decay implemented, literature referenced, plot shows convergence |
| Q16 | 2 | 2/2 | Correct γ ≈ 0.7937, derivation from Bellman equation, experimentally confirmed |
| Q17 | 1 | 1/1 | Multiple valid downsides listed |
| Q18 | 2 | 1.5/2 | Good drone example, discussion OK but some typos hurt clarity |
| Q19 | 2 | 2/2 | Two solid approaches: multi-objective reward + RLHF |
| Q20 | 3 | ?/3 | Submitted as image — cannot assess here |
| Q21 | 3 | ?/3 | Submitted as image — cannot assess here |
| Q22 | 2 | ?/2 | Submitted as image — cannot assess here |
| Q23 | 0 | 0/0 | Division of work table present |

**Questions total (excl. Q20–22): ~41/44**
**Questions total (incl. Q20–22, assuming ~6/8): ~47/52**

---

## General Rubric

### 1. Quality of the report
| Criterion | Score | Notes |
|-----------|-------|-------|
| Report structure | 6/6 | Well-structured, follows template throughout |
| Quality of answers | 5/6 | Clear and well-reasoned; formula sign error in Q5/Q7 |
| Quality of discussions | 6/6 | In-depth, references equations, includes tables |
| Quality of language | 3/6 | Several typos and grammar issues across Q18, Q52, Q64 |

**Points 1: ~5/6** (average: (6+5+6+3)/4 × ... → per rubric formula: (5+5+5+0)×0.25 = ~3.75/6... more like 4-4.5/6 given partial credit)

### 2. Quality of the code
| Criterion | Score | Notes |
|-----------|-------|-------|
| Code structure | 6/6 | Functions well-separated, helper functions reused |
| Quality of formatting | 5/6 | Generally clean, minor inconsistencies |
| Quality of documentation | 6/6 | Thorough docstrings on all major functions |
| Quality of implementation | 4/6 | Core is correct; alpha/gamma bug existed and was recently fixed |

**Points 2: ~5/6**

### 3. Scientific method
| Criterion | Score | Notes |
|-----------|-------|-------|
| Approach | 5/6 | Multiple runs, both mazes, varied parameters — solid methodology |
| Soundness | 4/6 | Generally sound but Q12 results unreliable before fix |
| Testing | 4/6 | Q3 verified; not much other explicit testing |
| Verification | 4/6 | Q16 is excellent; elsewhere verification is implicit |
| Argumentation | 5/6 | Mostly coherent, Q9/Q10 trade-off tables are well-argued |

**Points 3: ~4.5/6**

### 4. Visual aids
| Criterion | Score | Notes |
|-----------|-------|-------|
| Plotting methods | 6/6 | Line plots + shading + bar charts — all appropriate |
| Readability of plots | 5/6 | Clear titles, labels, xlim set; some subplots may be small |
| Correctness of plots | 5/6 | Both mazes shown; references in markdown present |

**Points 4: ~5/6** (missing: explicit captions on each subplot, not just titles)

### 5. Reproducibility
| Criterion | Score | Notes |
|-----------|-------|-------|
| Reliability of results | 4/6 | Seed set; 10 runs; Q12 results unreliable due to bug |
| Reliability of plots | 5/6 | Code for all plots present |
| Provenance of results | 5/6 | Report generally follows experiments; Q12 mismatch |

**Points 5: ~4.5/6**

---

## Totals (Estimated)

| Component | Points |
|-----------|--------|
| Questions (Q1–Q22, image Qs estimated at 6/8) | ~47/52 |
| General rubric (5 × ~4.7 avg) | ~23.5/30 |
| **Total** | **~70.5/82 (~86%)** |

---

## Priority fixes before submission

1. **Re-run Q12** after the alpha bug fix and rewrite the markdown to match actual results
2. **Fix formula sign** in Q5 and Q7 text (+ not − before γ)
3. **Fix typos**: "autonomous", "the reward", "ignore", "correctness", "theoretical", "demonstrating"
4. Verify pen-and-paper answers (Q20–22) are correctly attached and legible