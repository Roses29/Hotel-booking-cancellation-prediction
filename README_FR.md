🌍 [Read in English](README.md) | 📓 [Voir PDF](./CHT_Graded_Project_Learner_Notebook.ipynb)

# 🏨 Prédiction d'annulations hôtelières

## Présentation

Ce projet s'attaque au problème des annulations de réservations hôtelières, qui représentent une source importante de pertes de revenus pour les hôtels. En utilisant un jeu de données réel du groupe **INN Hotels** (Portugal), l'objectif est de construire des modèles de machine learning capables de prédire si une réservation sera annulée, et d'en tirer des recommandations opérationnelles concrètes.

## Jeu de données

Le dataset contient **36 275 réservations** avec **19 variables**, dont :

- Informations sur les clients (nombre d'adultes, d'enfants, de demandes spéciales)
- Détails de la réservation (délai de réservation, segment de marché, type de chambre, formule repas)
- Informations de séjour (nuits en semaine, nuits de week-end, date d'arrivée)
- Variable cible : `booking_status` (Annulée / Non annulée)

## Méthodologie

1. **Analyse exploratoire des données (EDA)**
   - Analyses univariées et bivariées
   - Traitement des valeurs aberrantes (prix moyen par chambre, nombre d'enfants)
   - Résultats clés : 32,8 % des réservations ont été annulées ; les réservations en ligne présentent le taux d'annulation le plus élevé (~38 %) ; les clients fidèles ont un très faible taux d'annulation (~2-3 %)

2. **Préparation des données**
   - Encodage one-hot des variables catégorielles
   - Division entraînement/test 70/30 avec stratification

3. **Modèles entraînés**
   | Modèle | F1-Score (Test) |
   |--------|----------------|
   | Régression Logistique | 0,79 |
   | SVM – Noyau Linéaire | 0,80 |
   | SVM – Noyau RBF | 0,81–0,82 |
   | Arbre de Décision (optimisé) | 0,82 |
   | Forêt Aléatoire | 0,90 |

4. **Métrique d'évaluation** : F1-Score (pour équilibrer précision et rappel sur les deux classes)

## Résultats Clés

- Le **délai de réservation (lead time)** est la variable la plus importante : plus le délai entre la réservation et l'arrivée est long, plus le risque d'annulation est élevé.
- Le **prix moyen de la chambre** et le **nombre de demandes spéciales** sont également des prédicteurs importants.
- Les **réservations en ligne** présentent le taux d'annulation le plus élevé ; les segments **complémentaire** et **corporate** sont les plus fiables.

## Recommandations Business

1. Appliquer des politiques d'annulation plus strictes (remboursements réduits) pour les réservations avec un long délai.
2. Proposer une tarification dynamique pour attirer des réservations pendant les périodes creuses.
3. Mettre en place des politiques non-remboursables ou à faible remboursement pour les réservations en ligne.
4. Enrichir l'expérience client avec des services et avantages supplémentaires pour fidéliser la clientèle.

### Stack Technique

- **Python** – pandas, NumPy, Matplotlib, Seaborn
- **Scikit-learn** – Régression Logistique, SVM, Arbre de Décision, Forêt Aléatoire, GridSearchCV
