# TD2 : Creating Tables with Spatial Columns

---

## 1. Create Spatial Tables (Points)

Utilisez la commande SQL suivante pour créer une table \`points_of_interest\` avec une colonne géométrique de type \`Point\` :

\`\`\`sql
CREATE TABLE points_of_interest (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    location GEOMETRY(Point, 4326)
);
\`\`\`

### Étapes pour insérer des données avec QGIS :
1. Établissez une connexion à votre base de données depuis QGIS :
    - Faites un clic droit sur **PostGIS** dans le panneau du navigateur.
    - Sélectionnez **Nouvelle Connexion** et renseignez les informations suivantes :
        - **Nom de la base de données**
        - **Nom d’utilisateur et mot de passe**
        - **Hôte et port**
2. Ouvrez la connexion.
3. Dans l’affichage de la base de données, double-cliquez sur la table \`points_of_interest\` pour l’ajouter comme couche dans QGIS.
4. Passez en mode édition et ajoutez des points directement sur la carte.
5. Sauvegardez vos modifications.

### Vérification :
Pour vérifier les données insérées, exécutez la requête suivante dans votre base de données :

\`\`\`sql
SELECT * FROM points_of_interest;
\`\`\`

---

## 2. Create Spatial Tables (Polygons)

Pour créer une table \`park_boundaries\` avec une colonne géométrique de type \`Polygon\`, utilisez la commande SQL suivante :

\`\`\`sql
CREATE TABLE park_boundaries (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    area GEOMETRY(Polygon, 4326)
);
\`\`\`

### Étapes :
1. Insérez des données dans la table en utilisant QGIS, puis sauvegardez vos modifications.
2. Vérifiez les données avec la requête suivante :

\`\`\`sql
SELECT * FROM park_boundaries;
\`\`\`

---

## 3. Create a Spatial Table with a LineString Column

Pour créer une table \`roads\` contenant une colonne spatiale de type \`LineString\`, utilisez la commande SQL suivante :

\`\`\`sql
CREATE TABLE roads (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    path GEOMETRY(LineString, 4326)
);
\`\`\`

### Exemple de vérification des données :
Exécutez la requête suivante pour vérifier les données :

\`\`\`sql
SELECT * FROM roads;
\`\`\`

---

## Ressources
- [Documentation officielle PostGIS](https://postgis.net/documentation/)
- [Documentation QGIS](https://qgis.org/en/docs/index.html)