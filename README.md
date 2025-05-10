
# ⚡ Prévision de la Consommation Énergétique à l'aide du Machine Learning et des Séries Temporelles

## 📘 Résumé du Projet

Ce projet vise à prévoir la consommation énergétique globale à court terme à l’aide de modèles de machine learning et de séries temporelles. L’objectif est d’identifier le modèle le plus performant pour anticiper la demande énergétique et soutenir la prise de décision dans un cadre opérationnel.

---

## 📊 Données Utilisées

- **Source** : Données collectées à fréquence de 10 minutes.
- **Variables** :
  - Température, Humidité, Vitesse du vent
  - Heures, Jours de la semaine, Indicateur week-end
  - Lags de consommation énergétique (`lag_1`, `lag_2`, `lag_24`)
- **Cible** : `Total_PowerConsumption = Zone1 + Zone2 + Zone3`

---

## 🛠️ Prétraitement

- Nettoyage des données et traitement des valeurs manquantes
- Création de variables temporelles et de décalage
- Normalisation Min-Max pour les modèles sensibles à l’échelle (LSTM, SVR)
- Transformation des données en séquences pour les modèles séquentiels

---

## 🤖 Modèles Testés

| Modèle         | Type               | Normalisation | Séquentiel |
|----------------|--------------------|---------------|------------|
| Random Forest  | Ensemble (Arbres)  | ❌             | ❌          |
| XGBoost        | Gradient Boosting  | ❌             | ❌          |
| SARIMA         | Série Temporelle   | ❌             | ✅          |
| LSTM           | Deep Learning RNN  | ✅             | ✅          |
| SVR            | Régression non-lin.| ✅             | ❌          |

---

## 📏 Évaluation

- Métrique utilisée : **Root Mean Squared Error (RMSE)**
- Séparation temporelle : 80% entraînement / 20% test
- Résultats disponibles dans le rapport final

---

## 📈 Visualisations

- Courbes de prédiction vs consommation réelle
- Matrices de corrélation
- Importance des variables (Random Forest, XGBoost)

---

## 🧠 Recommandation Finale

Le modèle **LSTM** s’est montré le plus adapté pour la capture des dynamiques temporelles.  
Les modèles **Random Forest** et **XGBoost** restent d'excellentes alternatives dans les contextes à contrainte de ressources.

---

## ⚙️ Installation

1. Clonez le dépôt Git :
```bash
git clone https://github.com/votre-utilisateur/power-forecasting.git
cd power-forecasting
```

2. Créez un environnement virtuel (optionnel mais recommandé) :
```bash
python -m venv venv
source venv/bin/activate    # Linux/macOS
venv\Scripts\activate     # Windows
```

3. Installez les dépendances :
```bash
pip install -r requirements.txt
```

---

## 🚀 Utilisation

Les notebooks sont organisés étape par étape :

- Démarrez Jupyter Lab ou Jupyter Notebook :
```bash
jupyter lab
```

- Ouvrez les notebooks dans le dossier `Notebooks/` et exécutez-les dans l’ordre :
  1. `01_exploration_donnees.ipynb`
  2. `02_nettoyage_features.ipynb`
  3. ...
  8. `08_model_svr.ipynb`

---


