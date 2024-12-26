# TD3 : Spatial SQL Functions

This guide explains advanced spatial SQL functions for analyzing and manipulating spatial data in PostGIS. By the end of this tutorial, you will learn how to perform spatial queries such as proximity analysis and area calculations.

---

## Prerequisites
- A PostgreSQL database with PostGIS installed and configured (refer to TD1 if needed).
- Spatial tables with relevant geometry data (refer to TD2 for creating spatial tables).

---

## Objectives
1. Count the number of parcels within a 1 km radius of specific fixed points.
2. Calculate the total area of parcels near the fixed points.

---

## Steps to Follow

### 1. Download and Import the Parcels Shapefile

#### Download the Shapefile
- Use the following [link](#) to download the parcel shapefile.

#### Import the Shapefile into PostGIS
1. Open the PostGIS Shapefile Import/Export Manager.
2. Use the downloaded shapefile and import it in the SRID 4326.
3. Select relevant data options.
4. Specify the database connection details.
5. Click **Import** to load the shapefile into your database.

---

### 2. Count Parcels Within 1 km Radius

Use the following SQL query to count the parcels within 1 km of the specified fixed points:

\`\`\`sql
SELECT COUNT(*)
FROM public.\"parcels\"
WHERE ST_DWithin(
    geom,
    (SELECT geom FROM public.\"fixed_points\" WHERE gid = 43227),
    1000
);
\`\`\`

---

### 3. Calculate Total Area of Parcels

To calculate the total area of the parcels within the same radius, use the following SQL query:

\`\`\`sql
SELECT SUM(ST_Area(geom))
FROM public.\"parcels\"
WHERE ST_DWithin(
    geom,
    (SELECT geom FROM public.\"fixed_points\" WHERE gid = 43227),
    1000
);
\`\`\`

---

## Additional Notes

### 1. Visualization in QGIS
- Display the parcel layer in QGIS by right-clicking on it and selecting **Add Layer**.
- Apply a filter using the following SQL to display parcels within the 1 km radius:

\`\`\`sql
ST_DWithin(geom, (SELECT ST_Buffer(geom, 1000) FROM public.\"fixed_points\" WHERE gid = 43227), 1000)
\`\`\`

#### Steps to Apply the Filter:
1. Right-click on the displayed layer and select **Filter**.
2. Enter the SQL condition in the query editor.
3. Click **OK** to apply the filter.

---

## Resources
- [PostGIS Documentation](https://postgis.net/documentation/)
- [QGIS Documentation](https://qgis.org/en/docs/index.html)

"