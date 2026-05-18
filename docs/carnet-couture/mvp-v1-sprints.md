# Carnet Couture — MVP V1 en sprints courts

## Objectif de la V1

La V1 doit valider une hypothèse simple : un couturier peut remplacer son cahier papier par un carnet numérique léger pour enregistrer, suivre et retrouver ses commandes client.

La promesse produit de la V1 est volontairement courte :

> Enregistrer une commande avec le client, les dates, les photos du tissu et du modèle, le statut, le paiement léger, puis la retrouver rapidement.

## Périmètre impératif V1

### Inclus

- Un compte simple pour un couturier ou une couturière.
- Création et modification d'un client.
- Création, modification et suppression confirmée d'une commande.
- Association d'une commande à un client.
- Date de réception du tissu.
- Date prévue de livraison.
- Photo du tissu.
- Photo du modèle demandé.
- Statut de commande : `Reçue`, `En cours`, `Terminée`, `Livrée`.
- Notes libres pour les détails du modèle, les mensurations simples ou les remarques.
- Paiement léger : prix total, avance, reste à payer calculé.
- Liste des commandes.
- Recherche par nom ou téléphone.
- Tableau de bord simple : commandes en cours, prochaines livraisons, retards.

### Exclus de la V1

- Paiement en ligne.
- Mobile Money.
- Factures ou reçus PDF.
- Notifications push avancées.
- WhatsApp automatique.
- Gestion multi-utilisateurs.
- Gestion d'équipe ou d'employés.
- Gestion de stock.
- Comptabilité complète.
- Statistiques avancées.
- Application mobile native obligatoire.
- Mode hors ligne complet.
- Gestion multi-ateliers.
- Catalogue de modèles.

## Principes de conception MVP

- Mobile-first : l'expérience principale est sur téléphone.
- Formulaires courts : une commande doit pouvoir être ajoutée en moins de 2 minutes.
- Photos centrales : le tissu et le modèle doivent être visibles dès la fiche commande.
- Mots simples : éviter les termes techniques comme CRM, pipeline ou workflow.
- Peu de statuts : quatre statuts suffisent pour tester l'usage réel.
- Tolérance à l'erreur : tout élément important doit être modifiable.
- Recherche rapide : retrouver une commande est aussi important que l'enregistrer.

## Découpage en sprints courts

Chaque sprint doit durer entre 3 et 5 jours ouvrés. L'objectif est de livrer un incrément testable à chaque fin de sprint.

### Sprint 0 — Cadrage et prototype basse fidélité

#### Objectif

Aligner le périmètre V1, les écrans essentiels et le parcours principal avant de coder.

#### Livrables

- Parcours utilisateur principal : réception d'un tissu, création de commande, consultation, livraison.
- Liste définitive des champs V1.
- Maquette simple des écrans : tableau de bord, liste commandes, ajout commande, détail commande, liste clients, détail client.
- Règles métier de base : statuts, calcul du reste à payer, définition d'une commande en retard.

#### Critères d'acceptation

- Le parcours principal est compréhensible sans explication longue.
- Le formulaire de commande tient sur un écran mobile avec sections simples.
- La cliente valide explicitement ce qui est inclus et exclu de la V1.

### Sprint 1 — Socle application et commandes locales

#### Objectif

Construire le squelette utilisable du carnet numérique avec les données principales, même sans fonctionnalités avancées.

#### Livrables

- Interface mobile-first.
- Navigation entre tableau de bord, commandes et clients.
- Création d'une commande avec client, téléphone, dates, statut et notes.
- Liste des commandes.
- Détail d'une commande.
- Modification du statut.

#### Critères d'acceptation

- Un utilisateur peut créer une commande complète sans photo.
- Une commande créée apparaît immédiatement dans la liste.
- Le statut peut être changé depuis le détail de la commande.
- Les commandes affichent au minimum le nom du client, la date de livraison et le statut.

### Sprint 2 — Photos, clients et recherche

#### Objectif

Rendre le MVP utile pour le problème initial : ne plus confondre les tissus et retrouver rapidement une commande.

#### Livrables

- Ajout d'une photo du tissu.
- Ajout d'une photo du modèle.
- Création automatique ou sélection d'un client lors de la création de commande.
- Liste des clients.
- Détail client avec historique de commandes.
- Recherche par nom ou téléphone.

#### Critères d'acceptation

- Une commande peut contenir une photo du tissu et une photo du modèle.
- Les photos sont visibles dans le détail commande.
- Un client peut avoir plusieurs commandes.
- Une recherche par nom ou téléphone retrouve la commande attendue.

### Sprint 3 — Tableau de bord, paiements légers et retards

#### Objectif

Donner au couturier une vue claire sur les priorités et les restes à payer.

#### Livrables

- Tableau de bord avec commandes en cours.
- Liste des prochaines livraisons.
- Liste ou indicateur des commandes en retard.
- Champs prix total et avance.
- Calcul automatique du reste à payer.
- Filtres simples par statut.

#### Critères d'acceptation

- Une commande dont la date de livraison est passée et non livrée est indiquée comme en retard.
- Le reste à payer est calculé automatiquement.
- Le tableau de bord permet d'identifier les commandes à traiter en priorité.
- Les commandes peuvent être filtrées par statut.

### Sprint 4 — Stabilisation et test terrain

#### Objectif

Préparer une version testable par 3 à 5 couturiers en conditions réelles.

#### Livrables

- Corrections d'ergonomie observées pendant les tests internes.
- Messages d'erreur simples.
- Confirmations pour suppression.
- Données de démonstration.
- Guide de test terrain.
- Liste des retours utilisateurs à collecter.

#### Critères d'acceptation

- Un couturier peut ajouter une commande en moins de 2 minutes.
- Un couturier peut retrouver une commande sans assistance.
- Le produit peut être testé sur téléphone pendant une vraie semaine de travail.
- Les retours sont structurés pour décider de la V2.

## Scénario de test MVP

Pendant le test terrain, demander à chaque couturier de réaliser les actions suivantes :

1. Ajouter un nouveau client.
2. Ajouter une commande pour ce client.
3. Prendre ou ajouter une photo du tissu.
4. Ajouter une photo du modèle demandé.
5. Renseigner la date de réception.
6. Renseigner la date de livraison.
7. Ajouter le prix total et l'avance.
8. Retrouver la commande dans la liste.
9. Rechercher la commande par nom ou téléphone.
10. Passer la commande au statut `En cours`.
11. Marquer la commande comme `Terminée` puis `Livrée`.

## Indicateurs de réussite V1

Le MVP est considéré comme prometteur si :

- Au moins 3 couturiers comprennent le parcours principal sans formation longue.
- Une commande réelle peut être ajoutée en moins de 2 minutes.
- Les utilisateurs retrouvent une commande plus vite que dans leur cahier.
- Les photos du tissu et du modèle sont jugées utiles.
- Les utilisateurs acceptent de tester l'application pendant au moins une semaine.
- Les retours demandent surtout des améliorations V2, et non une refonte du cœur V1.

## Questions de précision à poser à la cliente

### Priorité métier

1. Quel est le problème le plus douloureux aujourd'hui : perdre les informations, confondre les tissus, oublier les délais, ou suivre les paiements ?
2. Pour la V1, faut-il privilégier la rapidité d'enregistrement ou le niveau de détail des commandes ?
3. Quels types de vêtements sont les plus fréquents chez les couturiers visés ?

### Utilisateurs ciblés

4. La V1 vise-t-elle un couturier indépendant, une couturière seule, ou un petit atelier ?
5. Une seule personne utilisera-t-elle le compte en V1 ?
6. Les utilisateurs sont-ils généralement à l'aise avec un smartphone ?

### Commandes

7. Quelles informations sont absolument obligatoires pour enregistrer une commande ?
8. Les quatre statuts `Reçue`, `En cours`, `Terminée`, `Livrée` suffisent-ils pour commencer ?
9. Une commande peut-elle contenir plusieurs vêtements, ou faut-il créer une commande par vêtement ?
10. Faut-il pouvoir modifier toutes les informations après création ?

### Photos

11. La photo du tissu doit-elle être obligatoire ou simplement recommandée ?
12. La photo du modèle doit-elle être obligatoire ou optionnelle ?
13. Une seule photo de tissu et une seule photo de modèle suffisent-elles pour la V1 ?
14. Les couturiers utilisent-ils plutôt l'appareil photo direct ou des images déjà reçues par WhatsApp ?

### Clients

15. Le numéro de téléphone est-il obligatoire pour chaque client ?
16. Un client peut-il avoir plusieurs commandes actives en même temps ?
17. Faut-il afficher l'historique complet des commandes d'un client dès la V1 ?

### Paiements

18. Le suivi prix total, avance et reste à payer est-il indispensable en V1 ?
19. Faut-il gérer plusieurs avances sur une même commande, ou une seule avance suffit-elle pour commencer ?
20. Faut-il afficher les commandes avec reste à payer dans le tableau de bord ?

### Plateforme et usage terrain

21. Les couturiers auront-ils une connexion internet régulière ?
22. Une application web installable sur téléphone suffit-elle pour tester, ou faut-il absolument une application Android ?
23. Les tests terrain se feront-ils avec de vraies données clients ?
24. Combien de couturiers peuvent tester la V1 pendant une semaine ?

### Décisions V2/V3

25. Parmi notifications, WhatsApp, reçus PDF, mensurations structurées et mode hors ligne, quelle fonctionnalité semble la plus importante après la V1 ?
26. La cliente envisage-t-elle un produit pour un seul atelier ou une solution destinée à plusieurs couturiers ?
27. Le modèle économique attendu est-il un achat unique, un abonnement, ou une offre gratuite au départ ?

## Décisions à verrouiller avant développement

Avant de lancer le Sprint 1, il faut valider :

- Le nom provisoire du produit.
- La cible exacte de la V1.
- Les champs obligatoires d'une commande.
- Les champs obligatoires d'un client.
- Le caractère obligatoire ou non des photos.
- L'inclusion ou non du paiement léger.
- Le choix PWA mobile-first ou application native.
- La durée du test terrain et le nombre de couturiers testeurs.
