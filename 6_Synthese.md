# Semaine Synthèse : Industrialisation IA & MLOps 2026

Bienvenue dans cette semaine intensive. L'objectif est de passer d'un simple Notebook de recherche à une **application IA robuste, testée et monitorée**.

## Objectifs Pédagogiques

* Maîtriser l'écosystème moderne Python avec **uv**.
* Structurer une API de production avec **FastAPI**.
* Mettre en place un monitoring complet (**MLflow/TensorBoard**) et des logs pro (**Loguru**).
* Garantir la qualité logicielle (**Pytest**, **Docstrings**, **README**).

Nouveauté: 
- [pytest-cov](https://pypi.org/project/pytest-cov/)
- joblib

---

## Le Workflow Standard 

Pour chaque projet, vous devez respecter la structure suivante :

1. **Gestion de projet** : Initialisation avec `pyproject.toml` et `uv lock`.
2. **Exploration** : Notebook de nettoyage et visualisation des données.
3. **Entraînement** : Utilisation de **SciKeras** pour intégrer le Deep Learning dans un pipeline Scikit-Learn.
4. **Monitoring** : Suivi des métriques via **MLflow** (Tabulaire) ou **TensorBoard** (Séquences/Images).
5. **Export** : Sauvegarde du pipeline complet avec `joblib`.

---

## Exercices

*Vous devez réaliser l'exploration et l'entraînement pour les **quatre** sujets suivants. Cependant, **un seul projet au choix** devra être "Industrialisé" (API, Tests, Logs, Docstrings).*

#### 1. Régression : Consommation Énergétique
Prédire la consommation électrique d'une usine sidérurgique.

* **Dataset :** [Steel Industry Energy Consumption](https://www.kaggle.com/datasets/csafrit2/steel-industry-energy-consumption)
* **Challenge :** Gérer les variables temporelles et la multi-colinéarité.

#### 2. Classification : Réussite Académique
Prédire si un étudiant va abandonner, rester ou obtenir son diplôme.

* **Dataset :** [Students' Dropout and Academic Success](https://www.kaggle.com/datasets/thedevastator/higher-education-predictors-of-student-retention)
* **Challenge :** Équilibrage des classes et analyse de l'importance des variables.

#### 3. Vision : Reconnaissance Culinaire (Transfer Learning)
Classifier des images de plats parmi 101 catégories.

* **Dataset :** [Food-101](https://www.kaggle.com/datasets/dansbecker/food-101/data)
* **Challenge :** Utilisation d'un modèle pré-entraîné (MobileNet ou ResNet) et optimisation fine (Fine-tuning).

#### 4. RNN : Qualité de l'Air (Time Series)
Prédire la concentration de CO (Monoxyde de carbone) à partir de capteurs chimiques.

* **Dataset :** [Air Quality Index](https://archive.ics.uci.edu/dataset/360/air+quality)
* **Challenge :** Mise en place d'une fenêtre temporelle (Sliding Window) et gestion des données manquantes.

---

## Le Livrable Final (Le Projet Choisi)

Le projet que vous choisirez de finaliser devra impérativement comporter :

### Structure du Code

```text
├── api/
│   ├── main.py            # Routes FastAPI
│   └── model_ia/
│       └── model.py       # Logique de prédiction (Propre & Documenté)
├── tests/
│   └── test_api.py        # Pytest pour la route /predict
├── logs/                  # Dossier des logs générés par Loguru
├── model_v1.joblib        # Le pipeline exporté
├── pyproject.toml         # Dépendances gérées par uv
└── README.md              # Documentation complète

```

### Exigences Techniques

* **FastAPI** : Une route `/predict` qui reçoit un JSON et renvoie la prédiction.
* **Loguru** : Chaque appel à l'API doit être loggué (Input, Output, Temps d'exécution).
* **Documentation** : Docstrings au format Google/NumPy pour chaque fonction dans `model.py`.
* **Validation** : Au moins 2 tests unitaires avec **Pytest** ainsi que la mise en place du framework [pytest-cov](https://pypi.org/project/pytest-cov/). A minima, la route `predict` et le modèle.
* **Monitoring** : Capture d'écran ou fichier de log prouvant l'utilisation de **MLflow** ou **TensorBoard** durant l'entraînement.
