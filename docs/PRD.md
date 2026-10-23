## Problème
Un boulanger indépendant reçoit des avis clients sur son profil Google Business. Il les lit un par un, sans jamais voir la vue d'ensemble : il ne sait pas si sa note progresse ou baisse, ni quels sujets reviennent dans les commentaires. Des problèmes récurrents de service client passent donc inaperçus, et des avis restent sans réponse. Il a besoin de voir en un coup d'œil des indicateurs qui lui permettent de mieux piloter son entreprise et d'améliorer son service client.

## Solution
Le boulanger charge le zip d'export de son profil Google Business obtenu via Google Takeout. L'outil le guide pas à pas pour obtenir cet export. Il affiche ensuite sur une seule page quatre indicateurs, chacun comparé à la semaine précédente :
- la note moyenne ;
- le nombre d'avis ;
- les thèmes récurrents dans les commentaires, positifs et négatifs, sur une liste fixe ;
- les avis sans réponse.

À terme, les avis seront récupérés automatiquement, sans passer par l'export.

## Utilisateur cible
Un boulanger indépendant, propriétaire d'une seule boutique, seul ou avec quelques salariés. Il n'est pas à l'aise avec les outils numériques et gère lui-même son profil Google Business. Il consulte l'outil sur ordinateur, une fois par semaine, en fin de journée ou le week-end.

## User Stories
1. US-1 : En tant que boulanger, je veux être guidé pas à pas pour obtenir l'export Google Takeout de mon profil Google Business, afin de réussir l'export sans aide extérieure.
2. US-2 : En tant que boulanger, je veux charger le zip d'export, afin que l'outil analyse mes avis.
3. US-3 : En tant que boulanger, je veux voir ma note moyenne comparée à celle de la semaine précédente, afin de savoir si elle progresse ou baisse.
4. US-4 : En tant que boulanger, je veux voir le nombre d'avis comparé à celui de la semaine précédente, afin de savoir si l'activité d'avis monte ou baisse.
5. US-5 : En tant que boulanger, je veux voir les thèmes récurrents des commentaires, positifs et négatifs, comparés à la semaine précédente, afin de repérer ce qui revient et ce qui s'aggrave.
6. US-6 : En tant que boulanger, je veux voir la liste des avis sans réponse, afin de savoir à quels clients répondre.
7. US-7 : En tant que boulanger, je veux voir les quatre indicateurs sur une seule page, afin de comprendre ma situation en un coup d'œil.
8. US-8 : En tant que boulanger, je veux recharger un nouvel export chaque semaine, afin d'obtenir des indicateurs à jour.
9. US-9 : En tant que boulanger, je veux un message clair si le fichier chargé n'est pas un zip d'export Google Takeout valide, afin de comprendre quoi refaire.
10. US-10 : En tant que boulanger, je veux un message clair si l'export ne contient aucun avis, afin de ne pas croire à une panne de l'outil.
11. US-11 : En tant que boulanger, je veux savoir quand il n'y a pas d'avis la semaine précédente, afin de ne pas lire une comparaison trompeuse.
12. US-12 : En tant que boulanger, je veux voir un état clair quand aucun avis ne correspond à un thème, afin de ne pas confondre « aucun » et « erreur ».
13. US-13 : En tant que boulanger, je veux voir un état clair quand tous mes avis ont une réponse, afin d'être rassuré.
14. US-14 : En tant que boulanger, je veux pouvoir refaire le chargement après une erreur, afin de ne pas tout recommencer.

## Critères de succès
1. Le boulanger passe du chargement du zip à l'affichage des indicateurs en moins de 2 minutes.
2. Sur 3 boulangers testeurs, chacun réussit l'export Google Takeout et le chargement du zip sans aide extérieure, en suivant seulement le guide de l'outil.
3. Sur un export de test de 50 avis, les 4 indicateurs affichés correspondent aux chiffres calculés à la main.
4. Après avoir consulté l'outil, le boulanger répond à au moins un avis sans réponse : cet avis apparaît comme répondu à l'export suivant.

## Hors périmètre
- Récupération automatique des avis.
- Répondre aux avis depuis l'outil.
- Répartition des notes de 1 à 5 étoiles.
- Liste des avis négatifs récents à traiter.
- Plusieurs boutiques.
- Mobile et tablette.
- Comptes, connexion et historique conservé d'une session à l'autre. La comparaison avec la semaine précédente se calcule dans un seul export.
- Thèmes personnalisables ou découverts automatiquement.
- Avis d'autres plateformes ou de concurrents.
- Export ou partage des indicateurs (PDF, e-mail, impression).
- Alertes et notifications.
- Autres langues que le français.

## Décisions d'implémentation
- Outil utilisable sur ordinateur uniquement.
- Une seule page affiche les quatre indicateurs.
- Chaque indicateur est affiché avec sa valeur de la période courante et sa comparaison avec la semaine précédente.
- La liste des thèmes est fixe : pain, viennoiseries, accueil, attente, prix, propreté.
- Le guide d'export est pas à pas, intégré à l'outil, avant le chargement du zip.
- Un seul zip est chargé à la fois ; recharger un nouvel export remplace le précédent.
- L'outil ne conserve rien entre deux sessions.
- Erreurs : fichier invalide, export sans avis et absence d'avis la semaine précédente ont chacun un message dédié en français.
- États vides : aucun avis pour un thème, aucun avis sans réponse.

## Notes complémentaires
Rien à signaler.
