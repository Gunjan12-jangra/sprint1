# VCS Design + POC | Mono Repo & Micro Repo

---

## 1. Introduction

Version Control System (VCS) helps teams manage source code, track changes, and work together safely. Git is the most commonly used VCS today.

In real projects, code can be organized in two main ways:

- **Monorepo (Mono Repository)** – all projects/services in one single repository

- **Microrepo (Multi Repository)** – each project/service has its own separate repository

This document explains both Mono Repo and Micro Repo in easy wording, with features, advantages, disadvantages, workflow and best practices.

---

## 2. What is a Monorepo?

A Monorepo is a single repository that contains multiple projects or services.

**Example Structure**

```text
company-monorepo/
├── frontend/
├── backend/
├── payment-service/
├── shared-libs/
└── README.md
```

---

## 3. Monorepo Features

- Single Git repository

- Shared libraries in one place

- One version control history

- Common coding standards

- Easy dependency management

- Centralized CI/CD

---

## 4. Advantages of Monorepo

- Easy code sharing

- Simple dependency management

- One place for all code

- Simpler project versioning

- Easier testing across projects

---

## 5. Challenges / Disadvantages of Monorepo

- Repository size becomes very large

- CI/CD can become slow

- Access control is difficult

- One small change can trigger full pipeline

- Not ideal for very large teams

---

## 6. Monorepo Workflow

- Developer clones single repo

- Creates a feature branch

- Makes changes in required service

- Runs tests locally

- Raises Pull Request (PR)
  
- CI pipeline runs for whole repo
  
- Code review and merge

---  

## 7. Monorepo Best Practices

- Use clear folder structure

- Optimize CI (run tests only for changed modules)

- Maintain strong branching strategy

- Keep shared libraries well documented

---

# 8. What is a Microrepo?

A Microrepo approach means one repository per service or project.

**Example**

- auth-service-repo

- payment-service-repo

- frontend-repo

Each repo is independent.

---

## 9. Microrepo Features

- One service per repository

- Independent versioning

- Separate CI/CD pipelines

- Better access control

- Faster builds

---

## 10. Advantages of Microrepo

- Faster CI/CD

- Easy scaling for large teams

- Independent deployments

- Better security and access control

---

## 11. Challenges / Disadvantages of Microrepo

- Code duplication risk

- Managing many repos is hard

- Dependency version mismatch

- Cross-service changes are complex

---

## 12. Microrepo Workflow

- Developer clones specific repo

- Creates feature branch

- Makes changes

- Runs tests

- Creates PR

- CI runs only for that repo

- Merge and deploy independently

---

## 13. Microrepo Best Practices

- Follow same repo template

- Use shared libraries as packages

- Maintain versioning rules

- Automate repo creation

- Use clear naming convention

---

## 14. Mono Repo vs Micro Repo (Summary)
| Feature |	Monorepo |	Microrepo |
| ----------- | --------------- | ----------------- |
| Repo Count |	One |	Many |
| CI Speed	| Slower	| Faster |
| Code Sharing |	Easy |	Medium |
| Scaling	Medium |	Medium | High |
| Best For |	Small–Medium teams |	Large teams |

---

## 15. Conclusion

- Monorepo is simple and good for small teams.

- Microrepo is best for large teams and microservices architecture

Choose based on team size, project complexity, and deployment needs.

---

## 16. Contact Information

| Contact Type | Details                                                             |
| ------------ | ------------------------------------------------------------------- |
| Email        | [gunjan.jangra.snaatak@mygurukulam.co](mailto:gunjan.jangra.snaatak@mygurukulam.co) |

---

## 17. References
| References Link | Description |
| --------------------- | --------------------------- |
| [Git Documentation](https://git-scm.com/doc) | Git Official Documentation |
| [Monorepo Practices](https://about.google/monorepo/) | Google Monorepo Practices |

---
