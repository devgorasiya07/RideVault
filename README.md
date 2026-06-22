# 🚕 RideVault

RideVault is a comprehensive, object-oriented, database-driven ride-sharing platform (Uber/Ola clone). It demonstrates enterprise-level backend engineering, strict database schema management, and real-world mathematical routing algorithms.

### ✨ Key Features:
* **Enterprise PostgreSQL Schema:** 13+ tables with strict constraints, cascading deletes, and sequence management.
* **Geospatial Routing:** Utilizes the real-world **Haversine formula** for precise GPS distance calculation between city coordinates.
* **Dynamic Pricing Engine:** Calculates fares using live database rules, minimum fare checks, and geographical surge multipliers.

---

## 📁 Project Structure

    RideVault/
    ├── DDL.sql                      # SQL schema definitions (Tables, Keys, Constraints)
    ├── DataInsertion.sql            # Inserts sample data into tables
    ├── DQL.sql                      # SELECT queries for analysis
    ├── ERD.jpg                      # Entity-Relationship Diagram (image)
    └── RelationalDiagram.pdf        # Detailed relational model (PDF)

---

## 🛠️ Requirements

To run this project locally, you will need the following installed on your machine:

* **Database Engine:** PostgreSQL or a compatible SQL database
* **SQL Client:** pgAdmin 4 (Highly Recommended)

---

## 🚀 Setup Instructions

### 1. Clone the repository

    git clone https://github.com/devgorasiya07/RideVault.git
    cd RideVault

### 2. Configure the Database (pgAdmin)

1. Open **pgAdmin** and connect to your local PostgreSQL server.
2. Right-click on Databases -> Create -> Database...
3. Name the new database `RideVault` and save.
4. Right-click on your new `RideVault` database and select **Query Tool**.

### 3. Execute SQL files in this exact order:

1. **Open `DDL.sql`**, copy all content, and run it.
   *(This will create the enterprise database schema).*
2. **Open `DataInsertion.sql`**, copy all content, and run it.
   *(This will insert all necessary sample data).*
3. **Open `DQL.sql`**, copy all content, and run it. (Optional)
   *(This will run pre-built analysis queries).*
---

## 📊 Diagrams

To truly understand the relational flow of data, refer to the included diagrams:

* **`ERD.jpg`** – A high-level Entity-Relationship Diagram.
* **`RelationalDiagram.pdf`** – The full, deep-dive relational schema with strict data types.

---

## 🧩 Customize It

Once you have the project running, you can scale it further:

* **PL/pgSQL Triggers:** Write automated triggers (e.g., automatically insert a row into `WALLET_TRANSACTIONS` the moment a `Ride` status is updated to 'COMPLETED').
* **Extend Analytics:** Modify `DQL.sql` to include complex analytical queries.
