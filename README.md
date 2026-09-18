# ✈️ Airport Management Analysis | SQL Project

A SQL-based Airport Management and Data Analysis project focused on managing airport operations and extracting meaningful insights from relational data.

The project demonstrates practical SQL skills including database design, table relationships, data manipulation, joins, filtering, aggregation, subqueries, and analytical queries.

---

## 📌 Project Overview

The Airport Management Analysis project is designed to organize and analyze airport-related information using a relational database.

The database can be used to manage and analyze entities such as:

- Airports
- Airlines
- Flights
- Passengers
- Employees
- Tickets
- Luggage
- Terminals
- Gates

The main objective of this project is to use SQL to manage structured airport data and answer business-oriented analytical questions.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Design a relational airport management database
- Create structured SQL tables
- Define primary and foreign key relationships
- Insert and manage airport-related data
- Retrieve information using SQL queries
- Analyze flight and passenger information
- Analyze airline and airport operations
- Use joins to combine data from multiple tables
- Use aggregate functions for analysis
- Apply filtering and sorting techniques
- Use subqueries for advanced analysis
- Generate meaningful insights from relational data
- Practice real-world SQL database operations

---

## 🛠️ Technologies Used

- SQL
- MySQL
- MySQL Workbench
- Relational Database Management System
- Git
- GitHub

---

## 🗄️ Database Entities

The database is organized around multiple related entities.

### ✈️ Airports

Stores information about airports.

Typical information includes:

- Airport ID
- Airport name
- Location
- Airport code

### 🛫 Airlines

Stores information about airlines.

Typical information includes:

- Airline ID
- Airline name
- Country

### 🛩️ Flights

Stores flight-related information.

Typical information includes:

- Flight ID
- Airline
- Departure airport
- Arrival airport
- Departure time
- Arrival time

### 👤 Passengers

Stores passenger information.

Typical information includes:

- Passenger ID
- Passenger name
- Contact information
- Passenger details

### 🎫 Tickets

Stores ticket and booking information.

Typical information includes:

- Ticket ID
- Passenger
- Flight
- Seat number
- Ticket price

### 🧳 Luggage

Stores passenger luggage information.

Typical information includes:

- Luggage ID
- Ticket ID
- Weight
- Luggage type

### 👨‍💼 Employees

Stores airport employee information.

Typical information includes:

- Employee ID
- Employee name
- Position
- Airport

### 🏢 Terminals

Stores airport terminal information.

Typical information includes:

- Terminal ID
- Terminal name
- Airport ID

### 🚪 Gates

Stores airport gate information.

Typical information includes:

- Gate ID
- Gate number
- Terminal ID

---

## 🔗 Database Relationships

The database uses relational connections between the main entities.

```text
Airports
   │
   ├────────── Airlines
   │
   ├────────── Terminals
   │                │
   │                └────────── Gates
   │
   └────────── Employees

Airlines
   │
   └────────── Flights
                    │
                    ├────────── Departure Airport
                    │
                    └────────── Arrival Airport
                    │
                    └────────── Tickets
                                  │
                                  ├────────── Passengers
                                  │
                                  └────────── Luggage
```

---

## 📊 SQL Concepts Demonstrated

This project demonstrates practical SQL concepts including:

### Basic SQL

- SELECT
- INSERT
- UPDATE
- DELETE
- WHERE
- ORDER BY
- DISTINCT

### Aggregate Functions

- COUNT()
- SUM()
- AVG()
- MIN()
- MAX()

### Joins

- INNER JOIN
- LEFT JOIN
- RIGHT JOIN

### Advanced SQL

- GROUP BY
- HAVING
- Subqueries
- CASE statements
- Aliases
- Multiple-table joins
- Conditional filtering

---

## 🔍 Analysis Performed

The SQL analysis can be used to answer questions such as:

### Airport Analysis

- How many airports are available?
- What are the airport locations?
- Which airport handles the highest number of flights?
- Which terminals belong to each airport?

### Airline Analysis

- How many airlines operate in the database?
- Which airlines operate the most flights?
- Which airlines have the highest passenger volume?

### Flight Analysis

- How many flights are available?
- Which flights depart from each airport?
- Which flights arrive at each airport?
- What are the departure and arrival schedules?
- Which routes are used most frequently?

### Passenger Analysis

- How many passengers are registered?
- Which passengers have booked flights?
- Which flights have the highest number of passengers?

### Ticket Analysis

- What is the average ticket price?
- What is the highest ticket price?
- What is the total ticket revenue represented in the dataset?
- Which flights generate the highest ticket value?

### Luggage Analysis

- What is the total luggage weight?
- What is the average luggage weight?
- Which passengers have checked luggage?

### Employee Analysis

- How many employees work at each airport?
- What positions are represented?
- Which employees are assigned to specific airports?

---

## 🧠 SQL Query Examples

### Retrieve passengers with their flight information

```sql
SELECT
    p.name AS passenger_name,
    f.flight_id,
    f.departure_airport_id,
    f.arrival_airport_id
FROM Passengers p
INNER JOIN Tickets t
    ON p.passenger_id = t.passenger_id
INNER JOIN Flights f
    ON t.flight_id = f.flight_id;
```

### Retrieve employees with their airport information

```sql
SELECT
    e.name AS employee_name,
    e.position,
    a.name AS airport_name
FROM Employees e
INNER JOIN Airports a
    ON e.airport_id = a.airport_id;
```

### Count flights by airline

```sql
SELECT
    a.name AS airline_name,
    COUNT(f.flight_id) AS total_flights
FROM Airlines a
LEFT JOIN Flights f
    ON a.airline_id = f.airline_id
GROUP BY a.airline_id, a.name;
```

### Calculate average ticket price

```sql
SELECT
    AVG(price) AS average_ticket_price
FROM Tickets;
```

### Find the highest ticket price

```sql
SELECT
    MAX(price) AS highest_ticket_price
FROM Tickets;
```

---

## 📈 Analytical Areas

The project focuses on extracting insights from different areas of airport operations.

| Analysis Area | Example Analysis |
|---|---|
| Airports | Airport count and locations |
| Airlines | Flights operated by each airline |
| Flights | Flight routes and schedules |
| Passengers | Passenger and booking analysis |
| Tickets | Ticket pricing analysis |
| Luggage | Luggage weight analysis |
| Employees | Employee distribution |
| Terminals | Terminal allocation |
| Gates | Gate management |

---

## 📁 Project Structure

```text
SQL---Airport_Management_Analysis/
│
├── SQL/
│   ├── Database Creation/
│   ├── Table Creation/
│   ├── Data Insertion/
│   └── Analysis Queries/
│
├── Data/
│
├── ER Diagram/
│
├── Screenshots/
│
├── README.md
└── .gitignore
```

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/Nazish-08/SQL---Airport_Management_Analysis.git
cd SQL---Airport_Management_Analysis
```

### 2. Open MySQL Workbench

Open MySQL Workbench and connect to your MySQL server.

### 3. Create the Database

Create the database required for the project.

```sql
CREATE DATABASE airport_management;
USE airport_management;
```

### 4. Run the SQL Scripts

Execute the SQL scripts in the appropriate order:

1. Database creation
2. Table creation
3. Data insertion
4. Analysis queries

### 5. Execute Analysis Queries

Run the provided SQL queries to analyze the airport management data.

---

## 📐 Database Design

The project follows a relational database structure where entities are connected through primary keys and foreign keys.

The relationships help maintain data consistency and allow information to be retrieved across multiple tables using SQL joins.

---

## 💡 Key Learning Outcomes

Through this project, I gained practical experience in:

- SQL database design
- Relational database concepts
- MySQL
- Primary keys
- Foreign keys
- Database relationships
- Data insertion
- Data retrieval
- SQL joins
- Aggregate functions
- Grouping and filtering
- Subqueries
- Analytical SQL
- Data interpretation
- MySQL Workbench

---

## 🎓 Skills Demonstrated

- SQL
- MySQL
- Database Management
- Data Analysis
- Relational Database Design
- Query Optimization
- Data Modeling
- Analytical Thinking

---

## 👤 Author

**Nazish**
