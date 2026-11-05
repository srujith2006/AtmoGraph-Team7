# AtmoGraph-Team7
# AtmoGraph – Backend Development

## 1. Overview

This branch contains the backend development work for **AtmoGraph**, a graph-based global supply-chain analysis project.

The backend is responsible for establishing the Neo4j database, designing the supply-chain graph structure, managing data ingestion, and providing the foundation for graph-based analysis.

**Branch:** `Srujith-Backend`  
**Current Phase:** Week 1 – Graph Foundations  
**Status:** Week 1 foundation setup completed; automated data ingestion is pending.

---

## 2. Technology Stack

| Technology | Purpose |
|---|---|
| Python | Backend development |
| Neo4j AuraDB | Graph database |
| Cypher | Graph queries and database operations |
| Neo4j Python Driver | Python–Neo4j connectivity |
| python-dotenv | Environment variable management |
| Git & GitHub | Version control |

---

## 3. Week 1 – Graph Foundations

### 3.1 Database Setup

- Created a Neo4j AuraDB Free instance named `AtmoGraph`.
- Configured the cloud database connection.
- Verified successful database connectivity.

### 3.2 Graph Data Model

Designed a mock global supply-chain network using five node types:

| Node Label | Example Entity | ID |
|---|---|---|
| Supplier | Chip Supplier | S001 |
| Factory | India Factory | F001 |
| Port | Chennai Port | P001 |
| Warehouse | Singapore Warehouse | W001 |
| Retailer | US Retailer | R001 |

### 3.3 Relationships

Implemented the following directed relationships:

1. `SUPPLIES_TO` – Supplier → Factory
2. `SHIPS_TO` – Factory → Port
3. `TRANSPORTS_TO` – Port → Warehouse
4. `DISTRIBUTES_TO` – Warehouse → Retailer

Relationship properties include `lead_time_days` and, where applicable, `capacity`.

### 3.4 Database Constraints

Created unique constraints to prevent duplicate entity IDs for all five node labels:

- Supplier
- Factory
- Port
- Warehouse
- Retailer

### 3.5 Python–Neo4j Connectivity

- Installed the Neo4j Python Driver and python-dotenv.
- Configured database credentials using a root-level `.env` file.
- Implemented `backend/database/connection.py`.
- Successfully connected Python to Neo4j AuraDB.
- Verified the connection by retrieving the total node count from the database.

**Current database verification:** 5 nodes and 4 relationships.

---

## 4. Current Project Structure

```text
AtmoGraph-Team7/
│
├── backend/
│   ├── database/
│   │   └── connection.py
│   │
│   └── requirements.txt
│
├── .env.example
├── .gitignore
└── README.md
```

The actual `.env` file is stored locally and is intentionally excluded from version control.

---

## 5. Backend Setup Instructions

### Prerequisites

- Python installed
- A Neo4j AuraDB instance
- Git installed

### Step 1: Clone the repository

```bash
git clone <repository-url>
cd AtmoGraph-Team7
```

### Step 2: Install dependencies

```bash
pip install -r backend/requirements.txt
```

### Step 3: Configure environment variables

Create a `.env` file in the repository root:

```env
NEO4J_URI=your_neo4j_uri
NEO4J_USERNAME=neo4j
NEO4J_PASSWORD=your_neo4j_password
```

Replace the placeholder values with your own Neo4j AuraDB credentials.

**Important:** Never commit or share the `.env` file.

### Step 4: Test database connectivity

From the repository root, execute:

```bash
python backend/database/connection.py
```

A successful connection should display a confirmation message and the total number of nodes in the database.

---

## 6. Week 1 Progress Tracker

| Deliverable | Status |
|---|---|
| Neo4j AuraDB setup | Completed |
| Supply-chain graph schema design | Completed |
| Node creation | Completed |
| Relationship creation | Completed |
| Unique constraints | Completed |
| Python–Neo4j connectivity | Completed |
| Automated data ingestion scripts | Pending |
| Ingestion validation with mock data | Pending |

---

## 7. Upcoming Backend Tasks

The next backend activities will focus on:

- Developing automated data ingestion scripts.
- Loading mock supply-chain data into Neo4j.
- Handling node and relationship creation programmatically.
- Validating the ingested graph data.
- Preparing the database foundation for subsequent project phases.

---

## 8. Development Notes

- This README tracks backend-specific development progress on the `Srujith-Backend` branch.
- The main project README is maintained separately on the main branch.
- Database credentials must always remain in local environment variables.
- This document will be updated whenever new backend deliverables are completed.

---

**AtmoGraph – Backend Development**  
*Week 1: Graph Foundations*