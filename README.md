# Projet de sélection — Exploration de données avec Python

## 1. Présentation du besoin
L'entreprise Sell4All, spécialisée dans la vente de vêtements d'occasion en ligne, souhaite intégrer une fonctionnalité d'intelligence artificielle pour recommander automatiquement des produits à ses utilisateurs. Avant de développer cette fonctionnalité, il est indispensable de réaliser une première exploration et un nettoyage des données clients disponibles. L'objectif de ce projet est donc d'analyser le fichier de données démographiques et de dépenses des utilisateurs, d'en extraire des informations statistiques utiles, puis de préparer un ensemble de données propre et exploitable pour le futur modèle IA.

## 2. Étapes suivies pendant les 3 jours de réalisation
- **Jour 1 : Préparation de l'environnement et lecture des données**
  - Installation de Miniconda et de Jupyter Notebook.
  - Création de l'environnement virtuel.
  - Installation des bibliothèques nécessaires (Pandas, Matplotlib).
  - Lecture initiale du fichier CSV avec la bibliothèque Pandas pour en comprendre la structure.

- **Jour 2 : Exploration et analyse statistique**
  - Rédaction du résumé technique pour identifier le volume des données, les valeurs non nulles et les types de données.
  - Calcul de la moyenne et de la médiane des âges et des dépenses des clients.
  - Utilisation de la fonction groupby pour calculer la médiane d'âge pour chaque pays.
  - Création d'un graphique à barres avec Matplotlib pour visualiser les dépenses par pays.

- **Jour 3 : Nettoyage des données et finalisation**
  - Suppression des utilisateurs ayant dépensé moins de 10 € sur le site.
  - Élimination des lignes dupliquées pour assurer l'intégrité de l'analyse.
  - Sélection des colonnes pertinentes (Country, Age, Gender, Customer spendings).
  - Exportation des données nettoyées vers le fichier `cleaned_dataset-sell4all.csv`.
  - Rédaction de la documentation finale et préparation du dépôt GitHub.

## 3. Fonctionnalités développées et éléments finalisés
- **Analyse des données brutes** : Affichage des premières lignes et du résumé technique des données.
- **Statistiques descriptives** : Calculs automatisés de la moyenne et de la médiane pour différentes variables (Age, Dépenses).
- **Analyse par groupe** : Agrégation des données pour obtenir des métriques spécifiques (médiane d'âge par pays, dépenses totales par pays).
- **Visualisation de données** : Génération d'un graphique à barres clair et légendé pour comparer les dépenses entre les pays.
- **Pipeline de nettoyage** : Code fonctionnel qui filtre les dépenses trop faibles, supprime les doublons et conserve uniquement les colonnes requises.
- **Sauvegarde automatisée** : Génération du fichier CSV final prêt pour la modélisation IA.

## 4. Difficultés rencontrées et solutions mises en place
- **Identification des doublons** : Lors de la lecture initiale, il n'était pas évident de savoir si les mêmes utilisateurs apparaissaient plusieurs fois à cause de problèmes de saisie ou de mises à jour. *Solution :* L'utilisation de la méthode `drop_duplicates()` de Pandas a permis de nettoyer efficacement le jeu de données sans devoir vérifier manuellement chaque ligne.
- **Filtrage des colonnes** : Il fallait s'assurer de ne garder que les 4 colonnes demandées à la fin du processus. *Solution :* J'ai créé une liste spécifique contenant le nom exact des colonnes `['Country', 'Age', 'Gender', 'Customer spendings']` pour filtrer le DataFrame de manière stricte juste avant l'exportation.
- **Visualisation des pays** : Le nombre de pays pouvait rendre le graphique illisible si les étiquettes de l'axe X se chevauchaient. *Solution :* J'ai ajouté une rotation de 45 degrés aux étiquettes sur l'axe des abscisses (`plt.xticks(rotation=45)`) et ajusté l'espacement pour que tout soit lisible.

## 5. Mode d’exécution du projet

### Prérequis
- Un ordinateur fonctionnant sous Windows, Mac ou Linux.
- L'outil de gestion d'environnements et de paquets **Miniconda** installé.

### Commandes pour lancer le projet
1. Ouvrez votre terminal (Anaconda Prompt sous Windows).
2. Créez un nouvel environnement virtuel nommé "sell4all" avec Python :
   ```bash
   conda create -n sell4all python=3.9 -y
   ```
3. Activez cet environnement :
   ```bash
   conda activate sell4all
   ```
4. Installez les bibliothèques requises (Pandas, Matplotlib et Jupyter) :
   ```bash
   pip install pandas matplotlib jupyter
   ```
5. Naviguez vers le dossier contenant le projet (par exemple `C:\Project`) :
   ```bash
   cd C:\Project
   ```
6. Lancez Jupyter Notebook :
   ```bash
   jupyter notebook
   ```
7. Dans votre navigateur, ouvrez le fichier `sell4all_exploration.ipynb`.
8. Pour exécuter tout le code, cliquez sur **Cell** > **Run All** dans le menu supérieur. Le fichier de données nettoyé `cleaned_dataset-sell4all.csv` sera alors généré dans le même dossier.
