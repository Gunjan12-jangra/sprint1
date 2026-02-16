# Frontend - Documentation

---

## Author Information

| Author | Created on | Version | Last updated by | Last edited on | L0 Reviewer | L1 Reviewer | L2 Reviewer |
|--------|------------|---------|-----------------|----------------|-------------|-------------|-------------|
| Gunjan Jangra | 04-02-2026 | v1.0 | Gunjan Jangra | 16-02-2026 | Sharvari Khamkar | Aman Raj | Abhishek Dubey / Ravindra Kumar |

---

## Table of Contents

1. [Introduction](#1-introduction)  
2. [Purpose](#2-purpose)  
3. [Pre-requisites](#3-pre-requisites)  
4. [Dependencies](#4-dependencies)  
5. [Important Ports](#5-important-ports)  
6. [Architecture](#6-architecture)  
7. [Dataflow Diagram](#7-dataflow-diagram)  
8. [Step-by-step installation of Frontend Application](#8-step-by-step-installation-of-frontend-application)  
9. [Monitoring](#9-monitoring)  
10. [Disaster Recovery](#10-disaster-recovery)  
11. [High Availability](#11-high-availability)  
12. [Troubleshooting](#12-troubleshooting)  
13. [FAQs](#13-faqs)  
14. [Contact Information](#14-contact-information)  
15. [References](#15-references)  

---

## 1. Introduction

The Frontend Application is a React-based web application that provides the user interface for interacting with backend microservices such as Employee API, Salary API, and Attendance API.

It is deployed on an EC2 instance inside a private subnet and accessed securely through a Bastion server using NGINX reverse proxy.

The frontend communicates with backend services using REST APIs.

---

## 2. Purpose

The purpose of the Frontend Application is to provide a user-friendly interface for accessing and managing employee data.

It helps users to:

- View employee records  
- Create employee entries  
- View salary information  
- View attendance records  
- Interact with backend APIs  

---

## 3. Pre-requisites

Before deploying the Frontend Application, ensure the following requirements are met.

---

### 3.1 Frontend Server Requirements

| Hardware Specifications | Minimum Recommendation |
|------------------------|------------------------|
| Processor | Dual Core |
| RAM | 4 GB |
| Disk | 20 GB |
| OS | Ubuntu 22.04 LTS |

---

### 3.2 Bastion Server Requirements

| Hardware Specifications | Minimum Recommendation |
|------------------------|------------------------|
| Processor | Dual Core |
| RAM | 2 GB |
| Disk | 10 GB |
| OS | Ubuntu 22.04 LTS |

The Bastion server is used for secure access and reverse proxy.

---

### 3.3 Network & Connectivity Requirements

Required connectivity:

- Bastion Server → Frontend Server (Port 3000)
- Bastion Server → API Server (Ports 8080, 8081, 8082)
- User → Bastion Server (Ports 80 and 443)

Frontend server must remain private.

---

### 3.4 Security Requirements

- Frontend server must be in private subnet  
- Bastion server must be in public subnet  
- Only required ports should be open  
- SSL should be enabled  
- Reverse proxy must be configured  

---

## 4. Dependencies

### Build Time Dependencies

| Name | Version | Description |
|-----|---------|-------------|
| Node.js | 16 | Required to build React application |
| NPM | Latest | Package manager |

---

### Run Time Dependencies

| Name | Version | Description |
|-----|---------|-------------|
| NGINX | Latest | Reverse proxy |
| Serve | Latest | Serves React build |
| Ubuntu | 22.04 | Operating system |

---

## 5. Important Ports

### Inbound Ports

| Port | Description |
|------|-------------|
| 3000 | Frontend Application |
| 80 | HTTP |
| 443 | HTTPS |

---

### Outbound Ports

| Port | Description |
|------|-------------|
| 8080 | Employee API |
| 8081 | Attendance API |
| 8082 | Salary API |

---

## 6. Architecture

The Frontend Application follows microservices architecture.

Components:

- Frontend Server (React App)
- Bastion Server (NGINX Reverse Proxy)
- Backend APIs
- Database Server

Flow:

User → Bastion Server → Frontend Server → Backend APIs → Database

---

## 7. Dataflow Diagram

Data flow steps:

1. User opens frontend URL in browser  
2. Request goes to Bastion server  
3. NGINX forwards request to frontend server  
4. React frontend loads  
5. Frontend calls backend APIs  
6. Backend sends response  
7. Frontend displays data  

---

## 8. Step-by-step installation of Frontend Application

### Step 1: Connect to Frontend Server

```bash
ssh -i key.pem ubuntu@<frontend_private_ip>
```

### Step 2: Install Node.js

```bash
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt install nodejs -y
```

**Verify:**

```bash
node -v
npm -v
```

### Step 3: Clone Repository

```bash
git clone https://github.com/OT-MICROSERVICES/frontend.git
cd frontend
```

### Step 4: Install and Build

```bash
npm install
npm run build
```

### Step 5: Create Service

```bash
sudo nano /etc/systemd/system/frontend.service
```

```bash
[Unit]
Description=Frontend React App
After=network.target

[Service]
User=ubuntu
WorkingDirectory=/home/ubuntu/frontend
ExecStart=/usr/bin/npx serve -s build -l 3000
Restart=always

[Install]
WantedBy=multi-user.target
```

**Start service:**

```bash
sudo systemctl daemon-reload
sudo systemctl start frontend
sudo systemctl enable frontend
```

### Step 6: Configure NGINX on Bastion Server

**Install nginx:**

```bash
sudo apt install nginx -y
```

**Reload nginx:**

```bash
sudo systemctl reload nginx
```

---

## 9. Monitoring

### 9.1 Metrics

| Parameter |	Description |
| ------------------- | -------------------------- |
| CPU Usage	| CPU consumption |
| Memory Usage	| RAM usage |
| Availability	| Uptime |
| Response Time	| Application response |

---

### 9.2 Health Check

**Check frontend service:**

```bash
sudo systemctl status frontend
```

**Check nginx:**

```bash
sudo systemctl status nginx
```

---

## 10. Disaster Recovery

Recovery steps:

- Restart frontend service

- Restart nginx

- Redeploy application

- Restore backup if needed

---


## 11. High Availability

To ensure high availability:

- Deploy multiple frontend instances

- Use load balancer

- Use auto scaling

---

## 12. Troubleshooting

| Issue |	Solution |
|---------------------- |----------------------------- |
| Frontend not loading | Check frontend service |
| 502 error	| Check frontend server |
| NGINX error	| Check nginx config |
| API not working |	Check backend API |

---

## 13. FAQs

**Q: What is frontend application?**  
Frontend provides user interface.

**Q: Where is frontend hosted?**  
On private EC2 server.

**Q: How users access frontend?**  
Through Bastion server using nginx.

---

## 14. Contact Information

| Contact Type | Details                                                             |
| ------------ | ------------------------------------------------------------------- |
| Email        | [gunjan.jangra.snaatak@mygurukulam.co](mailto:gunjan.jangra.snaatak@mygurukulam.co) |

---

## 15. References

| Reference | Description |
|-----------|-------------|
| [React Documentation](https://react.dev) | Official React Documentation |
| [Nginx Documentation](https://nginx.org/en/docs) | Official NGINX Documentation |
| [Node.js Documentation](https://nodejs.org/docs) | Official Node.js Documentation |

---
