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
- **Java JDK 21 ou supérieur** (Java 8 minimum, mais 21 ou mieux recommandé)
- Système d'exploitation : Windows, macOS ou Linux
- Navigateur web moderne

## Installation
1. **Téléchargez le projet** :
   - [Archive ZIP du projet](https://github.com/lemire/apache-tomcat-mondrian/archive/refs/heads/main.zip)
2. **Décompressez l'archive** dans un dossier sans espaces ni caractères spéciaux (ex. `C:/MonCours` ou `~/mondrian-tomcat`).

## Configuration de Java
- Ouvrez un terminal (macOS/Linux) ou une invite de commandes (Windows). Pour  une invite de commandes sous Windows, cliquez sur l’icône de recherche dans la barre des tâches ou appuyez sur Windows + S. Tapez Invite de commande ou cmd.
- Vérifiez la version de Java :
  ```sh
  java -version
  javac -version
  ```
- Si besoin, installez le JDK depuis [Adoptium](https://adoptium.net).

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
- Si Tomcat ne démarre pas, vérifiez la configuration de Java (`JAVA_HOME`, `PATH`). Sous Windows, voir la sous-section suivante. Sous Linux et macOS, tapez `echo $JAVA_HOME`.
- Si le port 8080 est occupé, modifiez-le dans `conf/server.xml`.
- En cas de problème, faites des captures d'écran complètes de vos manipulations et transmettez-les à votre encadrant.

### Variables d'environnement sous Windows

Par défault, l'outil d'installation Adoptium configure les variables `PATH` et `JAVA_HOME` correctment. Cependant, ces variables peuvent être mal configurées sur votre machine. Si les variables PATH et JAVA_HOME ne sont pas correctement configurées après l'installation d'Adoptium sur Windows 11, vous pouvez les ajuster manuellement. Ouvrez le menu Démarrer, recherchez "Variables d’environnement" et sélectionnez "Modifier les variables d’environnement du système". Dans la fenêtre qui s’ouvre, cliquez sur "Variables d’environnement". Sous "Variables système", vérifiez si JAVA_HOME existe et pointe vers le répertoire d’installation de Java (par exemple, C:\Program Files\Eclipse Adoptium\temurin-17-jdk). S’il est absent ou incorrect, créez ou modifiez JAVA_HOME avec le chemin correct. Ensuite, dans la variable Path (sous "Variables système"), ajoutez %JAVA_HOME%\bin si ce n’est pas déjà fait. Cliquez sur "OK" pour enregistrer, puis ouvrez une nouvelle invite de commande et tapez java -version pour vérifier.

## Ressources utiles
- [Documentation officielle Tomcat](https://tomcat.apache.org/tomcat-9.0-doc/index.html)
- [Mondrian OLAP](http://mondrian.pentaho.com/)

