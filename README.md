# 🚕 RideVault

RideVault is a comprehensive, object-oriented, database-driven ride-sharing platform (Uber/Ola clone). It demonstrates enterprise-level backend engineering, strict database schema management, and real-world mathematical routing algorithms.

### ✨ Key Features:
* **Enterprise PostgreSQL Schema:** 13+ tables with strict constraints, cascading deletes, and sequence management.
* **Interactive CLI Dashboard:** Java-based backend simulating a real-world application for both Riders and Drivers.
* **Geospatial Routing:** Utilizes the real-world **Haversine formula** for precise GPS distance calculation between city coordinates.
* **Dynamic Pricing Engine:** Calculates fares using live database rules, minimum fare checks, and geographical surge multipliers.

---

## 📁 Project Structure

```text
RideVault/
├── src/main/java/com/ridevault/ # Java OOP Backend (Models, DAOs, Services, CLI)
├── DDL.sql                      # SQL schema definitions (Tables, Keys, Constraints)
├── DataInsertion.sql            # Inserts sample data into tables
├── DQL.sql                      # SELECT queries for analysis
├── ERD.jpg                      # Entity-Relationship Diagram (image)
└── RelationalDiagram.pdf        # Detailed relational model (PDF)
```

---

## 🛠️ Requirements

To run this project locally, you will need the following installed on your machine:

* **Java Development Kit (JDK):** Version 17 or higher
* **Database Engine:** PostgreSQL or a compatible SQL database
* **SQL Client:** pgAdmin 4 (Highly Recommended)
* **IDE:** VS Code, IntelliJ IDEA, or Eclipse
* **Viewer:** Any standard Image/PDF viewer to open the database diagrams

---

## 🚀 Setup Instructions

### 1. Clone the repository

```bash
git clone [https://github.com/yourusername/RideVault.git](https://github.com/yourusername/RideVault.git)
cd RideVault
```

### 2. Configure the Database (pgAdmin)

1. Open **pgAdmin** and connect to your local PostgreSQL server.
2. Right-click on Databases -> Create -> Database...
3. Name the new database `RideVault` and save.
4. Right-click on your new `RideVault` database and select **Query Tool**.

### 3. Execute SQL files in this exact order:

1. **Open `DDL.sql`**, copy all content, and run it.
   📌 *This will create the enterprise database schema (tables, constraints, foreign keys).*

2. **Open `DataInsertion.sql`**, copy all content, and run it.
   📌 *This will insert all necessary sample data (Fare Rules, Surge Zones, Base Users) into the tables.*

3. **Open `DQL.sql`**, copy all content, and run it. (Optional)
   📌 *This will run pre-built analysis queries to show analytical insights and ride history.*

### 4. Run the Java Application

1. Open the project folder in your preferred Java IDE.
2. Navigate to `src/main/java/com/ridevault/DatabaseConnection.java`.
3. Update the `PASSWORD` and `USER` variables to match your local PostgreSQL credentials.
4. Run `Main.java` to launch the interactive dashboard.
5. Choose your portal (Rider or Driver) and test the system!

---

## 📊 Diagrams

To truly understand the relational flow of data, refer to the included diagrams:

* **`ERD.jpg`** – A high-level Entity-Relationship Diagram showing how Users, Rides, Wallets, and Vehicles interact.
* **`RelationalDiagram.pdf`** – The full, deep-dive relational schema with strict data types, exact column names, and cardinality limits.

*(Open these files using your operating system's default image or PDF viewer).*

---

## 🧩 Customize It

Once you have the project running, you can scale it further:

* **Expand Locations:** Open `Location.java` and add more real-world GPS coordinates to expand the serviceable area beyond the initial launch city.
* **Database Migration:** Adjust SQL data types in the DDL if you wish to migrate the architecture from PostgreSQL to MySQL or Oracle.
* **Extend Analytics:** Modify `DQL.sql` to include complex analytical queries (e.g., determining peak surge hours, calculating total driver revenue, or tracking user retention).
