# Spatial Database

## TD-1: Installation of PostGIS and Creation of a Spatial Database

### 1. Download and Install PostgreSQL
- Go to the [PostgreSQL download page](https://www.postgresql.org/download/) to download the latest version of PostgreSQL for your operating system (Linux, MacOS, Windows, BSD, Solaris).
- Follow the installation guide to install the software.
- Set a password for the `Postgres` user during installation. **Note: Use an easy-to-remember password.**

### 2. Download and Install PostGIS
- During the installation of PostgreSQL, check all the necessary components (including **Stack Builder**).
- Launch **Stack Builder** to download PostGIS.
- Select the corresponding version of PostgreSQL, and download PostGIS.
- Once the installation is complete, click **Close**.

### 3. Create a Database using PgAdmin 4
- Launch **pgAdmin** and log in using the password set for `Postgres`.
- Expand `Servers` > Right-click on PostgreSQL > **Create** > **Database**.
- Name your database, such as `spatial-db-1`, and click **Save**.
- Expand `Databases`, go to your new database, and add the PostGIS extension with the following command in **Query Tool**:
  ```sql
  CREATE EXTENSION postgis;
  ```