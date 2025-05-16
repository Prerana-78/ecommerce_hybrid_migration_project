# 🛠️ Hybrid Database Migration Project (MySQL → MongoDB)

This project demonstrates a real-world **heterogeneous database migration** from **MySQL** to **MongoDB**, using Python for ETL scripts, validation, and Docker for monitoring via Prometheus + Grafana.

---

## 📌 Project Overview

- **Goal**: Migrate legacy application data (users and orders) from MySQL to MongoDB with validation and monitoring.
- **Type**: Heterogeneous migration (Relational → NoSQL)
- **Scope**: Local development environment (Windows)

---

## 🔧 Technologies Used

| Layer          | Tools / Tech                                      |
|----------------|---------------------------------------------------|
| Source DB      | MySQL 8.0 (via MySQL Workbench)                   |
| Target DB      | MongoDB (via Compass + pymongo)                   |
| ETL Scripts    | Python (PyMySQL + PyMongo)                        |
| Validation     | Python row count checker                          |
| Monitoring     | Docker, Prometheus, Grafana, MongoDB Exporter     |
| Interface Tool | MongoDB Compass, MySQL Workbench                  |

---

## 📁 Project Structure

```
ecommerce_hybrid_migration_project/
├── etl_scripts/
│   ├── migrate_users.py
│   └── migrate_orders.py
├── validation/
│   └── validate_row_counts.py
├── monitoring/
│   ├── docker-compose.yml
│   └── prometheus.yml
└── README.md
```

---

## 🚀 How to Run

### 1. Setup MySQL
- Create a database: `legacy_app_db`
- Add `users` and `orders` tables using SQL scripts
- Insert sample data

### 2. Run Migration Scripts
```bash
python etl_scripts/migrate_users.py
python etl_scripts/migrate_orders.py
```

### 3. Validate Data
```bash
python validation/validate_row_counts.py
```

### 4. Start Monitoring Stack
```bash
cd monitoring
docker-compose up -d
```

### 5. Add MongoDB Exporter (separately)
```bash
docker run -d -p 9216:9216 -e MONGODB_URI="mongodb://localhost:27017" bitnami/mongodb-exporter:latest
```

---

## 📊 Monitoring in Grafana

- Visit: `http://localhost:3000`
- Login: `admin` / `admin`
- Import Dashboard ID: **11915** for MongoDB metrics

---

## ✅ Output

- ✅ Successful MySQL → MongoDB migration
- ✅ Row count validation between DBs
- ✅ Prometheus + Grafana running in Docker
- ✅ MongoDB Exporter providing live metrics

---

## 👤 Author

**Prerana-78**  
May 16, 2025  
GitHub: [Prerana-78](https://github.com/Prerana-78)

---
