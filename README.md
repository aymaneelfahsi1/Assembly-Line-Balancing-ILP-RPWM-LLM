
# Assembly-Line-Balancing-ILP-RPWM-LLM

Ce dépôt contient le code source et la documentation pour le mini-projet :

**"Implémentation d’Approches par Programmation Linéaire Entière, Algorithmique, et Intelligence Artificielle pour l’Équilibrage de Lignes d’Assemblage"**

## Aperçu du Projet

Ce projet consiste en une analyse comparative de trois approches différentes pour résoudre le problème d’équilibrage de lignes de production dans l’industrie textile, spécifiquement pour la fabrication de chemises et de pantalons. Les trois méthodes sont :

1. **Modèle de Programmation Linéaire Entière (PLNE)** : une approche mathématique.
2. **Méthode du Poids Positionnel Classé (RPWM)** : une procédure algorithmique.
3. **Intégration de Modèles de Langage (LLM)** : utilisation de l'intelligence artificielle pour générer automatiquement la structure de la ligne d’assemblage à partir de descriptions textuelles.

## Auteurs
- **EL FAHSI Aymane**
- **DIA Mohamadou**
- **Amar Serigne Mbaye Sy**
- **Tanoh Anet Fergus**

*Élèves-ingénieurs  - Ecole Centrale Casablanca*

## Encadrants

- **Pr. RIANE Fouad**
- **Pr. JGHAMOU Afaf**

## Année Universitaire

2023-2024

## Rapport

### Table des Matières

1. [Mise en Contexte](#1-mise-en-contexte)
2. [Méthode Algorithmique](#2-méthode-algorithmique)
3. [Méthode Mathématique](#3-méthode-mathématique)
4. [Approche par Intelligence Artificielle (LLM)](#4-approche-ia-llm)
5. [Références](#5-références)

---

## 1. Mise en Contexte

Le travail consiste en une analyse comparative de trois approches différentes pour résoudre le problème d’équilibrage de lignes de production dans l’industrie textile, spécifiquement pour la fabrication de chemises et de pantalons. Les méthodes sont issues de recherches distinctes, incluant une approche basée sur l'intelligence artificielle.

---

## 2. Méthode Algorithmique

### 2.1 Contexte et Approche de Résolution

#### 2.1.1 Approche Générale

L’approche adoptée dans cette recherche se focalise sur l’analyse détaillée des opérations de la chaîne d’assemblage, en évaluant les temps de travail normaux et standards pour chaque tâche. En utilisant ces données, l’étude a pu identifier des moyens d’optimiser la distribution des tâches et de réduire les délais inutiles tout en maintenant la qualité et l’efficacité de la production.

#### 2.1.2 Méthode du Poids Positionnel Classé

L’article décrit l’application de l’algorithme de poids positionnel classé pour équilibrer la chaîne d’assemblage. Cette méthode algorithmique a été choisie pour sa capacité à fournir une répartition efficace des tâches en tenant compte de divers facteurs tels que le temps de cycle et les contraintes de précédence. L’algorithme a joué un rôle clé dans l’identification des goulots d’étranglement potentiels et la proposition de solutions pour améliorer l’efficacité globale.

#### 2.1.3 Mesures de Performance

L’étude a évalué l’efficacité de la chaîne d’assemblage en utilisant des indicateurs tels que le nombre de postes de travail, le temps de cycle, l’efficacité de la ligne, le retard d’équilibre et l’indice de fluidité. Ces mesures ont permis d’apprécier l’impact des améliorations et d’identifier les ajustements nécessaires pour optimiser la ligne d’assemblage.

#### 2.1.4 Les Deux Scénarios Étudiés

- **Scénario 1** : Équilibrage de la ligne avec contraintes de temps de cycle et de précédence.
- **Scénario 2** : Équilibrage de la ligne avec contraintes étendues, incluant les types de machines et les ressources disponibles.

### 2.2 Notre Implémentation

Notre implémentation est détaillée dans le notebook `implementation_2.ipynb`, qui inclut :

- Structuration des données et analyse initiale.
- Calcul des Poids Positionnels Classés (RPW).
- Affectation des tâches aux postes de travail pour les deux scénarios.
- Visualisation des graphes de précédence et des affectations.
- Évaluation des performances et comparaison avec les résultats de l’article.

---

## 3. Méthode Mathématique

### 3.1 Contexte et Approche de Résolution

#### 3.1.1 Contexte

L’article propose une approche avancée pour l’équilibrage de la ligne de production de chemises. Cette approche repose sur un modèle de Programmation Linéaire en Nombres Entiers (PLNE), conçu pour optimiser l’équilibre de la ligne tout en tenant compte de diverses contraintes comme le temps de cycle, les relations de précédence, l’adéquation des machines pour certaines tâches et la disponibilité des opérateurs.

#### 3.1.2 Approches Comparées

- **Modèle 1** : Cherche à minimiser le nombre total de postes de travail ouverts.
- **Modèle 7** : Un modèle affiné qui intègre des variables supplémentaires pour capturer les écarts entre les temps d’exécution des tâches dérivées.

### 3.2 Notre Implémentation

Notre implémentation, trouvée dans le notebook `implementation_1.ipynb`, utilise la bibliothèque d’optimisation Gurobi pour modéliser et résoudre les problèmes de PLNE pour les deux modèles.

---

## 4. Approche par Intelligence Artificielle (LLM)

### 4.1 Contexte et Motivation

Dans le but de simplifier le processus de définition de structures de lignes d’assemblage complexes, nous avons implémenté une approche basée sur les Modèles de Langage (LLM). Cette méthode permet aux utilisateurs de fournir des descriptions textuelles des tâches, des relations de précédence, et des contraintes, et génère automatiquement une structure de données exploitable pour l’équilibrage de la ligne.

### 4.2 Implémentation

Le code est disponible dans le fichier `llm_approach.py` et utilise un modèle de langage pré-entraîné (par exemple, GPT-4) pour interpréter les descriptions et générer les structures de données nécessaires.

#### Fonctionnalités Clés

- **Analyse du Texte Utilisateur** : Le modèle traite les descriptions textuelles pour extraire les tâches, les relations de précédence, les temps standards, et les types de machines.
- **Génération Automatique de `data_scen`** : Produit une structure de données contenant toutes les informations nécessaires pour l’équilibrage. 
- **Intégration Facile** : Les données générées sont compatibles avec les méthodes d'affectation de postes de travail existantes.

### 4.3 Avantages

- **Gain de Temps** : Évite la saisie manuelle fastidieuse des structures de données complexes.
- **Flexibilité** : Permet de décrire rapidement de nouveaux scénarios ou de modifier les existants.
- **Adaptabilité** : Le modèle peut gérer des descriptions incomplètes ou imprécises en inférant les informations manquantes (nécessitant néanmoins l'intervention d'un expert pour valider les recommandations et les pistes)

### 4.4 Comment Utiliser

1. **Fournir une Description Textuelle** : Rédigez une description détaillée des tâches et contraintes de votre ligne d’assemblage.
2. **Exécuter le Script** : Lancez `llm_approach.py` en passant la description en entrée.
3. **Obtenir les Données Structurées** : Le script génère les données structurées prêtes à être utilisées avec les méthodes d'équilibrage.
