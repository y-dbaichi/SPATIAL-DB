# TD1 : Introduction à Spatial SQL

Ce guide détaille les étapes d'installation de PostGIS et de configuration de votre première base de données spatiale. PostGIS est une extension puissante de PostgreSQL, qui permet d'effectuer des opérations avancées de SIG (Systèmes d'Information Géographique) dans un système de gestion de bases de données relationnelles.

---

## Prérequis
- PostgreSQL doit être installé sur votre machine.
- Accès Internet pour télécharger les extensions et outils nécessaires.

---

## Étapes à Suivre

### 1. Installer PostgreSQL
- Rendez-vous sur la page de téléchargement officielle de PostgreSQL et sélectionnez la version adaptée à votre système d'exploitation (Windows, macOS ou Linux).
- Suivez les instructions d'installation pour configurer PostgreSQL.
- Définissez un mot de passe pour l'utilisateur \`postgres\` lors de l'installation.

### 2. Installer PostGIS
- Pendant l'installation de PostgreSQL, veillez à sélectionner tous les composants, y compris l'outil Stack Builder.
- Lancez Stack Builder et sélectionnez la version de PostgreSQL installée.
- Dans la liste des applications, choisissez PostGIS et suivez les instructions à l'écran pour terminer l'installation.

### 3. Créer votre première base de données spatiale
- Ouvrez **pgAdmin 4**, l'outil de gestion des bases de données PostgreSQL.
- Connectez-vous au serveur PostgreSQL avec les identifiants définis lors de l'installation.
- Cliquez avec le bouton droit sur **Bases de données** et sélectionnez **Créer > Base de données**.
- Donnez un nom à votre base de données (par exemple, \`spatial_db\`) et enregistrez.
- Ouvrez l'outil de requête pour votre base de données et exécutez la commande suivante pour activer PostGIS :
  \`\`\`sql
  CREATE EXTENSION postgis;
  \`\`\`
- Vérifiez l'installation en recherchant la table \`spatial_ref_sys\` sous **Schémas > Public > Tables**.

---

## Prochaines Étapes
Une fois votre base de données spatiale configurée, vous pouvez passer à la création de tables avec des colonnes spatiales et à l'exécution d'opérations SIG avec SQL. Consultez **TD2** pour plus de détails sur la création de tables spatiales.

---

## Ressources
- [Documentation PostGIS](https://postgis.net/documentation)
- [Documentation PostgreSQL](https://www.postgresql.org/docs)