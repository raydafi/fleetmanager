# 🚗 FleetManager

**FleetManager** est une application de bureau développée en **C# (Windows Forms)** permettant la gestion complète d'une flotte automobile d'entreprise. Elle permet de suivre les véhicules, les conducteurs, l'historique des utilisations et les coûts associés, avec un système de gestion des droits utilisateurs sécurisé.

![Status](https://img.shields.io/badge/Status-Completed-success)
![Technology](https://img.shields.io/badge/Tech-C%23%20%7C%20WinForms%20%7C%20MySQL-blue)

## 🌟 Fonctionnalités Principales

* **Tableau de Bord Intelligent :**
    * Visualisation des statistiques par conducteur et par véhicule (système d'onglets).
    * Calcul automatique des coûts carburant estimés et du kilométrage total de la flotte.
* **Gestion des Véhicules :** Ajout, modification et suppression de véhicules (Immatriculation, Modèle, Prix au litre, etc.).
* **Suivi des Utilisations :** Historique des trajets effectués par les conducteurs.
* **Sécurité & Utilisateurs :**
    * Système de connexion sécurisé.
    * **Hachage des mots de passe** avec [BCrypt](https://github.com/BcryptNet/bcrypt.net).
    * **Gestion des rôles** (Admin, Manager, User).
    * Interface adaptative : Les fonctionnalités d'administration (Gestion utilisateurs/véhicules) sont masquées pour les utilisateurs standards.

## 🛠️ Prérequis Techniques

Pour faire fonctionner l'application sur votre poste, vous avez besoin de :

1.  Un PC sous **Windows**.
2.  Le Framework .NET (généralement inclus dans Windows ou avec l'exécutable).

## 📥 Installation et Configuration

Suivez ces étapes scrupuleusement pour installer l'environnement.

### Étape 1 : Installation de la Base de Données (WampServer)

L'application nécessite une base de données locale pour fonctionner.

1.  Téléchargez et installez [WampServer](https://www.wampserver.com/).
2.  Lancez WampServer (l'icône doit passer au vert dans la barre des tâches).
3.  Ouvrez votre navigateur et accédez à **phpMyAdmin** (généralement à l'adresse `http://localhost/phpmyadmin`).
4.  Connectez-vous (Par défaut : Utilisateur = `root`, Mot de passe = *laisser vide*).

### Étape 2 : Création de la Base de Données

1.  Dans phpMyAdmin, cliquez sur **"Nouvelle base de données"**.
2.  Nommez la base de données : `fleetmanager` (Respectez exactement ce nom, tout en minuscules).
3.  Cliquez sur **Créer**.

### Étape 3 : Création des Tables (Script SQL)

Pour que l'application fonctionne, elle a besoin d'une structure précise (tables `users`, `vehicules`, `utilisations`).

1.  Allez dans l'onglet **SQL** de votre base de données `fleetmanager`.
2.  **Copiez et collez** les requêtes SQL situées dans le fichier fleetmanager/db.sql présent dans ce dépôt GitHub.
3.  Exécutez la requête.

> **Note :** Assurez-vous d'avoir au moins un utilisateur "admin" dans la table `users` pour pouvoir vous connecter la première fois. Si le script ne le crée pas, insérez-le manuellement avec un mot de passe connu.

### Étape 4 : Téléchargement de l'Application

Vous n'avez pas besoin de compiler le code si vous voulez juste utiliser l'application. Téléchargez l'exécutable prêt à l'emploi ici :

👉 **[Lien de téléchargement (SwissTransfer)] : https://www.swisstransfer.com/d/632013a8-94e2-4dbf-bc89-7a3f7b2f3908**

1.  Téléchargez le fichier `.zip` ou `.exe`.
2.  Si c'est un ZIP, extrayez tout le contenu dans un dossier.
3.  Lancez `FleetManager.exe`.

---

## 🚀 Utilisation

1.  Lancez l'application.
2.  Connectez-vous avec vos identifiants.
    * *Note : Le système détectera automatiquement si votre mot de passe n'est pas encore crypté et le sécurisera à la première connexion.*
3.  Si vous êtes **Admin**, vous verrez tous les boutons (Ajout Utilisation, Gérer Véhicules, Gérer Utilisateurs).
4.  Si vous êtes **User**, vous ne pourrez qu'ajouter des utilisations.

   Vous retrouverez un tutoriel pour l'utilisation dans le fichier tuto.pdf

## 🏗️ Architecture du Code

Le projet respecte le modèle **MVC (Modèle-Vue-Contrôleur)** pour une meilleure maintenance :

* **📂 Controllers :** Contient la logique métier et fait le lien entre la base de données et l'interface (`Controller.cs`).
* **📂 Models :** Contient les définitions des objets (`User.cs`, `Vehicule.cs`).
* **📂 Services :** Gère la connexion technique à MySQL (`DataService.cs`).
* **📂 Views :** Contient les formulaires Windows Forms (`Accueil.cs`, `Connexion.cs`, etc.).

## 📦 Dépendances (NuGet)

* `MySqlConnector` : Pour la communication avec la base de données MySQL.
* `BCrypt.Net-Next` : Pour le hachage sécurisé des mots de passe.

---
*Projet réalisé dans le cadre d'un développement C# WinForms.*
