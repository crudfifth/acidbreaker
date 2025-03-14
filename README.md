# ACID-Breaker: Database Resilience & Security Testing Tool

ACID-Breaker is a tool designed for **database resilience testing, failure simulation, and security assessments**.  
It provides a suite of tests to evaluate **ACID compliance**, **fault tolerance**, and **protection against security threats** such as SQL injection and privilege escalation.

## Features

### 1️⃣ Transaction Failure Simulation
- **Forced process termination**: Kill the database process mid-transaction to test rollback behavior.
- **Journal log corruption**: Delete `wal` or `redo log` files to observe data recovery.
- **Disk full & I/O error simulation**: Fill up disk space and observe database behavior.

### 2️⃣ Consistency Testing
- **Foreign key constraint bypass**: Disable FK constraints and insert inconsistent data.
- **Data type corruption**: Insert malformed or NULL values into required fields.
- **Dirty read simulation**: Modify records during an ongoing `SELECT` query.

### 3️⃣ Isolation Testing
- **Race condition & deadlock tests**: Execute concurrent transactions updating the same records.
- **Phantom read detection**: Modify data mid-transaction to observe read inconsistencies.

### 4️⃣ Durability Disruption
- **Commit without `fsync`**: Bypass disk writes and observe data loss upon crash.
- **Simulated power failure**: Force system shutdown or kill the DB process unexpectedly.
- **Storage failure emulation**: Remount the DB directory as read-only.

### 5️⃣ Security & Attack Simulations
- **SQL Injection resilience test**: Execute automated SQL injection patterns.
- **Brute-force attack simulation**: Test login security with dictionary-based attacks.
- **Privilege escalation assessment**: Attempt unauthorized `GRANT` permissions.
- **Query log sniffing**: Capture SQL queries over the network.

## Use Cases
- **Database fault tolerance testing**
- **Security auditing for SQL injection & privilege escalation**
- **Durability & consistency validation under extreme conditions**
- **Transaction rollback integrity checks**

## Supported Databases
- **MySQL**
- **PostgreSQL**
- **SQLite**
- **MongoDB** (limited support)

## Technology Stack
- **Languages**: Python / Rust / Bash
- **Testing Frameworks**: `pytest`, `locust`
- **Containerization**: Docker / docker-compose
- **Network Monitoring**: `tcpdump`, `wireshark`

## Getting Started

### Prerequisites
Ensure you have the following installed:

- Docker
- Python 3.8+
- PostgreSQL or MySQL (running locally or in a container)

### Installation
```bash
git clone https://github.com/yourusername/ACID-Breaker.git
cd ACID-Breaker
pip install -r requirements.txt
```
Running Tests
```
python run_tests.py --target-db postgresql
```
