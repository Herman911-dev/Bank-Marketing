# 🏦 Analyse Marketing & Prédiction de Souscription Bancaire (R)

## 🎯 Objectif du Projet
Ce projet vise à analyser et prédire le comportement des clients suite à des campagnes de démarchage téléphonique pour un dépôt à terme. L'enjeu est d'identifier les profils les plus susceptibles de souscrire afin d'optimiser le **ROI (Retour sur Investissement)** des campagnes marketing.

## 🏗️ Méthodologie & Pipeline Data
Le projet suit une démarche de Data Science complète, de l'exploration brute au déploiement :

### 1. Nettoyage & Préparation (ETL)
- **Traitement des valeurs aberrantes** : Utilisation de la méthode de l'écart interquartile (IQR) sur la variable `balance` pour éviter de fausser les moyennes par des profils atypiques.
- **Gestion des données manquantes** : Traitement des valeurs `unknown` par suppression ou réétiquetage (ex: "jamais_contacté").
- **Ingénierie des caractéristiques** : Encodage des variables catégorielles (One-Hot Encoding) pour la modélisation.

### 2. Analyse Exploratoire & Statistique (EDA)
- **Segmentation Métier** : Identification des étudiants et retraités comme cibles prioritaires.
- **Tests de Corrélation** : Test du **Khi-Deux ($\chi^2$)** pour valider statistiquement l'influence du métier et de l'éducation sur la souscription ($p\text{-value} < 0.05$).
- **Visualisation Bivariée** : Analyse de la relation entre l'âge, le solde bancaire et le taux de succès via `ggplot2`.

### 3. Modélisation & Machine Learning
- **Algorithme** : Implémentation du **KNN (K-Nearest Neighbors)** avec $k=5$.
- **Évaluation** : Utilisation d'une matrice de confusion pour mesurer la performance.
- **Résultat métier** : Le modèle atteint une **précision de 58%** sur les prédictions positives, soit un taux **5 fois supérieur** au taux de conversion naturel (11.7%).

### 4. Déploiement Interactif (Shiny)
- Création d'une application **R Shiny** permettant aux décideurs de simuler des segments de clientèle (âge, métier, solde) et d'obtenir instantanément le potentiel de conversion.

## 🛠️ Stack Technique
- **Langage** : R
- **Bibliothèques** : `ggplot2`, `class` (ML), `shiny` (Web App), `stats`.

## 🚀 Comment utiliser ce projet
1. **Cloner le repo** : `git clone https://github.com/votre-pseudo/votre-repo.git`
2. **Installation** : Assurez-vous d'avoir les packages installés : 
   ```r
   install.packages(c("ggplot2", "class", "shiny"))
