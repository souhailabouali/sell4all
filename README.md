# Sell4All — Exploration des données avec Python

Ce projet a été réalisé dans le cadre du parcours **Développement en Intelligence Artificielle** à YouCode. L'idée, c'était de se familiariser avec l'exploration et le nettoyage de données en Python, avant de se lancer dans de vraies fonctionnalités de recommandation.

## De quoi ça parle ?

Sell4All, c'est une boutique en ligne de vêtements d'occasion qui existe depuis environ six mois. Ils veulent ajouter un système de recommandation de produits basé sur le pays, l'âge, le genre, les dépenses et les habitudes d'achat des clients.

Mais avant d'arriver là, il fallait d'abord bien comprendre et nettoyer les données clients qu'ils avaient. Du coup, ce projet se concentre sur l'exploration du fichier `dataset-sell4all.csv` avec Pandas et Matplotlib, dans un notebook Jupyter.

## Comment j'ai procédé

### Jour 1 — 14 août 2026
- Installation de l'environnement (Miniconda, Jupyter, Pandas, Matplotlib)
- Chargement du CSV dans un DataFrame Pandas
- Affichage des premières lignes (`df.head()`) pour voir à quoi ça ressemble
- Utilisation de `df.info()` pour comprendre la structure, les types de données et les valeurs manquantes

### Jour 2 — 15 août 2026
- Calcul de la moyenne et de la médiane pour `Age` et `Customer spendings`
- Tentative du bonus : médiane de l'âge par pays avec `groupby`
- Création d'un graphique à barres pour visualiser les dépenses totales par pays (Matplotlib)
- Nettoyage : suppression des lignes avec des dépenses inférieures à 10 €, puis suppression des doublons
- Export des données nettoyées dans un nouveau CSV (`dataset-sell4all-clean.csv`), en ne gardant que les colonnes utiles : `Country`, `Age`, `Gender`, `Customer spendings`

### Jour 3 — 16 août 2026
- Derniers ajustements, vérification de la version Python utilisée
- Rédaction de ce README et mise en ligne sur GitHub

## Ce qui a été fait

- [x] Lecture du CSV avec Pandas
- [x] Affichage des 5 premières lignes
- [x] Explication de la structure du dataset (lignes, colonnes, types) en Markdown
- [x] Moyenne et médiane de `Age` et `Customer spendings`
- [x] Bonus : médiane d'âge par pays
- [x] Graphique à barres des dépenses totales par pays
- [x] Nettoyage : filtrage des dépenses < 10 € et suppression des doublons
- [x] Export du CSV nettoyé avec les colonnes sélectionnées

## Quelques petits obstacles

- **Colonnes inutiles** — Le dataset d'origine contenait des infos personnelles comme `Name`, `Email`, `Phone Number` et `Address`. Je ne voulais pas toucher aux données brutes, donc je les ai gardées dans le fichier original, mais je ne les ai pas incluses dans la version nettoyée exportée.
- **Choix de l'agrégation pour le graphique** — J'ai pris la somme des dépenses par pays (`groupby('Country').sum()`) plutôt que la moyenne, parce que ça donne une meilleure idée du poids économique total de chaque pays, même si le nombre de clients varie.
- **Ordre du nettoyage** — J'ai d'abord filtré les petits dépensiers, puis j'ai supprimé les doublons. Ça me semblait plus logique d'éliminer les lignes peu pertinentes avant de traiter les redondances.

## Comment lancer le projet

### Ce qu'il faut

- [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- Python 3.x
- Jupyter Notebook
- Les bibliothèques `pandas` et `matplotlib`

### Installation

```bash
conda create -n sell4all python=3.13
conda activate sell4all
pip install pandas matplotlib jupyter
