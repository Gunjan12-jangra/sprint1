# Employee API — Proof of Concept (POC)

---

## Author Information

| Author           | Created     | Version | Last updated by  | Last Edited On | L0 Reviewer | L1 Reviewer | L2 Reviewer |
| ---------------- |---------------- | ------- | ---------------- | -------------- | ----------- | ----------- | ----------- |
| Gunjan Jangra  |  15-02-2026     |  1.0     | Gunjan Jangra |  15-02-2026     |   Sharvari Khamkar             |     Aman Raj        |  Abhishek Dubey/Ravindra Kumar             |

---

## Table of Contents

1. [Purpose](#1-purpose)  
2. [Prerequisites](#2-prerequisites)  
3. [Deployment Steps](#3-deployment-steps)  
4. [Troubleshooting](#4-troubleshooting)  
5. [Final Result](#5-final-result)  
6. [Final Deployment Summary](#6-final-deployment-summary)
7. [Conclusion](#7-conclusion)  
8. [Contact Information](#8-contact-information)  
9. [References](#9-references)  

---

## 1. Purpose

The Employee API is a **Golang microservice** for managing employee data.  

This POC demonstrates:

- Deploying Employee API in a server
- Connecting with ScyllaDB (and optional Redis)
- Running REST APIs
- Running API as a systemd service
- Using Swagger UI for API testing

---

## 2. Prerequisites

| Requirement        | Version / Notes       |
|-------------------|---------------------|
| Ubuntu            | 22.04               |
| Go                | As defined in go.mod |
| Make              | Latest              |
| ScyllaDB          | Latest              |
| Redis (optional)  | 7+                  |
| Open Port         | 8080                |

---

## 3. Deployment Steps

### Step 1: Create and Access EC2 Instance

Launch a private subnet EC2 instance for Employee API.

**Required ports:**

| Ports | Description |
|---------------- | -------------------- |
| 8080 | HTTP API access |
| 9042  | ScyllaDB access |

---

### Step 2: Install Build Dependencies

```bash 
sudo apt update
sudo apt install golang make -y
```

---

### Step 3: Employee API config.yml Setup
#### api config.yml

```bash
scylladb:
  host: ["10.0.1.25:9042"]
  username: scylla
  password: 12345
  keyspace: employee

redis:
  enabled: false
  host: 10.0.1.25:6379
  password: 12345
  database: 0
```

---

### Step 4: Employee API Database Migration File Setup

**Install migrate:**

```bash
migrate install
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.17.0/migrate.linux-amd64.tar.gz | tar xvz
sudo mv migrate /usr/local/bin/migrate
```

**Create migrate.json:**

```bash
migrate.json root
{
  "database": "cassandra://10.0.1.25:9042/employee?username=scylla&password=12345"
}
```

**Run migrations:**

```bash
make run-migrations
```

---

### Step 5: Background Process Run Command 

```bash
nohup go run main.go > api.log 2>&1 &
```

---

### Step 6: Creating Services for the Employee API

```bash
vim /etc/systemd/system/employee-api.service
```

#### service file for employee

```bash
[Unit]
Description=Employee API
After=network.target

[Service]
Type=simple
User=ubuntu
WorkingDirectory=/home/ubuntu/employee/employee-api
ExecStart=nohup go run /home/ubuntu/employee/employee-api/main.go > api.log 2>&1 &

Restart=always
RestartSec=3

[Install]
WantedBy=multi-user.target
```


**Enable and start service:**

```bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl enable employee-api.service 
sudo systemctl start employee-api.service 
sudo systemctl status employee-api.service
```

---

### Step 7: Access API

- Base URL: http://<server-ip>:8080

- Swagger UI: http://<server-ip>:8080/swagger/index.html

**Example CURL Commands:**

**Create Employee:**

```bash
curl -X POST http://127.0.0.1:8080/employees \
-H "Content-Type: application/json" \
-d '{"id":"1","name":"John Doe","email":"john@example.com","department":"Engineering"}'
```

**Get Employee by ID:**

```bash
curl http://127.0.0.1:8080/employees/1
```

**Get All Employees:**

```bash
curl http://127.0.0.1:8080/employees
```

---

## 4. Troubleshooting
| Issue	Check | Fix |
| ----------------------------- | --------------------------------------- |
| Employee API not running |	sudo systemctl status employee-api |
| Database connection failure	| Verify ScyllaDB is running and reachable |
| Port conflicts |	Ensure port 8080 is free |

---

## 5. Final Result

- Employee API running as systemd service

- REST endpoints functional via CURL or frontend integration

- Database migrations applied successfully

---

## 6. Final Deployment Summary

- Go backend deployed in production mode

- ScyllaDB integrated as primary database

- systemd service ensures auto-restart and availability

- Swagger UI ready for API testing

---

## 7. Conclusion

This POC shows that the Employee API can be fully set up and run as a backend service.
The API is ready to work with other systems, and all endpoints have been tested using CURL and Swagger. 
It runs as a systemd service, so it can restart automatically if needed, and the setup is ready for production use.

---

## 8. Contact Information

| Contact Type | Details                                                             |
| ------------ | ------------------------------------------------------------------- |
| Email        | [gunjan.jangra.snaatak@mygurukulam.co](mailto:gunjan.jangra.snaatak@mygurukulam.co) |

---

## 9. References

| Reference                   | Description                               |
|------------------------------|------------------------------------------|
| [Employee API Repository](https://github.com/your-repo/employee-api) | The source code repository for this microservice |
| [ScyllaDB Documentation](https://docs.scylladb.com/) | Guides for setting up, configuring, and using ScyllaDB |
| [Go Documentation](https://golang.org/doc/) | Documentation for the Go programming language and dependency management |

---
