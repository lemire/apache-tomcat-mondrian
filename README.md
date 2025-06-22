# Mondrian avec Apache Tomcat

Ce projet propose une distribution de Mondrian OLAP Server intégrée à Apache Tomcat, prête à l'emploi pour l'expérimentation et l'apprentissage.

## Table des matières
- [Présentation](#présentation)
- [Prérequis](#prérequis)
- [Installation](#installation)
- [Configuration de Java](#configuration-de-java)
- [Démarrage du serveur](#démarrage-du-serveur)
- [Tests de l'installation](#tests-de-linstallation)
- [Arrêt du serveur](#arrêt-du-serveur)
- [Dépannage](#dépannage)
- [Ressources utiles](#ressources-utiles)

## Présentation
Ce dépôt fournit un environnement clé en main pour utiliser Mondrian avec Tomcat. Il est destiné à l'enseignement, à l'expérimentation et à la découverte de l'OLAP.

## Prérequis
- **Java JDK 21 ou supérieur** (Java 8 minimum, mais 21 recommandé)
- Système d'exploitation : Windows, macOS ou Linux
- Navigateur web moderne

## Installation
1. **Téléchargez le projet** :
   - [Archive ZIP du projet](https://github.com/lemire/apache-tomcat-mondrian/archive/refs/heads/main.zip)
2. **Décompressez l'archive** dans un dossier sans espaces ni caractères spéciaux (ex. `C:/MonCours` ou `~/mondrian-tomcat`).

## Configuration de Java
- Ouvrez un terminal (macOS/Linux) ou une invite de commandes (Windows).
- Vérifiez la version de Java :
  ```sh
  java -version
  javac -version
  ```
- Si besoin, installez le JDK depuis [Adoptium](https://adoptium.net).
- **Sous Windows** :
  - Ajoutez le dossier `bin` du JDK à la variable d'environnement `PATH`.
  - Définissez la variable `JAVA_HOME` :
    ```sh
    SET JAVA_HOME=C:\chemin\vers\votre\jdk
    ```

## Démarrage du serveur
1. **Vérifiez que le port 8080 est libre** :
   - Visitez [http://localhost:8080](http://localhost:8080). Si une page s'affiche, modifiez le port dans `conf/server.xml` (ex. 8090).
2. **Rendez-vous dans le dossier `bin`** du projet.
4. **Démarrez Tomcat** :
   - **Windows** :
     ```sh
     startup.bat
     ```
   - **macOS/Linux** :
     ```sh
     ./startup.sh
     ```
5. Accédez à [http://localhost:8080](http://localhost:8080) pour vérifier que Tomcat fonctionne.

## Tests de l'installation
- Rendez-vous sur [http://localhost:8080/mondrian-embedded/](http://localhost:8080/mondrian-embedded/).
- Cliquez sur **JPivot pivot table** pour tester l'interface graphique.
- Testez une requête MDX dans l'interface ad hoc :
  ```mdx
  select [Time].[1997] on columns from [Sales]
  ```
- Un résultat doit s'afficher.

## Arrêt du serveur
- **Windows** :
  ```sh
  shutdown.bat
  ```
- **macOS/Linux** :
  ```sh
  ./shutdown.sh
  ```

## Dépannage
- Si Tomcat ne démarre pas, vérifiez la configuration de Java (`JAVA_HOME`, `PATH`).
- Si le port 8080 est occupé, modifiez-le dans `conf/server.xml`.
- En cas de problème, faites des captures d'écran complètes de vos manipulations et transmettez-les à votre encadrant.

## Ressources utiles
- [Documentation officielle Tomcat](https://tomcat.apache.org/tomcat-9.0-doc/index.html)
- [Mondrian OLAP](http://mondrian.pentaho.com/)

---

*Merci de lire attentivement toutes les consignes avant de demander de l'aide. Les captures d'écran sont obligatoires pour tout support.*