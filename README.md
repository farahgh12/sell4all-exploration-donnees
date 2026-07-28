# Projet Sell4All — Exploration de données avec Python

## C'est quoi ce projet ?

Ce projet est le test de sélection pour intégrer le parcours **Développement en Intelligence Artificielle à YouCode**.

Sell4All est une entreprise qui vend des vêtements d’occasion en ligne. Après quelques mois d’activité, elle souhaite développer une fonctionnalité de recommandation de produits basée sur l’intelligence artificielle.

Avant de développer cette fonctionnalité, il faut d’abord explorer et nettoyer les données clients disponibles. C’est exactement l’objectif de ce projet : analyser le dataset, calculer quelques statistiques, créer une visualisation et préparer un fichier de données propre qui pourra être utilisé plus tard dans un modèle d’IA.

## Comment j'ai organisé mon travail — 3 jours

### Jour 1 — Installation et découverte des données

J’ai installé Miniconda et Jupyter Notebook. Cette étape m’a pris un peu plus de temps que prévu, car j’avais un conflit avec une version de Python déjà installée sur mon PC.

J’ai finalement créé un environnement Conda séparé pour éviter ce problème :

```bash
conda create -n sell4all python=3.9
```

Après cela, j’ai installé Pandas et Matplotlib, puis j’ai lu le fichier `dataset-sell4all.csv`.

J’ai affiché les cinq premières lignes avec `df.head()` afin de voir à quoi ressemblent les données et de mieux comprendre leur structure.

### Jour 2 — Analyse des données

Je me suis concentrée sur la partie analyse.

J’ai utilisé `df.info()` pour afficher le résumé technique des données :

* le nombre de lignes ;
* les colonnes disponibles ;
* le nombre de valeurs non nulles ;
* les types de données.

J’ai ensuite calculé la moyenne et la médiane pour les colonnes `Age` et `Customer spendings`.

Pour la partie bonus, j’ai calculé la médiane d’âge pour chaque pays. J’ai dû chercher comment fonctionne `groupby()`, et la vidéo de présentation de Pandas m’a aidée à comprendre son utilisation.

J’ai terminé cette partie avec la création d’un graphique à barres représentant les dépenses totales des clients par pays.

### Jour 3 — Nettoyage et finalisation

J’ai nettoyé les données en supprimant :

* les lignes des clients ayant dépensé moins de **10 €** ;
* les lignes dupliquées.

J’ai ensuite conservé uniquement les colonnes demandées :

* `Country`
* `Age`
* `Gender`
* `Customer spendings`

Enfin, j’ai exporté les données nettoyées dans le fichier `cleaned_dataset-sell4all.csv`, puis j’ai finalisé le notebook et rédigé ce README.

## Ce qui est fait

* Lecture du fichier CSV avec Pandas.
* Affichage des cinq premières lignes avec `df.head()`.
* Résumé technique avec `df.info()` et explication des résultats :

  * nombre d’entrées ;
  * valeurs non nulles ;
  * types de données.
* Calcul de la moyenne et de la médiane pour `Age`.
* Calcul de la moyenne et de la médiane pour `Customer spendings`.
* Bonus : calcul de la médiane d’âge par pays avec `groupby()`.
* Création d’un graphique à barres des dépenses totales par pays.
* Suppression des lignes ayant des dépenses inférieures à **10 €**.
* Suppression des doublons.
* Création d’un fichier CSV nettoyé contenant uniquement les quatre colonnes demandées.

## Difficultés rencontrées

### Nom de la colonne `Age`

Au début, j’avais du mal avec le nom de la colonne `Age`. Dans la consigne, il est écrit **« Âge »** avec un accent, mais dans le fichier CSV, la colonne s’appelle simplement `Age`.

Cela m’a donné une erreur `KeyError` lors de mon premier essai.

J’ai résolu ce problème en utilisant :

```python
df.columns
```

Cette commande m’a permis de vérifier les noms exacts des colonnes présentes dans le dataset.

### Affichage des noms des pays

Dans le graphique, les noms des pays se chevauchaient sur l’axe X, car le dataset contient plusieurs pays.

J’ai résolu ce problème en ajoutant une rotation de 45 degrés :

```python
plt.xticks(rotation=45, ha='right')
```

Cela a rendu les noms des pays plus lisibles.

### Ordre du nettoyage

Je n’étais pas certaine de l’ordre à utiliser pour supprimer les doublons et filtrer les dépenses inférieures à **10 €**.

J’ai testé les deux possibilités et j’ai gardé l’ordre suivant :

1. Filtrer les clients ayant dépensé moins de **10 €**.
2. Supprimer les lignes dupliquées.

Cet ordre m’a permis d’obtenir un résultat cohérent et de respecter les étapes demandées dans le brief.

## Technologies utilisées

* Python
* Jupyter Notebook
* Pandas
* Matplotlib
* Miniconda

## Structure du projet

```text
sell4all-exploration-donnees/
├── dataset-sell4all.csv
├── cleaned_dataset-sell4all.csv
├── sell4all_exploration.ipynb
└── README.md
```

## Comment lancer le projet

### Prérequis

Il faut avoir **Miniconda** installé sur son ordinateur.

### 1. Créer un environnement

```bash
conda create -n sell4all python=3.9
```

### 2. Activer l’environnement

```bash
conda activate sell4all
```

### 3. Installer les bibliothèques

```bash
pip install pandas matplotlib jupyter
```

### 4. Se placer dans le dossier du projet

```bash
cd C:\Project
```

### 5. Lancer Jupyter Notebook

```bash
jupyter notebook
```

### 6. Exécuter le notebook

Ouvrez le fichier :

```text
sell4all_exploration.ipynb
```

Puis cliquez sur :

**Cell → Run All**

Le fichier `cleaned_dataset-sell4all.csv` sera généré automatiquement dans le dossier du projet.
