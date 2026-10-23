# Analyse des avis clients Google Business

## Stack
Application web 100 % navigateur, desktop uniquement : pas de serveur, de base de données ni de compte.

## Documents projet
Toujours lire ces documents avant de coder :
- @docs/PRD.md — pourquoi et quoi du produit
- @docs/PLAN.md — phases d'implémentation et user stories
- @docs/DESIGN.md — système design et direction visuelle

## Système design
Toujours lire DESIGN.md avant toute décision visuelle ou UI.
Polices, couleurs, espacements et direction esthétique y sont définis.
Ne pas dévier sans validation explicite.
En mode QA, signaler tout code qui ne respecte pas DESIGN.md.

## Conventions
- Tout est calculé côté client depuis le zip ; rien n'est persisté entre sessions.
- Semaine courante = 7 jours glissants finissant à la date de l'avis le plus récent de l'export, pas à aujourd'hui.
- Thèmes : liste fixe, détection par mots-clés français, polarité déduite de la note.
- Chaque erreur et chaque état vide a son message français dédié, jamais un message générique.
- Terracotta `#C2410C` réservé aux CTA et états actifs.

## Jargon métier
- **Export Takeout** : zip Google Takeout du profil Google Business, seule source de données.
- **Semaine courante / précédente** : les deux fenêtres de 7 jours comparées sur chaque indicateur.
- **Thème** : l'un des six sujets fixes (pain, viennoiseries, accueil, attente, prix, propreté).
