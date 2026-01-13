# 🎯 Requirements & Contraintes
- The architecture must explicitly define φ, κ, and ε with inputs, outputs, and rules.
- External dependencies must be localized to the operator that relies on them (ε).
- The method must be applicable to its own repository without contradiction.

# 🔍 Research Findings
- [IA] Occurrence de termes anglais structurants dans plusieurs fichiers
  (ex: README.md, ARCHITECTURE.md, examples/).
  [H] Je constate que l’anglais est utilisé comme langue par défaut
  pour décrire la méthode, ce qui crée une distance cognitive
  et favorise le copier/coller sans appropriation.


# 🛠 Décisions Techniques
| Décision                                                  | Rationnel (Pourquoi ?)                                              |
| --------------------------------------------------------- | ------------------------------------------------------------------- |
| ARCHITECTURE.md is the single source of truth for φ, κ, ε | Avoid duplication and ambiguity between README and method documents |
| planning-with-files dependency localized in ε             | ε is the only operator relying on external execution discipline     |

# ⚠️ Issues & Blocages
| Problème rencontré | Résolution / Piste |
|------------------|-------------------|
| Mélange FR / EN dans un même document | Nécessite un lexique canonique avant toute traduction |

