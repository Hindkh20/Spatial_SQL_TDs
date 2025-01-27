# Spatial Database

## TD-2: Creating Tables with Spatial Columns

### Objective:
Create tables in PostgreSQL with spatial columns and manipulate these data using QGIS and PgAdmin.

---

### 1. Creating a Spatial Table (Points)

#### 1.1 Create the Table in PostgreSQL with PgAdmin
Open PgAdmin and connect to your PostgreSQL database. Create a table `points_of_interests` with a geometry column of type `Point` by executing the following query:

```sql
CREATE TABLE points_of_interests (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255),
    geom GEOMETRY(Point, 4326)
);
```

#### 1.2 Add Data in QGIS
To insert points into this table via QGIS:

1. Open QGIS.
2. In the **Browser** panel, right-click on **PostgreSQL** and select **New Connection**.
3. In the window that opens, enter the following information:
   - **Connection Name**: Choose a descriptive name for the connection.
   - **Host**: localhost (or the IP address of your server).
   - **Port**: 5432 (the default port for PostgreSQL).
   - **Database Name**: The name of your database.
   - **Username and Password**: Use the credentials you set during PostgreSQL installation.
4. Click **Test Connection** to ensure the settings are correct.
5. Once the connection is successfully created, double-click the `points_of_interests` table in the **Browser** panel. This will add the table as a layer in QGIS.
6. Switch to **Edit mode** to add points:
   - Click the **Edit** button in QGIS (pencil icon).
   - Click the **Add Point** button and place points on the map.
7. Once you have added points, click **Save Edits** in QGIS.

#### 2. Verification in PgAdmin
Go back to PgAdmin and run the following query to check that the points have been inserted into the table:

```sql
SELECT * FROM points_of_interests;
```

---

### 3. Creating a Spatial Table (Lines)

#### 3.1 Create the Table in PostgreSQL with PgAdmin

To create a table containing lines (`LINESTRING`) in PostgreSQL, open PgAdmin and execute the following query in your database:

```sql
CREATE TABLE rivers (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255),
    geom GEOMETRY(LINESTRING, 4326)
);
```

#### 3.2 Add Data in QGIS (see section 1.2)

#### 3.3 Verification:
Go back to PgAdmin and execute the following query to check that the lines have been inserted into the table:

```sql
SELECT * FROM rivers;
```

---

## Important Notes:

- **Coordinate System**: The geometries use SRID 4326 (WGS 84) in this example.
- **QGIS Connection**: Ensure that the PostgreSQL connection in QGIS is correctly configured to access the tables.
- **Edit Mode**: Always enable edit mode before adding or modifying data in QGIS.

This document provides a step-by-step guide for creating and manipulating spatial tables in PostgreSQL, as well as adding data via QGIS.