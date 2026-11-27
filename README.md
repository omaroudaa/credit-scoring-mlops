# Credit Scoring – Pipeline MLOps End-to-End

## Présentation

Ce projet vise à industrialiser un modèle de Machine Learning dédié à la prédiction du risque de crédit. Il met en œuvre un pipeline MLOps complet couvrant l'entraînement, le suivi des expériences, le déploiement et la surveillance du modèle.

L'objectif est d'assurer la reproductibilité des entraînements, l'automatisation des tests et le suivi des performances du modèle tout au long de son cycle de vie.

## Technologies utilisées

- **Python & Scikit-learn** : développement et entraînement du modèle Random Forest.
- **MLflow** : suivi des expériences, gestion des métriques et Model Registry.
- **FastAPI & Pydantic** : développement d'une API REST pour les prédictions.
- **Pytest** : tests automatisés.
- **GitHub Actions** : intégration continue (CI/CD).
- **Docker** : conteneurisation de l'application.
- **Evidently AI** : surveillance des données et détection du Data Drift.

## Fonctionnalités principales

- Préparation des données et configuration centralisée des hyperparamètres avec `params.yaml`.
- Entraînement reproductible d'un modèle Random Forest.
- Suivi des expériences et des performances avec MLflow.
- Développement d'une API REST permettant de prédire le risque de crédit.
- Automatisation des tests et validation du code avec GitHub Actions.
- Conteneurisation et exécution de l'application avec Docker.
- Détection des changements dans les données de production grâce à Evidently AI.

## Structure du projet

```text
credit-scoring-mlops/
├── data/
├── src/
│   ├── train.py
│   ├── app.py
│   └── monitor.py
├── tests/
├── .github/workflows/
├── params.yaml
├── requirements.txt
├── Dockerfile
└── README.md
```

## Installation et exécution

**1. Cloner le projet**

```bash
git clone https://github.com/omaroudaa/credit-scoring-mlops.git
cd credit-scoring-mlops
```

**2. Installer les dépendances**

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Sous Windows, utiliser `venv\Scripts\activate`.

**3. Entraîner le modèle**

```bash
python -m src.train
```

**4. Lancer l'API**

```bash
uvicorn src.app:app --reload
```

**5. Exécuter les tests**

```bash
python -m pytest -v tests/
```

**6. Lancer la surveillance des données**

```bash
python -m src.monitor
```

**7. Construire l'image Docker**

```bash
docker build -t credit-scoring-api .
```

## Auteur

**Omar Oudaa**

