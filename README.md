# Sell4All — Exploration de données avec Python

Projet de sélection réalisé dans le cadre du parcours **Développement en Intelligence Artificielle** à YouCode.

## 1. Présentation du besoin

**Sell4All** est une entreprise de vente au détail spécialisée dans la vente de vêtements d'occasion en ligne. Après 6 mois d'activité, elle souhaite intégrer une première fonctionnalité d'intelligence artificielle capable de recommander automatiquement des produits à ses utilisateurs, en s'appuyant notamment sur leur pays, âge, genre, dépenses et habitudes d'achat.

Avant de développer cette fonctionnalité, il est nécessaire d'**explorer et de nettoyer** les données clients disponibles (`dataset-sell4all.csv`). C'est l'objectif de ce projet : réaliser une première exploration de ces données avec Python (Pandas, Matplotlib) dans un notebook Jupyter clair et documenté.

## 2. Étapes suivies pendant les 3 jours de réalisation

**Jour 1 — 14 août 2026**
- Installation de l'environnement (Miniconda, Jupyter Notebook, Pandas, Matplotlib)
- Lecture du fichier `dataset-sell4all.csv` avec Pandas
- Affichage des 5 premières lignes (`df.head()`)
- Affichage et explication du résumé technique du dataset (`df.info()`, nombre de lignes/colonnes, types de données)

**Jour 2 — 15 août 2026**
- Calcul de la moyenne et de la médiane des colonnes `Age` et `Customer spendings`
- Question bonus : calcul de la médiane d'âge par pays (`groupby`)
- Création d'un graphique à barres montrant les dépenses totales des clients par pays (Matplotlib)
- Nettoyage des données : suppression des lignes avec moins de 10 € de dépenses, puis suppression des doublons
- Export des données nettoyées dans un nouveau fichier CSV (`dataset-sell4all-clean.csv`) avec uniquement les colonnes `Country`, `Age`, `Gender`, `Customer spendings`

**Jour 3 — 16 août 2026**
- Ajustements finaux (mise à jour de la version Python utilisée)
- Rédaction du README et préparation du dépôt GitHub

## 3. Fonctionnalités développées

- [x] Lecture du fichier CSV avec Pandas
- [x] Affichage des 5 premières lignes
- [x] Résumé technique (nombre de lignes, colonnes, types de données) avec explication en Markdown
- [x] Calcul de la moyenne et de la médiane de `Age` et `Customer spendings`
- [x] Bonus : médiane d'âge par pays
- [x] Visualisation en graphique à barres des dépenses par pays
- [x] Nettoyage : suppression des dépenses < 10 € et des doublons
- [x] Export du CSV nettoyé (`Country`, `Age`, `Gender`, `Customer spendings`)

## 4. Difficultés rencontrées et solutions mises en place

- **Colonnes non nécessaires à l'analyse** (informations personnelles comme `Name`, `Email`, `Phone Number`, `Address`) : elles ont été conservées dans le dataset d'origine pour ne pas altérer les données brutes, mais exclues du fichier CSV final exporté, en ne sélectionnant que les colonnes utiles (`Country`, `Age`, `Gender`, `Customer spendings`).
- **Choix de l'agrégation pour le graphique par pays** : le nombre de clients variant selon les pays, la somme des dépenses (`groupby('Country').sum()`) a été retenue plutôt que la moyenne, afin de représenter le poids économique total de chaque pays.
- **Ordre des opérations de nettoyage** : le filtrage des dépenses < 10 € a été appliqué avant la suppression des doublons, afin de partir d'un jeu de données déjà pertinent avant d'éliminer les lignes redondantes.

## 5. Mode d'exécution du projet

### Prérequis

- [Miniconda](https://docs.conda.io/en/latest/miniconda.html) installé
- Python 3.x
- Jupyter Notebook
- Bibliothèques : `pandas`, `matplotlib`

### Installation

```bash
conda create -n sell4all python=3.13
conda activate sell4all
pip install pandas matplotlib jupyter
```

### Lancer le projet

```bash
jupyter notebook exploration-sell4all.ipynb
```

Puis exécuter les cellules du notebook dans l'ordre (`Cell > Run All`). Le fichier `dataset-sell4all.csv` doit se trouver dans le même dossier que le notebook. Le fichier nettoyé `dataset-sell4all-clean.csv` sera généré automatiquement dans ce même dossier.

## 6. Contenu du dépôt

- `exploration-sell4all.ipynb` — notebook Jupyter contenant l'exploration complète des données
- `dataset-sell4all.csv` — fichier de données brutes fourni
- `dataset-sell4all-clean.csv` — fichier de données nettoyées, généré par le notebook
- `README.md` — ce fichier
