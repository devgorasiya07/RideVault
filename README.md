# 🚕 RideVault

RideVault is a comprehensive, object-oriented, database-driven ride-sharing platform (Uber/Ola clone). It includes:

* Enterprise-grade PostgreSQL schema with strict constraints and sequence management
* Java-based backend simulating a real-world CLI interactive dashboard
* Advanced routing using the Haversine formula for precise GPS distance calculation
* Dynamic pricing engine utilizing live database fare rules and surge multipliers

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

🛠️ Requirements
Java Development Kit (JDK 17 or higher)

PostgreSQL or compatible SQL database

SQL client (pgAdmin 4 recommended)

Java IDE (VS Code, IntelliJ, or Eclipse)

Image/PDF viewer for diagrams (optional)

🚀 Setup Instructions
1. Clone the repository
Bash
git clone [https://github.com/yourusername/RideVault.git](https://github.com/yourusername/RideVault.git)
cd RideVault
2. Open pgAdmin (Database Setup)
Connect to your PostgreSQL server

Create a new database named RideVault

Open a new Query Tool tab for this database

3. Execute SQL files in this order:
Open DDL.sql, copy all content, and run it
📌 This will create the enterprise database schema (tables, constraints, keys)

Open DataInsertion.sql, copy all content, and run it
📌 This will insert sample data (Fare Rules, Surge Zones, Users) into the tables

Open DQL.sql, copy all content, and run it (Optional)
📌 This will run the analysis queries and show analytical insights

4. Run the Java Application
Open the project in your preferred Java IDE.

Navigate to src/main/java/com/ridevault/DatabaseConnection.java.

Update the PASSWORD variable with your local PostgreSQL password.

Run Main.java to launch the interactive Rider and Driver dashboards!

📊 Diagrams
ERD.jpg – Entity-Relationship Diagram showing high-level architecture

RelationalDiagram.pdf – Full relational schema with foreign keys and strict data types

Open with any image or PDF viewer.
