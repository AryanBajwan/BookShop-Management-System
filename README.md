# 📚 BookShop Management System

This project contains the database schema for a **BookShop Management System** built using **MySQL**.  
The database handles books, suppliers, employees, members, purchases, and sales records.

---

## 🗄️ Database Information
- **Database Name**: `Management`

---

## 📑 Tables and Schema

### 1. `Books`
| Column | Type | Constraints |
|--------|------|-------------|
| id | INT | Primary Key |
| name | VARCHAR(255) |  |
| auth | VARCHAR(255) |  |
| price | INT |  |
| qty | INT |  |

---

### 2. `Suppliers`
| Column | Type | Constraints |
|--------|------|-------------|
| id | INT | Primary Key |
| name | VARCHAR(255) |  |
| phn | BIGINT |  |
| addr_line1 | VARCHAR(255) |  |
| addr_line2 | VARCHAR(255) |  |
| addr_city | VARCHAR(100) |  |
| addr_state | VARCHAR(100) |  |

---

### 3. `Purchases`
| Column | Type | Constraints |
|--------|------|-------------|
| ord_id | INT | Primary Key |
| book_id | INT | Foreign Key → Books(id) |
| sup_id | INT | Foreign Key → Suppliers(id) |
| qty | INT |  |
| dt_ordered | DATE |  |
| eta | INT |  |
| received | CHAR(1) | CHECK (`T` or `C` or `F`) DEFAULT 'F' |
| inv | INT |  |

---

### 4. `Employees`
| Column | Type | Constraints |
|--------|------|-------------|
| id | INT | Primary Key |
| name | VARCHAR(255) |  |
| addr_line1 | VARCHAR(255) |  |
| addr_line2 | VARCHAR(255) |  |
| addr_city | VARCHAR(100) |  |
| addr_state | VARCHAR(100) |  |
| phn | BIGINT |  |
| date_of_joining | DATE |  |
| salary | BIGINT |  |
| mgr_status | CHAR(1) | CHECK (`T` or `F`) DEFAULT 'F' |

---

### 5. `Members`
| Column | Type | Constraints |
|--------|------|-------------|
| id | INT | Primary Key |
| name | VARCHAR(255) |  |
| addr_line1 | VARCHAR(255) |  |
| addr_line2 | VARCHAR(255) |  |
| addr_city | VARCHAR(100) |  |
| addr_state | VARCHAR(100) |  |
| phn | BIGINT |  |
| beg_date | DATE |  |
| end_date | DATE |  |
| valid | VARCHAR(10) |  |

---

### 6. `Sales`
| Column | Type | Constraints |
|--------|------|-------------|
| invoice_id | INT | Primary Key |
| member_id | INT | Foreign Key → Members(id) |
| book_id | INT | Foreign Key → Books(id) |
| qty | INT |  |
| amount | INT |  |
| date_s | DATE |  |

---

## 🚀 Usage
1. Create the database:
   ```sql
   CREATE DATABASE Management;
   USE Management;
