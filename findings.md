# 🎯 Requirements & Contraintes
- The architecture must explicitly define φ, κ, and ε with inputs, outputs, and rules.
- External dependencies must be localized to the operator that relies on them (ε).
- The method must be applicable to its own repository without contradiction.

# 🔍 Research Findings
- Planning-with-files requires that execution artifacts (findings, progress) record events, not rules.
  Source: https://github.com/OthmanAdi/planning-with-files/blob/master/docs/quickstart.md
- The combination of task_plan.md + progress.md + findings.md is sufficient
  to restore execution context after an interruption.
- The 5-question reboot table provides a fast mental rehydration of the sprint state.
- An external reader can reconstruct the full execution chain (φ → κ → ε)
  using only README.md, ARCHITECTURE.md, and the example file.


# 🛠 Décisions Techniques
| Décision                                                  | Rationnel (Pourquoi ?)                                              |
| --------------------------------------------------------- | ------------------------------------------------------------------- |
| ARCHITECTURE.md is the single source of truth for φ, κ, ε | Avoid duplication and ambiguity between README and method documents |
| planning-with-files dependency localized in ε             | ε is the only operator relying on external execution discipline     |

# ⚠️ Issues & Blocages
| Problème rencontré                                     | Résolution / Piste                       |
| ------------------------------------------------------ | ---------------------------------------- |
| Ambiguity about where to reference planning-with-files | Dependency localized inside ε definition |
| Uncertainty about next action after interruption | Reboot test clarifies current phase and next step |
