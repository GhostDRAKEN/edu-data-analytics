# 📊 Educational Data Analytics

> Plateforme d'analyse de données éducatives utilisant l'Intelligence Artificielle pour prédire les performances des étudiants et identifier ceux à risque d'échec.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.12-blue.svg)
![Flutter](https://img.shields.io/badge/flutter-3.x-blue.svg)
![Django](https://img.shields.io/badge/django-5.x-green.svg)

## 🎯 Objectif

Identifier **automatiquement** les étudiants à risque d'échec scolaire en utilisant le Machine Learning, et fournir des **recommandations personnalisées** pour améliorer leurs résultats.

## ✨ Fonctionnalités principales

### 📱 Application Mobile (Flutter)
- ✅ **Dashboard statistique** avec graphiques interactifs (camembert, barres)
- ✅ **Liste intelligente** avec filtres par profil (À risque, Moyen, Performant)
- ✅ **Recherche en temps réel** par nom/prénom
- ✅ **Détails étudiants** avec notes par matière et visualisations
- ✅ **Prédictions IA** pour tous les étudiants avec niveau de risque
- ✅ **Recommandations personnalisées** générées automatiquement

### 🔧 Backend API (Django)
- ✅ API REST complète (4 endpoints)
- ✅ Gestion de 1000+ étudiants
- ✅ Calcul automatique des profils
- ✅ Endpoints ML pour prédictions

### 🤖 Intelligence Artificielle
- ✅ **Modèle Random Forest** (95% de précision)
- ✅ Prédiction du risque d'échec
- ✅ Analyse des facteurs d'influence (feature importance)
- ✅ Génération automatique de recommandations

## 📸 Screenshots

### Dashboard Statistiques
![Stats](docs/screenshots/stats.png)
*Visualisation des répartitions avec graphique camembert*

### Liste des étudiants
![Liste](docs/screenshots/liste.png)
*Recherche et filtres intelligents*

### Détails étudiant
![Details](docs/screenshots/details.png)
*Notes par matière avec graphiques*

### Prédictions IA
![AI](docs/screenshots/predictions.png)
*Identification automatique des étudiants à risque*

### Recommandations personnalisées
![Reco](docs/screenshots/recommandations.png)
*Conseils adaptés générés par l'IA*

## 🛠️ Stack Technique

### Backend
- **Python 3.12**
- **Django 5.x** + Django REST Framework
- **scikit-learn** (Machine Learning)
- **Pandas & NumPy** (analyse de données)
- **SQLite** (base de données)

### Frontend Mobile
- **Flutter 3.x**
- **Dart**
- **fl_chart** (graphiques)
- **http** (API calls)

### Machine Learning
- **Random Forest Classifier**
- **Feature Engineering** (7 features)
- **joblib** (persistance du modèle)

## 📊 Performance du Modèle IA

| Métrique | Valeur |
|----------|--------|
| **Précision** | 95% |
| **Dataset** | 1000 étudiants |
| **Features** | 7 (notes, contexte familial, préparation) |
| **Algorithme** | Random Forest (100 estimateurs) |

### Features utilisées
1. Note en Mathématiques (importance: ~11%)
2. Note en Anglais (importance: ~20%)
3. Note en Sciences (importance: ~18%)
4. **Moyenne générale** (importance: ~49% - facteur principal)
5. Préparation aux tests
6. Type de repas (indicateur socio-économique)
7. Niveau d'éducation parental

## 🚀 Installation

### Prérequis
- Python 3.12+
- Flutter 3.x
- Git

### 1️⃣ Backend Django
```bash
# Cloner le repo
git clone https://github.com/GhostDRAKEN/edu-data-analytics.git
cd edu-data-analytics/backend

# Créer l'environnement virtuel
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Installer les dépendances
pip install -r requirements.txt

# Migrations
python manage.py migrate

# Charger les données (si disponible)
python manage.py loaddata students_data.json

# Lancer le serveur
python manage.py runserver
```

Le backend sera accessible sur `http://127.0.0.1:8000`

### 2️⃣ Application Mobile Flutter
```bash
# Aller dans le dossier Flutter
cd eduapp

# Installer les dépendances
flutter pub get

# Lancer sur émulateur/appareil
flutter run
```

### 3️⃣ Entraîner le Modèle IA
```bash
# Via API
curl -X POST http://127.0.0.1:8000/api/ml/train/

# Ou via Django shell
python manage.py shell
>>> from students.ml_model import StudentRiskPredictor
>>> predictor = StudentRiskPredictor()
>>> predictor.train()
```

## 📡 Endpoints API

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| GET | `/api/students/` | Liste tous les étudiants |
| GET | `/api/students/?profil=À risque` | Filtre par profil |
| GET | `/api/students/stats/` | Statistiques globales |
| GET | `/api/students/<id>/` | Détails d'un étudiant |
| POST | `/api/ml/train/` | Entraîne le modèle IA |
| GET | `/api/ml/predict/<id>/` | Prédit le risque pour 1 étudiant |
| GET | `/api/ml/predict/batch/` | Prédit pour tous les étudiants |

## 🏗️ Architecture
```
edu-data-analytics/
├── backend/                 # Django API
│   ├── education/          # App principale
│   ├── students/           # API étudiants + ML
│   │   ├── views.py       # Endpoints
│   │   ├── ml_model.py    # Modèle IA
│   │   └── serializers.py
│   └── manage.py
│
├── eduapp/                 # Flutter app
│   ├── lib/
│   │   ├── models/        # Modèles de données
│   │   ├── services/      # API services
│   │   ├── screens/       # Écrans
│   │   └── widgets/       # Composants réutilisables
│   └── pubspec.yaml
│
├── analysis/              # Notebooks Jupyter
└── docs/                  # Documentation
```

## 🎓 Ce que j'ai appris

Ce projet m'a permis de développer des compétences en :

- ✅ **Architecture fullstack** (Backend API + Mobile)
- ✅ **Machine Learning appliqué** (classification, feature engineering)
- ✅ **Développement Flutter** (navigation, state management, graphiques)
- ✅ **Design d'API REST** (Django REST Framework)
- ✅ **Visualisation de données** (graphiques interactifs)
- ✅ **Intégration IA dans une app réelle**

## 🔮 Améliorations futures

- [ ] Déploiement cloud (backend + base de données)
- [ ] Authentification utilisateur
- [ ] Export PDF des rapports
- [ ] Notifications push pour alertes
- [ ] Dashboard web admin
- [ ] Tracking de l'évolution dans le temps
- [ ] Support multi-langues

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à :
- 🐛 Signaler des bugs
- 💡 Proposer des fonctionnalités
- 🔧 Soumettre des pull requests

## 📄 Licence

Ce projet est sous licence MIT - voir le fichier [LICENSE](LICENSE) pour plus de détails.

## 👤 Auteur

**TOURE YAZID**

- GitHub: [@GhostDRAKEN](https://github.com/GhostDRAKEN)
- LinkedIn: [Ton profil]
- Portfolio: [ton-site.com]

---

⭐ **N'hésite pas à mettre une étoile si ce projet t'a été utile !**
