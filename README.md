# Porfolio-1---Etude-du-taux-d-attrition-de-cartes-de-cr-dit
Qui sont ces clients d'une banque qui résilient leur carte de crédit? sur 10127 clients, 1627 sont partis (16,1%). J'ai nettoyé les données avec Python (Panda), calculé la part de clients partis selon l'âge, le type de carte, et le niveau d'activité, puis vérifié ces chiffres en SQL. Résultats présentés dans un tableau de bord Tableau.

# Présentation du projet

Ce projet consiste à analyser l'attrition (*Customer Churn*) des clients d'une banque afin d'identifier les profils les plus susceptibles de résilier leur carte de crédit.

L'objectif est de comprendre les facteurs associés à ces résiliations, de mettre en évidence les segments les plus exposés et de proposer des pistes d'amélioration pour les stratégies de fidélisation.

Quelques chiffres clés :
- Clients analysés : 10 127
- Clients ayant résilié leur carte : 1 627
- Taux d'attrition global : 16,1 %

# Source des données

- Kaggle – Credit Card Customers.
- 10 127 observations.
- Attrition Flag.
- informations démographiques, caractéristiques des cartes et indicateurs d'activité des clients.

# Outils et méthodologie

1. Nettoyage et préparation des données – Python / Pandas

- Suppression de deux colonnes non pertinentes.
- Harmonisation des noms de colonnes en minuscules.
- Création d'une variable binaire pour identifier les départs (0 ou 1).
- Création de tranches d'âge.
- Segmentation des clients selon trois niveaux d'activité.
- Développement d'une fonction personnalisée `taux_par()` pour calculer les taux d'attrition selon différents critères.

2. Validation des résultats – SQL / SQLite

- Importation des données nettoyées dans une base SQLite.
- Création de requêtes SQL pour recalculer les indicateurs.
- Comparaison des résultats SQL avec ceux obtenus sous Pandas.

 Résultat : j'ai obtenu les mêmes résultats chiffrés avec Python/Pandas et SQL, confirmant la cohérence des calculs.

# Visualisation des données – Tableau

Création d'un tableau de bord interactif permettant d'explorer :
- Le nombre total de clients.
- Le nombre de clients ayant résilié leur carte de crédit.
- Le taux d'attrition global.
- Les taux d'attrition par tranche d'âge.
- Les taux d'attrition selon les niveaux d'activité.
- Les différences selon les caractéristiques des cartes bancaires
- Le lien entre nombre de transactions et montant des transactions pour les clients ayant résilié (vert) et les autres (rouge).

# Conclusions principales

16.07% des 10127 clients de cette banque ont résilié leur carte de crédit (1627 résiliations). 
L'étude croisée des caractéristiques comportementales et démographiques met en évidence les constats suivants:

- Catégorie de cartes : les détenteurs de carte Platinium présentent le taux d'attrition le plus élevé  atteingnant 25%, ce qui en fait le segment le plus fragile.
- Tranche d'âge: le risque de résiliation culmine chezles clients âgés de 40 et 60 ans bien que les écarts d'attrition entre les différentes tranches d'âge restent modérés.
- Inactivité: Environ 51% des résiliations surviennent chez des clients sans période d'inactivité déclarée sur l'année, indiquant que le départ n'est pas toujours précédé d'une longue phase de sommeil du compte.
- Volume et montant des transactions: le nuage de points montre clairement que les clients ayant résilié leur carte (en vert) se concentrent sur la zone à faible nombre de transactions et faibles montants cumulés. La sous-utilisation du produit carte constitue ainsi le principal facteur prédicitif de résiliation.

Aperçu du tableau de bord : [[Dashboard Credit Card Attrition](dashboard/dashboard.png)](https://public.tableau.com/app/profile/aurelie.duchez/viz/projet1-creditcardattritionanalysis/Dashboard1)

# Recommandations métier

À partir des résultats de l'analyse, plusieurs pistes d'action peuvent être envisagées :

1. Développer une fidélisation ciblée :
Concentrer les efforts de rétention sur les segments les plus exposés, en particulier les détenteurs de cartes Platinum et la tranche d'âge des 40-60 ans.

2. Anticiper le désengagement (Lutte contre la sous-utilisation) :
Mettre en place des alertes automatiques basées sur la baisse du volume de transactions (en deçà de 50 opérations) plutôt que sur l'inactivité prolongée, puisque l'étude montre que la majorité des résiliations surviennent chez des clients qui étaient encore actifs.
Proposer des offres incitatives ou des avantages personnalisés dès qu'une baisse d'utilisation de la carte est détectée, afin de réengager le client avant la résiliation effective.

# Limites et perspectives

Cette analyse repose sur des données historiques et permet principalement d'identifier des corrélations. Elle ne permet pas, à elle seule, de déterminer les causes profondes et exactes des départs ni de prédire individuellement les résiliations futures.
Perspectives d'amélioration :enrichir l'analyse avec des données comportementales supplémentaires (ex: historique de service client, réclamations), développer un modèle de Machine Learning prédictif (classification) pour anticiper le risque de départ de chaque client, construire un score de risque client (scoring) afin de prioriser les actions de fidélisation des équipes marketing.

# Compétences développées

- Analyse exploratoire des données (EDA).
- Nettoyage et transformation des données.
- Manipulation de données avec Python et Pandas.
- Requêtes SQL et validation des indicateurs.
- Stockage et gestion d'une base SQLite.
- Data Visualization avec Tableau.
- Analyse métier et formulation de recommandations.


**Projet réalisé dans le cadre du développement de compétences en Data Analytics et Business Intelligence.**
