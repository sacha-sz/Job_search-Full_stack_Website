# 🌐 SR10 – Plateforme de Gestion d'Offres d'Emploi

Ce dépôt contient le code source du projet **SR10** réalisé dans le cadre de l'UV **SR10** à l'**UTC** (Université de Technologie de Compiègne), consacrée au **développement web full-stack**.

L'application est une plateforme de gestion des offres d'emploi et des candidatures, développée avec **Node.js / Express** et une base de données **MySQL**.

<br/>

## 📌 Fonctionnalités principales

| Fonctionnalité | Description |
|---|---|
| 🔐 **Authentification** | Inscription, connexion sécurisée, protection anti-brute force |
| 📋 **Offres d'emploi** | Création, édition, suppression et consultation des offres |
| 📝 **Candidatures** | Dépôt de candidatures avec CV et lettre de motivation |
| 🏢 **Entreprises** | Gestion des entreprises et recruteurs |
| 👤 **Profils utilisateurs** | Visualisation et modification du profil |
| 🛡️ **Administration** | Gestion des utilisateurs et des entreprises via un espace admin |

<br/>

## 🗂 Organisation du projet

| Dossier | Contenu |
|---|---|
| [`doc/`](doc/) | Documents du projet : MCD, MLD, Use Case, rapport de sécurité |
| [`src/`](src/) | Code initial (HTML, JS, SQL de référence) |
| [`myapp/`](myapp/) | Application Node.js principale |
| [`myapp/model/`](myapp/model/) | Couche **Modèle** (accès BDD) |
| [`myapp/routes/`](myapp/routes/) | Couche **Contrôleur** (routes Express) |
| [`myapp/views/`](myapp/views/) | Couche **Vue** (templates EJS) |
| [`myapp/CSS/`](myapp/CSS/) | Feuilles de style |
| [`myapp/JobHub/`](myapp/JobHub/) | Mini-projet Vue.js (TD complémentaire) |
| [`myapp/mesfichiers/`](myapp/mesfichiers/) | Fichiers déposés par les utilisateurs (CV, LM) |
| [`myapp/test/`](myapp/test/) | Tests unitaires et d'intégration (Jest) |

<br/>

## 🏗 Architecture MVC

L'application suit le patron **Modèle-Vue-Contrôleur** :

```
myapp/
├── model/        ← Modèle     : accès à la base de données MySQL
├── routes/       ← Contrôleur : logique métier et routing Express
└── views/        ← Vue        : templates EJS rendus côté serveur
```

<br/>

## 🛠 Installation et lancement

### Prérequis

- [Node.js](https://nodejs.org/) v16+
- [MySQL](https://www.mysql.com/) — base de données requise

### Installation

```bash
# Cloner le dépôt
git clone https://github.com/sacha-sz/UTC-SR10.git
cd UTC-SR10/myapp

# Installer les dépendances
npm install
```

### Configuration de la base de données

Importer le schéma SQL depuis [`src/SQL/`](src/SQL/) dans votre instance MySQL, puis configurer les accès dans [`myapp/model/ConnexionBDD.js`](myapp/model/ConnexionBDD.js).

### Lancement

```bash
# Mode production
npm start

# Mode développement (rechargement automatique)
npm run start:dev
```

L'application est accessible sur `http://localhost:3000`.

<br/>

## 🧪 Tests

Les tests sont écrits avec **Jest** et **Supertest**.

```bash
cd myapp
npm test
```

| Fichier de test | Couverture |
|---|---|
| [`hello.test.js`](myapp/test/hello.test.js) | Vérification de base |
| [`Route_entreprise.test.js`](myapp/test/Route_entreprise.test.js) | Tests d'intégration des routes entreprise |
| [`Unit_Utilisateur.test.js`](myapp/test/Unit_Utilisateur.test.js) | Tests unitaires du modèle utilisateur |

<br/>

## 🔒 Sécurité

Trois vulnérabilités identifiées et corrigées — détail dans [`doc/Securite.md`](doc/Securite.md) :

| Vulnérabilité | Mesure appliquée |
|---|---|
| **Injection SQL** | Requêtes paramétrées avec `?` (aucune concaténation directe) |
| **Brute force** | Blocage du compte après plusieurs tentatives échouées |
| **Mots de passe** | Hachage avec `bcrypt` avant stockage |

<br/>

## 🧰 Technologies utilisées

| Technologie | Rôle |
|---|---|
| **Node.js + Express** | Serveur web et routing |
| **EJS** | Moteur de templates HTML |
| **MySQL** | Base de données relationnelle |
| **Vue.js** | Interface réactive (module JobHub) |
| **bcrypt** | Hachage des mots de passe |
| **Jest + Supertest** | Tests unitaires et d'intégration |
| **multer** | Upload de fichiers (CV, LM) |

<br/>

## 📄 Licence

Ce projet est sous licence **MIT** – voir le fichier [LICENSE](LICENSE) pour plus de détails.

<br/>

## 👥 Auteurs

- **[@sacha-sz](https://github.com/sacha-sz)**
- **[@TobiasInfo](https://github.com/TobiasInfo)**

<br/>

## 🔗 Références

- [UTC – Université de Technologie de Compiègne](https://www.utc.fr/)
- [🔒 Cours SR10 sur Moodle (accès UTC requis)](https://moodle.utc.fr/)
