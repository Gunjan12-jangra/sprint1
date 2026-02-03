# Microrepo

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
5. [Challenges / Disadvantages of Microrepo](#5-challenges--disadvantages-of-microrepo)
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

- One service per repository

- Independent versioning

- Separate CI/CD pipelines

- Better access control

- Faster builds

---

## 4. Advantages of Microrepo

- Faster CI/CD

- Easy scaling for large teams

- Independent deployments

- Better security and access control

---

## 5. Challenges / Disadvantages of Microrepo

- Code duplication risk

- Managing many repos is hard

- Dependency version mismatch

- Cross-service changes are complex

---

## 6. Microrepo Workflow

- Developer clones a specific repository
  
- Creates a feature branch
  
- Makes code changes
  
- Runs tests
    
- Creates a Pull Request (PR)
   
- CI pipeline runs only for that repository
   
- Service is merged and deployed independently  

---

## 7. Microrepo Best Practices

- Follow the same repository template

- Use shared libraries as packages

- Maintain versioning rules

- Automate repo creation

- Use clear naming conventions

---


## 8. Conclusion

Microrepo is best for large teams and microservices projects. It allows teams to work and deploy services independently.

---

## 9. Contact Information

| Contact Type | Details                                                             |
| ------------ | ------------------------------------------------------------------- |
| Email        | [gunjan.jangra.snaatak@mygurukulam.co](mailto:gunjan.jangra.snaatak@mygurukulam.co) |

---

## 10. References
| References Link | Description |
| --------------------- | --------------------------- |
| [Git Documentation](https://git-scm.com/doc) | Git Official Documentation |
| [Microservices](https://microservices.io/) | Microservices Architecture |

---
