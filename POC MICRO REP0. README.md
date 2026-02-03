# Microrepo - Documentation

---

## Authors

| Author           | Created    | Version | Last updated by  | Last Edited On | L0 Reviewer | L1 Reviewer | L2 Reviewer |
| ---------------- |---------------- | ------- | ---------------- | -------------- | ----------- | ----------- | ----------- |
| Gunjan Jangra  |  3-02-2026    |  1.0     | Gunjan Jangra |  3-02-2026     |       |          |             |             

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [What is a Microrepo?](#2-what-is-a-microrepo)
3. [Microrepo Features](#3-microrepo-features)
4. [Advantages of Microrepo](#4-advantages-of-microrepo)
5. [Disadvantages of Microrepo](#5-disadvantages-of-microrepo)
6. [Microrepo Workflow](#6-microrepo-workflow)
7. [Microrepo Best Practices](#7-microrepo-best-practices)
8. [Conclusion](#8-conclusion)
9. [Contact Information](#9-contact-information)
10. [References](#10-references)

---

## 1. Introduction

This document explains the Microrepo approach in simple terms, covering its features, advantages, disadvantages, workflow, and best practices.

A Version Control System (VCS) helps teams manage source code, track changes, and collaborate safely. In a Microrepo setup, Git is commonly used to manage each service or project in its own separate repository.

---

## 2. What is a Microrepo?

A Microrepo approach is a way of managing code where each service or project has its own separate Git repository.  
Instead of keeping all code in one place, every service is stored and managed independently.

**Example**

- auth-service-repo

- payment-service-repo

- frontend-repo

Each repository is independent.

---

## 3. Microrepo Features

| Feature |	Description |
| ---------------------- | -------------------------------- |
| One service per repository |	Each repository contains only a single service |
| Separate CI/CD pipelines |	Each service has its own build and deployment pipeline |
| Better access control	| Access can be controlled at the repository level |
| Faster builds |	Smaller repositories result in faster build times |
| Easier debugging | Issues are isolated to a single service/repository |

---

## 4. Advantages of Microrepo

- Faster CI/CD

- Easy scaling for large teams

- Independent deployments

- Better security and access control

---

## 5. Disadvantages of Microrepo

- Code duplication risk

- Managing many repos is hard

- Dependency version mismatch

- Cross-service changes are complex

---

## 6. Microrepo Workflow

**1. Developer clones a specific repository** – The developer downloads only the required service repository.

**2. Creates a feature branch** – A new branch is created to work safely on changes.

**3. Makes code changes** – The developer updates or adds code for that service.

**4. Runs tests** – Tests are run to check if the code is working properly.

**5. Creates a Pull Request (PR)** – The changes are sent for review and approval.

**6. CI pipeline runs only for that repository** – Automated build and tests run only for that service.

**7. Service is merged and deployed independently** – After approval, the service is deployed without affecting other services.


<img width="1354" height="567" alt="image" src="https://github.com/user-attachments/assets/d98d4dd4-fccf-424a-9ed2-49a0c33091f7" />
 

---

## 7. Microrepo Best Practices

- Follow the same repository template

- Use shared libraries as packages

- Maintain versioning rules

- Automate repo creation

- Use clear naming conventions

---


## 8. Conclusion

Microrepo is best suited for large teams and microservices-based projects. It enables teams to develop, test, and deploy services independently.

---

## 9. Contact Information

| Contact Type | Details                                                             |
| ------------ | ------------------------------------------------------------------- |
| Email        | [gunjan.jangra.snaatak@mygurukulam.co](mailto:gunjan.jangra.snaatak@mygurukulam.co) |

---

## 10. References
| References Link | Description |
| --------------------- | --------------------------- |
| [Monorepo and Multi‑Repo](https://medium.com/@kazimozkabadayi/choosing-between-monorepo-and-multi-repo-architectures-in-software-development-5b9357334ed2) | When and why to choose Multi‑Repo over Monorepo |
| [Monorepo vs Microrepo](https://dev.to/mrizwanashiq/monorepo-vs-microrepo-m58)| Monorepo and microrepo approaches |

---
