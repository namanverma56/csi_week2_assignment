# ShopEase Retail Sales Data Analysis

An end-to-end relational database implementation and analytics portfolio project based on a simulated e-commerce application platform named **ShopEase**. This project demonstrates the step-by-step lifecycle of managing transactional retail data—ranging from core schema creation and data constraints to advanced pipeline filtering, performance optimization, structural tables joins, and robust ACID-compliant transactional programming blocks.

## 🛠️ Tech Stack & Environment
* **Database Engine:** SQLite
* **Interface Platform:** SQLite Online IDE
* **Core Languages:** SQL (DDL, DML, DQL)

---

## 📊 Database Architecture (Schema)

The project leverages a normalized relational database structure consisting of four interconnected core tables. 

[Image of relational database entity relationship diagram showing connections between customers, products, orders, and order items tables]

### 1. Customers Table
Tracks essential buyer profiles, including identity information, geographic location, signup timelines, and membership tier attributes.
* `customer_id` (INT, Primary Key)
* Constraints: `email` is enforced as `UNIQUE NOT NULL` to prevent duplication.

### 2. Products Table
Manages the store catalog, department categorization, item brand indexing, pricing metrics, and real-time inventory management tracking.
* `product_id` (INT, Primary Key)
* Constraints: Enforces financial safety boundaries via `CHECK (unit_price > 0)` and warehouse verification via `CHECK (stock_qty >= 0)`.

### 3. Orders Table
Serves as the master transactional log tracking individual customer purchases, timestamps, operational logistics processing statuses, and financial totals.
* `order_id` (INT, Primary Key)
* Constraints: Relational enforcement via `FOREIGN KEY (customer_id)`. Restricts operational phases via `CHECK (status IN ('Pending','Shipped','Delivered','Cancelled'))`.

### 4. Order Items Table
The line-item bridge matching individual product quantities, applied promotional discounts, and exact unit pricing directly to parent orders.
* `item_id` (INT, Primary Key)
* Constraints: Multi-table connections via foreign keys referencing both `orders` and `products`.

---

## 📈 Core Project Implementations

The project code is structurally separated into modular analytical layers across five major milestones:

### 🔹 Section A: Data Definition & Integrity Guardrails
* Initialized database environments using strict column constraints (`NOT NULL`, `UNIQUE`, `DEFAULT`).
* Verified structural database safety guards by explicitly testing constraint failures against invalid operations (e.g., preventing negative inventory or impossible negative prices).

### 🔹 Section B: Filtering & Performance Optimization
* Executed conditional data extraction utilizing advanced `WHERE` operators, `BETWEEN` date arrays, and logical multi-conditional blocks.
* Created explicit database indexing (`CREATE
