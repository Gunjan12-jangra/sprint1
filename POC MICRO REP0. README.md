# VCS Design + POC | Mono Repo & Micro Repo

---

# 1. Introduction

Version Control System (VCS) helps teams manage source code, track changes, and work together safely. Git is the most commonly used VCS today.

In real projects, code can be organized in two main ways:

- **Monorepo (Mono Repository)** – all projects/services in one single repository

- **Microrepo (Multi Repository)** – each project/service has its own separate repository

This document explains both Mono Repo and Micro Repo in easy wording, with features, advantages, disadvantages, workflow and best practices.

---

## 2. What is a Microrepo?

A Microrepo approach means one repository per service or project.

**Example**

- auth-service-repo

- payment-service-repo

- frontend-repo

Each repo is independent.

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

- Developer clones specific repo

- Creates feature branch

- Makes changes

- Runs tests

- Creates PR

- CI runs only for that repo

- Merge and deploy independently

---

## 7. Microrepo Best Practices

- Follow same repo template

- Use shared libraries as packages

- Maintain versioning rules

- Automate repo creation

- Use clear naming convention

---


## 8. Conclusion

- Monorepo is simple and good for small teams.

- Microrepo is best for large teams and microservices architecture

Choose based on team size, project complexity, and deployment needs.

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
| [Monorepo Practices](https://about.google/monorepo/) | Google Monorepo Practices |

---
