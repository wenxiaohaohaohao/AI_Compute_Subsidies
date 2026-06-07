# NEV Model Project

**Project title:**
State-Contingent Industrial Policy, Local Competition, and Aggregate Misallocation:
Evidence from China's NEV Industry

---

## Core workflow

```text
discussion
→ identify module (01–08)
→ update only that module
→ label content status inside the module
→ if a modeling decision is resolved → update 99_decision_log
→ when module is stable → update 00_MASTER (accepted baseline only)
→ MASTER stable → paper section / Julia code
```

## Module map

| File | Scope |
|---|---|
| `00_MASTER_model_memo.md` | Current accepted baseline (English, paper-ready) |
| `01_research_mechanism.md` | Research question + mechanism + involution definition |
| `02_environment_firms.md` | Environment + household + firms + LBD |
| `03_government_game.md` | Local government objective + Markov-Nash game |
| `04_planner_equilibrium.md` | Planner problem + full equilibrium definition (8 conditions) |
| `05_quantification_solution.md` | Calibration moments + solution algorithm |
| `06_counterfactuals.md` | 5 counterfactual groups |
| `07_literature_positioning.md` | Literature positioning for JMP |
| `08_extensions.md` | Extensions explicitly outside baseline |
| `99_decision_log.md` | All accepted and rejected modeling decisions |

## Key rules

- MASTER receives only **accepted baseline** content. No alternatives, no open questions.
- Content status labels inside module notes:
  `[Accepted baseline]` / `[Alternative]` / `[Open question]` / `[Rejected]` / `[Main-text candidate]` / `[Appendix candidate]`
- Do not rewrite the entire model after every discussion. Update the relevant module only.
- `paper_draft/` and `code_plan/` will be created after the model is stable.
