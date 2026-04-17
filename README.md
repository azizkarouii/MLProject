# Return/Refund Propensity Classification — Olist E-Commerce

## 👤 Auteur
Mohamed Aziz Karoui & Wassim Sioud — [Ecole Polytechnique Sousse / Genie Informatique]

---

## 📦 Description du Dataset

| Caractéristique | Détail |
|---|---|
| **Source** | [Kaggle — Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) |
| **Volume** | ~100 000 commandes (2016–2018) |
| **Fichiers** | 9 fichiers CSV interconnectés |
| **Licence** | CC BY-NC-SA 4.0 |

Le dataset contient des informations réelles et anonymisées sur des commandes passées sur la
plateforme Olist au Brésil : statut des commandes, prix, paiements, localisation des clients et vendeurs,
caractéristiques des produits, et avis clients.

---

## ❓ Problématique

> **Peut-on prédire quelles commandes sont à risque de retour/remboursement ?**

La variable cible est `is_return_refund_risk` (classification binaire).
Proxy utilisé dans ce projet (pré-livraison) :
- `1` → commande à risque élevé (commande annulée/non disponible)
- `0` → commande à faible risque

Cette problématique est utile pour Olist : anticiper les commandes risquées, améliorer le fulfillment,
et aider la détection de fraude.

---

## 🗂️ Structure du Repository

```
olist-return-refund-propensity/
│
├── data/
│   └── download_instructions.md   # Comment télécharger le dataset depuis Kaggle
│
├── notebooks/
│   ├── 01_EDA.ipynb               # Analyse Exploratoire des Données
│   ├── 02_Modeling.ipynb          # Version finale (modèles retenus)
│   └── brouillon_essai.ipynb      # Essais multiples d'algorithmes/paramètres
│
├── src/
│   ├── __init__.py
│   ├── data_loader.py             # Chargement et fusion des 9 tables CSV
│   ├── preprocessing.py           # Nettoyage, encodage, feature engineering
│   └── evaluation.py             # Métriques et visualisation des résultats
│
├── requirements.txt               # Dépendances Python
├── README.md                      # Ce fichier
└── .gitignore                     # Fichiers à exclure de Git
```

---

## ⚙️ Installation & Lancement

### 1. Cloner le repository
```bash
git clone https://github.com/azizkarouii/MLProject.git
cd MLProject
```

### 2. Créer un environnement virtuel
```bash
python -m venv venv
source venv/bin/activate        # Linux / macOS
venv\Scripts\activate           # Windows
```

### 3. Installer les dépendances
```bash
pip install -r requirements.txt
```

### 4. Télécharger le dataset
Suis les instructions dans `data/download_instructions.md`.
Place les 9 fichiers CSV dans le dossier `data/`.

### 5. Lancer les notebooks
```bash
jupyter notebook
```
Ouvre d'abord `notebooks/01_EDA.ipynb`, puis `notebooks/02_Modeling.ipynb`.

---

## 📊 Résumé des Résultats

> *(À compléter après l'exécution complète des notebooks)*

| Modèle | F1-Score | AUC-ROC | Accuracy |
|---|---|---|---|
| Logistic Regression | — | — | — |
| Decision Tree | — | — | — |
| Random Forest | — | — | — |
| XGBoost (bonus) | — | — | — |

**Meilleur modèle** : Random Forest (à confirmer après exécution)

**Features les plus importantes** : ratio frais de port, variables paiement, volume d'articles, variables produit

---

## 🔑 Features Créées (Feature Engineering)

| Feature | Description |
|---|---|
| `freight_ratio` | Frais de port / prix total |
| `price_per_item` | Prix moyen par article de la commande |
| `purchase_month` | Mois d'achat de la commande |
| `purchase_day_of_week` | Jour de semaine d'achat |
| `is_return_refund_risk` | Variable cible binaire de risque return/refund |

---

## 📚 Références

- Dataset : https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce
- Scikit-learn : https://scikit-learn.org/
- XGBoost : https://xgboost.readthedocs.io/
