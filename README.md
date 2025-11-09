**Celestial Bodies Database**

## Overview

This repository contains the **Celestial Bodies Database** project, a SQL database challenge from FreeCodeCamp. The project simulates a universe database with interconnected celestial bodies including galaxies, stars, planets, moons, comets, asteroids, nebulas, and black holes. The database is designed to meet all FreeCodeCamp project requirements, including proper use of data types, primary and foreign keys, and relational integrity.

The main file in this repository is:

* `universe.sql` – SQL script to create the database, tables, relationships, and populate initial data.

---

## Database Features

### Tables

1. **Galaxy**

   * Contains basic galaxy information.
   * Columns: `galaxy_id` (PK), `name` (VARCHAR, UNIQUE), `galaxy_type` (VARCHAR), `age_in_millions_of_years` (INT), `distance_from_earth` (NUMERIC).

2. **Star**

   * Represents stars in galaxies.
   * Columns: `star_id` (PK), `name` (VARCHAR, UNIQUE), `galaxy_id` (FK), `mass` (NUMERIC), `has_life` (BOOLEAN), `age_in_millions_of_years` (INT).

3. **Planet**

   * Represents planets orbiting stars.
   * Columns: `planet_id` (PK), `name` (VARCHAR, UNIQUE), `star_id` (FK), `planet_type` (VARCHAR), `is_habitable` (BOOLEAN), `distance_from_star` (NUMERIC).

4. **Moon**

   * Represents moons orbiting planets.
   * Columns: `moon_id` (PK), `name` (VARCHAR, UNIQUE), `planet_id` (FK), `radius_km` (NUMERIC), `has_atmosphere` (BOOLEAN), `orbital_period_days` (INT).

5. **Comet**

   * Represents comets in the solar system.
   * Columns: `comet_id` (PK), `name` (VARCHAR, UNIQUE), `mass` (NUMERIC), `orbital_period_years` (NUMERIC), `has_tail` (BOOLEAN).

6. **Asteroid**

   * Represents asteroids.
   * Columns: `asteroid_id` (PK), `name` (VARCHAR, UNIQUE), `mass` (NUMERIC), `distance_from_earth` (NUMERIC), `is_potentially_hazardous` (BOOLEAN).

7. **Nebula**

   * Represents nebulas in galaxies.
   * Columns: `nebula_id` (PK), `name` (VARCHAR, UNIQUE), `galaxy_id` (FK), `nebula_type` (VARCHAR), `mass` (NUMERIC), `distance_from_earth` (NUMERIC).

8. **Black Hole**

   * Represents black holes.
   * Columns: `black_hole_id` (PK), `name` (VARCHAR, UNIQUE), `galaxy_id` (FK), `mass` (NUMERIC), `is_supermassive` (BOOLEAN), `distance_from_earth` (NUMERIC).

---

## Requirements Met

* **Database Name:** `universe`
* **Primary Keys:** Each table has a primary key named `table_name_id` that auto-increments.
* **Foreign Keys:** Proper foreign key relationships between stars → galaxies, planets → stars, moons → planets, etc.
* **Data Types:**

  * `INT` used for multiple numeric attributes.
  * `NUMERIC` used for precise measurements like mass or distance.
  * `TEXT` used for descriptions.
  * `BOOLEAN` used for flags like `has_life` or `is_habitable`.
* **Constraints:**

  * UNIQUE constraint on all `name` columns.
  * NOT NULL constraints on at least two columns per table.
* **Rows:**

  * Each table contains multiple rows to satisfy project requirements (e.g., galaxies and stars ≥ 6 rows, planets ≥ 12 rows, moons ≥ 20 rows).

---

## How to Run

1. Open a terminal and connect to PostgreSQL:

   ```bash
   psql --username=freecodecamp --dbname=postgres
   ```
2. Run the SQL script to create the database and tables:

   ```bash
   \i path/to/universe.sql
   ```
3. Verify the tables and data:

   ```sql
   \c universe
   \dt
   SELECT * FROM galaxy LIMIT 5;
   ```

---

## Project Notes

* Designed to pass **all FreeCodeCamp project tests**.
* Ensures **referential integrity** and **relational database best practices**.
* Can be used as a starting point for more advanced **astronomy-related SQL projects**.

---

## Repository Structure

```
celestial-bodies-database/
│
├── universe.sql         # Main SQL script to build the database
├── README.md            # Project documentation
```

---

## License

This project is open source and licensed under the MIT License.

---


