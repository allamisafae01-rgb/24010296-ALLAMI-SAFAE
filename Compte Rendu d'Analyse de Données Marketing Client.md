# Compte Rendu d'Analyse de Données Marketing Client

## 1. Thématique et Objectifs

Ce projet s'inscrit dans le domaine de l'**Analyse Marketing et de la Segmentation Client**. L'objectif principal est de préparer et d'analyser un jeu de données client pour identifier des tendances de comportement d'achat et des profils démographiques, en vue d'une future modélisation de segmentation (clustering).

## 2. Préparation et Nettoyage des Données

Le notebook a mis en œuvre des étapes cruciales de nettoyage et d'enrichissement des données pour garantir la qualité de l'analyse.

### 2.1. Gestion des Valeurs Manquantes et Outliers

*   **Valeurs Manquantes:** Les 24 lignes où le revenu (`Income`) était manquant ont été supprimées.
*   **Outliers:** Les valeurs extrêmes ont été traitées pour éviter de biaiser l'analyse. Les clients avec un revenu supérieur à 120 000 $ et ceux dont l'âge calculé dépassait 100 ans ont été retirés.

### 2.2. Ingénierie des Caractéristiques (Feature Engineering)

Plusieurs variables composites ont été créées pour enrichir l'analyse:

| Caractéristique | Description |
| :--- | :--- |
| **Âge** | Calculé à partir de l'année de naissance. |
| **Dépense Totale (`Total_Spend`)** | Somme des dépenses dans les six catégories de produits (Vins, Fruits, Viandes, Poissons, Sucreries, Or). |
| **Enfants (`Children`)** | Nombre total d'enfants à la maison (enfants et adolescents). |
| **Statut Marital Groupé** | Simplification des statuts en `Relationship` (Marié, Ensemble) ou `Single` (Célibataire, Divorcé, Veuf, etc.). |

## 3. Analyse Exploratoire des Données (EDA)

L'EDA a permis de dégager les tendances suivantes:

### 3.1. Profil Démographique

*   **Âge:** La clientèle est majoritairement composée d'individus matures, avec une concentration dans la tranche d'âge des 40 à 60 ans.
*   **Revenu:** Le revenu moyen se situe dans la classe moyenne, avec une distribution relativement normale après le traitement des outliers.

### 3.2. Comportement d'Achat

L'analyse des dépenses révèle une forte asymétrie dans les habitudes d'achat:

*   **Catégorie Dominante:** Le **Vin** (`MntWines`) représente la part la plus importante des dépenses totales des clients, ce qui en fait le principal moteur de revenus.
*   **Potentiel de Croissance:** Les dépenses dans les autres catégories (Fruits, Poissons, Sucreries, Or) sont significativement plus faibles, indiquant un potentiel de vente croisée (cross-selling) à explorer.

### 3.3. Relation Revenu-Dépense

Une **corrélation positive** a été observée entre le revenu du client et sa dépense totale. Les clients à revenu élevé ont tendance à dépenser davantage. Cependant, la variabilité des dépenses à revenu égal souligne la nécessité d'une segmentation plus fine que le simple revenu.

## 4. Conclusion et Prochaine Étape

Le notebook a réussi à transformer les données brutes en un ensemble de données propre et enrichi, prêt pour la modélisation.

*   **Conclusion:** La diversité des profils et des comportements d'achat justifie pleinement une approche de segmentation pour optimiser les stratégies marketing.
*   **Prochaine Étape:** L'application d'un algorithme de **clustering non supervisé** (tel que K-Means) est recommandée pour identifier et profiler les segments de clientèle distincts.
