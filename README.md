# WordPress avec Docker Compose

Ce projet déploie une application WordPress complète avec une base de données MySQL en utilisant Docker Compose. La configuration est sécurisée grâce à l'utilisation de Docker Secrets pour les mots de passe et d'un fichier `.env` pour les variables de configuration.

## Prérequis

* Docker
* Docker Compose

## Structure du Projet

```
.
├── .env
├── docker-compose.yml
├── secrets/
│   ├── mysql_password.txt
│   └── mysql_root_password.txt
└── README.md
```

## Installation et Lancement

1.  **Clonez ce dépôt :**
    ```bash
    git clone <URL_DE_VOTRE_DEPOT>
    cd <NOM_DE_VOTRE_DEPOT>
    ```

2.  **Configurez les variables d'environnement :**
    Le fichier `.env` est déjà inclus et configure le nom d'utilisateur et le nom de la base de données. Vous pouvez le modifier si besoin.

3.  **Créez les fichiers de secrets :**
    Créez un dossier `secrets` et ajoutez-y les fichiers suivants. Remplacez les exemples par vos propres mots de passe sécurisés.

    * Créez `secrets/mysql_root_password.txt` et ajoutez le mot de passe root de MySQL.
    * Créez `secrets/mysql_password.txt` et ajoutez le mot de passe pour l'utilisateur de la base de données WordPress.

4.  **Lancez l'application :**
    Exécutez la commande suivante à la racine du projet.
    ```bash
    docker-compose up -d
    ```

5.  **Accédez à WordPress :**
    Une fois les conteneurs démarrés, ouvrez votre navigateur et allez à l'adresse suivante pour finaliser l'installation de WordPress :
    [http://localhost:8080](http://localhost:8080)

## Gestion des Conteneurs

* **Pour arrêter l'application :**
    ```bash
    docker-compose down
    ```
* **Pour arrêter et supprimer les volumes (toutes les données seront perdues) :**
    ```bash
    docker-compose down -v
    ```