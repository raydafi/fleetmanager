# FleetManager

**FleetManager** est une application de bureau développée en **C# (Windows Forms)** permettant la gestion complète d'une flotte automobile d'entreprise. Elle permet de suivre les véhicules, les conducteurs, l'historique des utilisations, les coûts associés et la maintenance, avec un système de gestion des droits utilisateurs sécurisé.

![Status](https://img.shields.io/badge/Status-Completed-success)
![Technology](https://img.shields.io/badge/Tech-C%23%20%7C%20WinForms%20%7C%20MySQL-blue)

## Fonctionnalités Principales

L'application est structurée autour de plusieurs interfaces dédiées pour une navigation fluide et une gestion optimale :

* **Interface de Connexion :** Un accès sécurisé à l'application.
* **Tableau de Bord & Statistiques :** Une interface complète pour l'affichage des statistiques liées :
  * Aux véhicules.
  * Aux utilisateurs.
  * Aux utilisations des véhicules.
  * Aux coûts.
  * Aux entretiens.
* **Gestion des Véhicules :** Interface pour l'ajout, la modification et la suppression de véhicules.
* **Gestion des Utilisateurs :** Interface pour administrer les comptes et les rôles.
* **Saisie des Données :**
  * Interface d'**ajout d'une utilisation** (suivi des trajets).
  * Interface d'**ajout d'un entretien** (suivi de la maintenance).
* **Sécurité & Utilisateurs :**
    * **Hachage des mots de passe** avec [BCrypt](https://github.com/BcryptNet/bcrypt.net).
    * **Gestion des rôles** (Admin, Manager, User). L'interface s'adapte en fonction du rôle (masquage de l'administration pour les utilisateurs standards).

## Prérequis Techniques

Pour faire fonctionner l'application sur votre poste, vous avez besoin de :

1.  Un PC sous **Windows**.
2.  Le Framework .NET (généralement inclus dans Windows ou installé automatiquement avec l'exécutable).

*Note : La base de données est directement hébergée sur **alwaysdata**. Vous n'avez donc plus besoin d'installer de serveur local (comme WampServer) ou de configurer une base de données.*

## Installation et Configuration

L'installation a été simplifiée au maximum. Plus besoin de télécharger de fichier `.zip` ou de manipuler des scripts SQL.

1.  **Téléchargez l'installateur** depuis mon espace cloud :
    **[Lien de l'installateur](https://drive.google.com/file/d/1sbcGyxBRRlfSqcUJ1UBlZPZeZsXzr81_/view?usp=drive_link)**
2.  **Exécutez l'installateur** (`.exe`) que vous venez de télécharger.
3.  **Suivez simplement les étapes** affichées à l'écran par l'assistant d'installation.

---

## Utilisation

1.  Lancez l'application via le raccourci créé sur votre bureau ou dans le menu Démarrer.
2.  Pour votre **première connexion**, utilisez les identifiants administrateur par défaut :
    * **Login :** `admin`
    * **Mot de passe :** `admin`
    *(Note : Le système détectera automatiquement si votre mot de passe n'est pas encore crypté et le sécurisera à la première connexion. Il est recommandé de modifier ce mot de passe par la suite).*
3.  Si vous êtes **Admin**, vous aurez accès à toutes les interfaces (Ajout Utilisation, Ajout Entretien, Gestion Véhicules, Gestion Utilisateurs, Statistiques).
4.  Si vous êtes **User**, vos accès seront restreints aux actions de base (comme l'ajout d'utilisations).

## Architecture du Code

Le projet respecte le modèle **MVC (Modèle-Vue-Contrôleur)** pour une meilleure maintenance :

* **Controllers :** Contient la logique métier et fait le lien entre la base de données et l'interface (`Controller.cs`).
* **Models :** Contient les définitions des objets (`User.cs`, `Vehicule.cs`).
* **Services :** Gère la connexion technique à la base de données distante (`DataService.cs`).
* **Views :** Contient les formulaires Windows Forms (`Accueil.cs`, `Connexion.cs`, etc.).

## Dépendances (NuGet)

* `MySqlConnector` : Pour la communication avec la base de données MySQL hébergée sur alwaysdata.
* `BCrypt.Net-Next` : Pour le hachage sécurisé des mots de passe.

---
*Projet réalisé dans le cadre d'un développement C# WinForms.*
