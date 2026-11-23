# Fiche du sujet F5 : Facteurs de risque d'un portefeuille

> Cette fiche résume le sujet tel qu'il figure dans le tableau de l'énoncé de l'examen (Partie B) et tel qu'il a été traité dans ce projet. Si vous disposez de la fiche officielle (`projets_finance_science_donnees.md`), collez-la ici à la place de ce résumé.

## Sujet (énoncé)

| Élément | Précision |
|---|---|
| N° et titre | F5, Facteurs de risque d'un portefeuille |
| Type de tâche | Régression linéaire multiple |
| Algorithmes compatibles (annexe A) | 1 (régression linéaire) ; 2 (Ridge) en comparaison |
| Point d'attention | Les rendements du portefeuille sont à collecter soi-même ; les tests avec `statsmodels` sont autorisés |

## Question

Les rendements d'un portefeuille s'expliquent-ils par le marché, la taille et la valeur ?

## Mise en œuvre dans ce projet

- **Portefeuille** : équipondéré (poids 1/5, rééquilibré chaque mois) de cinq grandes valeurs technologiques américaines : AAPL, MSFT, GOOGL, AMZN, META. Les cours sont collectés sur Yahoo Finance (`yfinance`).
- **Facteurs** : Fama-French à trois facteurs (`Mkt-RF`, `SMB`, `HML`) et taux sans risque `RF`, issus de la Kenneth R. French Data Library.
- **Période** : janvier 2015 à décembre 2025, rendements mensuels en % (132 mois).
- **Cible** : rendement en excès `Rp_exc = Portefeuille − RF`.
- **Modèle** : `Rp_exc = α + β1·(Mkt-RF) + β2·SMB + β3·HML + ε`, estimé par moindres carrés ordinaires (algorithme n° 1), avec erreurs robustes de Newey-West (HAC).
- **Références** : moyenne d'apprentissage (référence naïve) et CAPM. Ridge (n° 2) sert de modèle de comparaison.
- **Évaluation** : découpage chronologique 75 % / 25 % (test : 2023-04 à 2025-12), validation croisée `TimeSeriesSplit`, R² hors échantillon (métrique principale), RMSE et MAE.
- **Objectif mesurable** : R² hors échantillon du modèle à trois facteurs supérieur à celui du CAPM et à 0, et test F de SMB et HML avec p < 0,05.

## Risques signalés

Biais de survie (titres choisis après coup), portefeuille concentré sur un secteur, peu de mois de test (33), facteurs observés le même mois que la cible (modèle explicatif, pas prédictif).
