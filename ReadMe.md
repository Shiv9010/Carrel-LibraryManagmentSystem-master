📚 Library Management System (SQL-Based)
A simple yet functional Library Management System built primarily using SQL for managing books, members, and transactions in a library database. Ideal for learning database design, normalization, and query handling.

🗂️ Project Overview
This project contains the SQL scripts necessary to:

Create and manage a library database

Store information about books, members, and borrow transactions

Handle book issues, returns, and due dates

Run queries for reporting and analytics

🛠️ Features
✅ Create tables with constraints (Primary Keys, Foreign Keys, etc.)

✅ Add, update, and delete records (CRUD operations)

✅ Issue and return books with date tracking

✅ Prevent double issue of the same book

✅ Calculate overdue fines (if applicable)

✅ View available vs issued books

✅ Search functionality using SQL LIKE and JOIN queries

🧩 Database Schema
The system typically includes the following tables:

Books – Stores details like title, author, genre, quantity

Members – Library user data like name, email, registration date

IssuedBooks – Tracks issued books, issue and return dates

Admins (optional) – For authentication or admin records

ER Diagram and schema design provided in /diagrams/ folder (optional)

📁 Project Structure
pgsql
Copy
Edit
library-management-system/
│
├── create_tables.sql         # SQL script to create all required tables
├── insert_sample_data.sql    # Sample data for testing
├── procedures.sql            # Stored procedures or triggers (if any)
├── queries.sql               # Useful SELECT queries
├── readme.md                 # Project documentation
└── diagrams/                 # (Optional) ER Diagrams or schema images
▶️ How to Run
Install any SQL RDBMS (like MySQL, PostgreSQL, SQLite)

Open your SQL client (MySQL Workbench, pgAdmin, etc.)

Execute create_tables.sql to set up the schema

Run insert_sample_data.sql to populate tables with sample data

Use queries.sql to test the functionality

🧪 Example Queries
sql
Copy
Edit
-- Find all books currently issued
SELECT b.title, i.member_id, i.issue_date 
FROM Books b
JOIN IssuedBooks i ON b.book_id = i.book_id
WHERE i.return_date IS NULL;

-- Find overdue books
SELECT * FROM IssuedBooks
WHERE return_date IS NULL AND DATEDIFF(CURRENT_DATE, issue_date) > 14;
📸 Screenshots
(Include screenshots of your schema, query output, or any GUI if built)

📃 License
This project is for educational purposes. You may use and modify it freely.
