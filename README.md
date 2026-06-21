# 🚕 RideVault: Enterprise Database Architecture

Welcome to the **RideVault Database Repository**. This project contains the complete, scalable Relational Database Management System (RDBMS) architecture for a robust ride-sharing application (similar to Uber or Ola). 

Designed with data integrity, geospatial tracking, and dynamic financial calculations in mind, this database serves as the unbreakable backbone for the RideVault ecosystem.

---

## 📊 Repository Structure

This repository is strictly organized into logical SQL layers and visual documentation:

* **`DDL.sql`** - **Data Definition Language:** The master blueprint. Contains all `CREATE TABLE` scripts, Primary/Foreign Key relationships, strict `NOT NULL` constraints, and sequence initializations.
* **`DataInsertion.sql`** - **Data Manipulation Language:** Contains robust mock data for Riders, Drivers, Fare Rules, and Locations to simulate a live production environment.
* **`DQL.sql`** - **Data Query Language:** Contains complex `SELECT`, `JOIN`, and analytical queries used by the backend to fetch ride history, calculate analytics, and filter available drivers.
* **`ERD.jpg`** - **Entity-Relationship Diagram:** A high-level visual map showing how entities (Users, Rides, Wallets, Vehicles) interact.
* **`RelationalDiagram.pdf`** - A comprehensive, deep-dive schematic of the database schema, detailing exact data types and cardinality.

---

## 🏗️ Core Architectural Features

This database goes beyond basic CRUD operations by implementing real-world business logic directly at the schema level:

* **Geospatial Tracking:** Utilizes strict `DECIMAL(9, 6)` coordinates (`pickup_lat`, `pickup_lng`) to ensure precise mapping and distance calculations (Haversine formula compatible).
* **Dynamic Pricing Engine:** A dedicated `FARE_RULES` and `SURGE_PRICING` schema that allows the backend to calculate real-time pricing based on vehicle category, distance, time, and high-demand geographical zones.
* **Transactional Wallet System:** A ledger-style `WALLET_TRANSACTIONS` table that records all credits/debits linked to specific `Ride_Ids`, ensuring zero financial leakage.
* **Strict State Management:** The `Ride` table utilizes indexed status columns (`PENDING`, `ACCEPTED`, `COMPLETED`) protected by relational constraints, preventing "race conditions" between drivers.
* **Session Management:** A `Driver_Session` table to track real-time driver availability and last-known GPS coordinates without overloading the core user table.

---

## 🛠️ Tech Stack

* **Database Engine:** PostgreSQL
* **Architecture:** Normalized Relational Database (3NF)
* **Design Tools:** pgAdmin 4, standard ERD modeling tools.

---

## 🚀 Getting Started (Local Setup)

To deploy this database on your local machine for testing or backend integration:

1. **Install PostgreSQL:** Ensure PostgreSQL and pgAdmin are installed on your machine.
2. **Create the Database:** Open pgAdmin, right-click on Databases, and create a new database named `"RideVault"`.
3. **Run the DDL:** Open the Query Tool, paste the contents of `DDL.sql`, and execute it to build the empty architecture.
4. **Seed the Data:** Clear the Query Tool, paste the contents of `DataInsertion.sql`, and execute it to populate the tables with testing data.
5. **Test the Logic:** Use `DQL.sql` to run sample queries and verify relational integrity.

---

## 💡 Developer Notes

* **Primary Key Sequences:** If manually inserting test data via the pgAdmin UI, remember to leave `SERIAL` ID columns blank to prevent sequence desynchronization (`duplicate key value violates unique constraint`).
* **Cascading Deletes:** Deleting a `Driver` or `Rider` will safely cascade down to their respective vehicles, wallets, and sessions to prevent orphaned data.
