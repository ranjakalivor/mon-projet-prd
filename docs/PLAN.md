# Plan : Analyse des avis clients Google Business

> PRD source : docs/PRD.md

## Décisions architecturales

Décisions durables qui s'appliquent à toutes les phases :

- **Plateforme** : application web pour ordinateur uniquement, 100 % navigateur. Le zip est lu et analysé côté client : aucun serveur, aucune base de données, aucun compte, rien conservé entre deux sessions.
- **Routes** : une seule page. Elle a deux états : « guide + chargement » puis « tableau de bord des quatre indicateurs ».
- **Entrée** : un seul zip Google Takeout à la fois ; charger un nouvel export remplace le précédent.
- **Modèle clé « Avis »** : note (1 à 5), date, commentaire, réponse du propriétaire (présente ou absente).
- **Périodes** : semaine courante = 7 jours glissants se terminant à la date de l'avis le plus récent de l'export ; semaine précédente = les 7 jours qui précèdent.
- **Thèmes** : liste fixe (pain, viennoiseries, accueil, attente, prix, propreté). Détection par mots-clés français. Polarité positive ou négative déduite de la note de l'avis.
- **Messages** : erreurs et états vides dédiés, en français, distincts les uns des autres.

---

## Phase 1 : Charger un zip valide et voir la note moyenne

**User stories** : US-2, US-3

### Ce qu'on livre

Le boulanger charge un zip d'export Google Takeout valide. L'outil lit les avis et affiche sur la page la note moyenne de la semaine courante, comparée à celle de la semaine précédente (hausse, baisse ou stable).

### Critères d'acceptation

- [ ] Un zip Takeout valide peut être chargé depuis la page.
- [ ] La note moyenne de la semaine courante s'affiche.
- [ ] La comparaison avec la semaine précédente indique clairement hausse, baisse ou stabilité.
- [ ] Sur un export de test de 50 avis, la note et sa comparaison correspondent au calcul manuel.

## Bloquée par

Aucune — démarrable immédiatement.

---

## Phase 2 : Nombre d'avis et comparaison

**User stories** : US-4

### Ce qu'on livre

La page affiche le nombre d'avis de la semaine courante, comparé à celui de la semaine précédente.

### Critères d'acceptation

- [ ] Le nombre d'avis de la semaine courante s'affiche.
- [ ] La comparaison avec la semaine précédente indique clairement hausse, baisse ou stabilité.
- [ ] Sur l'export de test de 50 avis, les chiffres correspondent au calcul manuel.

## Bloquée par

- Phase 1

---

## Phase 3 : Avis sans réponse

**User stories** : US-6, US-13

### Ce qu'on livre

La page affiche la liste des avis sans réponse du propriétaire. Quand tous les avis ont une réponse, un état clair le dit.

### Critères d'acceptation

- [ ] Chaque avis sans réponse apparaît dans la liste, avec sa note, sa date et son commentaire.
- [ ] Un avis avec réponse n'apparaît pas dans la liste.
- [ ] Si tous les avis ont une réponse, un message rassurant remplace la liste.
- [ ] Sur l'export de test de 50 avis, la liste correspond au calcul manuel.

## Bloquée par

- Phase 1

---

## Phase 4 : Thèmes récurrents positifs et négatifs

**User stories** : US-5, US-12

### Ce qu'on livre

La page affiche, pour chaque thème de la liste fixe, le nombre d'avis positifs et négatifs de la semaine courante, comparé à la semaine précédente. Un thème sans avis affiche un état « aucun avis » distinct d'une erreur.

### Critères d'acceptation

- [ ] Les six thèmes de la liste fixe sont présentés avec leurs comptes positifs et négatifs.
- [ ] Chaque thème montre l'évolution par rapport à la semaine précédente.
- [ ] Un thème sans aucun avis affiche « aucun avis », pas un message d'erreur.
- [ ] Sur l'export de test de 50 avis, les comptes par thème correspondent au calcul manuel.

## Bloquée par

- Phase 1

---

## Phase 5 : Guide d'export Google Takeout pas à pas

**User stories** : US-1

### Ce qu'on livre

Avant le chargement du zip, l'outil présente un guide pas à pas, intégré à la page, pour obtenir l'export Google Takeout du profil Google Business, avec accès direct à l'étape de chargement à la fin.

### Critères d'acceptation

- [ ] Le guide décrit chaque étape de l'export en langage simple, en français.
- [ ] Le boulanger peut avancer et revenir en arrière d'une étape à l'autre.
- [ ] La dernière étape mène au chargement du zip.
- [ ] Sur 3 boulangers testeurs, chacun réussit l'export et le chargement sans aide extérieure.

## Bloquée par

Aucune — démarrable immédiatement.

---

## Phase 6 : Erreurs et cas limites

**User stories** : US-9, US-10, US-11, US-14

### Ce qu'on livre

Chaque situation d'échec a un message dédié en français : fichier qui n'est pas un zip Takeout valide, export sans aucun avis, absence d'avis la semaine précédente (la comparaison n'est alors pas présentée comme trompeuse). Après une erreur, le boulanger peut refaire le chargement directement.

### Critères d'acceptation

- [ ] Un fichier invalide affiche un message qui explique quoi refaire.
- [ ] Un export sans avis affiche un message distinct, qui ne laisse pas croire à une panne.
- [ ] Sans avis la semaine précédente, les indicateurs indiquent l'absence de comparaison au lieu d'un écart trompeur.
- [ ] Après chaque erreur, un nouveau chargement est possible sans recommencer le parcours.

## Bloquée par

- Phase 1

---

## Phase 7 : Vue d'ensemble et rechargement hebdomadaire

**User stories** : US-7, US-8

### Ce qu'on livre

Les quatre indicateurs sont réunis sur une seule page lisible en un coup d'œil. Le boulanger peut recharger un nouvel export chaque semaine ; il remplace le précédent et tous les indicateurs se mettent à jour.

### Critères d'acceptation

- [ ] Les quatre indicateurs sont visibles ensemble sur une seule page, sur ordinateur.
- [ ] Recharger un nouvel export remplace entièrement les indicateurs précédents.
- [ ] Rien n'est conservé après fermeture de la page.
- [ ] Le parcours du chargement du zip à l'affichage des indicateurs prend moins de 2 minutes.
- [ ] Un avis sans réponse traité par le boulanger apparaît comme répondu à l'export suivant.

## Bloquée par

- Phase 2
- Phase 3
- Phase 4
