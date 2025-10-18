---
code: "G\xC9N\xC9R-011"
locale: fr
category_slug: "g\xE9n\xE9ral"
collections:
- homepage
tags:
- darna document master final corrige
is_featured: false
display_order: 120
status: published
question: "4.1. Algorithme de V\xE9rification d'Habilitation"
answer: |
  ```
  FONCTION verifier_habilitation(document, demandeur, beneficiaire):
      
      // Vérifier le statut du bénéficiaire
      SI beneficiaire.age < 18:
          RETOURNER verifier_mineur(document, demandeur, beneficiaire)
      
      SI beneficiaire.protection_juridique:
          RETOURNER verifier_majeur_protege(document, demandeur, beneficiaire)
      
      SI beneficiaire.situation == "detenu":
          RETOURNER verifier_detenu(document, demandeur, beneficiaire)
      
      SI beneficiaire.statut == "decede":
          RETOURNER verifier_succession(document, demandeur, beneficiaire)
      
      // Vérifier l'habilitation du demandeur selon le document
      habilitation = document.habilitation_requise
      
      SI habilitation CONTIENT "P": // Personne uniquement
          SI demandeur.id == beneficiaire.id:
              RETOURNER VRAI
      
      SI habilitation CONTIENT "F": // Famille directe
          SI verifier_lien_familial(demandeur, beneficiaire):
              RETOURNER VRAI
      
      SI habilitation CONTIENT "T": // Tiers avec procuration
          SI verifier_procuration(demandeur, beneficiaire, document):
              RETOURNER VRAI
      
      SI habilitation CONTIENT "A": // Avocat/Notaire
          SI verifier_mandat_professionnel(demandeur, beneficiaire):
              RETOURNER VRAI
      
      SI habilitation CONTIENT "R": // Représentant légal
          SI verifier_representation_legale(demandeur, beneficiaire):
              RETOURNER VRAI
      
      RETOURNER FAUX
  ```
  
---
