---
code: "G\xC9N\xC9R-012"
locale: fr
category_slug: "g\xE9n\xE9ral"
collections:
- homepage
tags:
- darna document master final corrige
is_featured: false
display_order: 130
status: published
question: "4.2. R\xE8gles de Calcul de Criticit\xE9"
answer: |
  **Formule de Calcul :**
  ```
  Score = (Score_Remplacement × 0.4) + (Score_Dépendances × 0.3) + (Score_Complexité × 0.2) + (Score_Validité × 0.1)
  ```
  
  **Facteurs de Pondération :**
  
  | Facteur | Pondération | Critères d'Évaluation |
  |:--------|:------------|:----------------------|
  | **Difficulté de Remplacement** | 40% | Non refaisable = 40 pts, Délai > 60j = 30 pts, Délai > 30j = 20 pts, Autres = 10 pts |
  | **Impact Dépendances** | 30% | Nombre de documents dépendants × 5 pts |
  | **Complexité d'Obtention** | 20% | Complexité (1-5) × 4 pts |
  | **Durée de Validité** | 10% | Validité < 12 mois = 10 pts, Autres = 0 pt |
  
---
