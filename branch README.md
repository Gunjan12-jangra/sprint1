# Branch Access Policies - Documentation

---

## Authors

| Author        | Created     | Version | Last updated by | Last Edited On | L0 Reviewer | L1 Reviewer | L2 Reviewer |
| ------------- | ----------- | ------- | --------------- | -------------- | ----------- | ----------- | ----------- |
| Gunjan Jangra | 5-02-2026   | 1.0     | Gunjan Jangra   | 5-02-2026      |             |             |             |

---

## Table of Contents

1. [Introduction](#1-introduction)  
2. [Why Branch Access Policies are Required](#2-why-branch-access-policies-are-required)  
3. [Branch Protection Rules](#3-branch-protection-rules)  
4. [Branch Access Levels](#4-branch-access-levels)  
5. [Protected Branches](#5-protected-branches)  
6. [Branch Strategy and Workflow](#6-branch-strategy-and-workflow)  
7. [Best Practices](#7-best-practices)  
8. [Contact Information](#8-contact-information)  
9. [References](#9-references)  

---

## 1. Introduction

This document guides branch rules, protection, workflows, and best practices for safe and reviewed code.

Branch access policies define who can perform actions on repository branches and how code changes should be merged. They ensure safe and structured development.

---

## 2. Why Branch Access Policies are Required

Branch access policies are important to:

- Prevent direct changes to critical branches like main or production.  
- Enforce code review to catch errors before merging.  
- Maintain code consistency cross the project.  
- Assign clear ownership and responsibilities to developers.  
- Support CI/CD pipelines, ensuring automated checks pass before merge.  

---

## 3. Branch Protection Rules

Branch protection rules are applied to safeguard branches. Common rules include:

- **Pull Request Required:** Code must be merged via a Pull Request; direct commits are blocked.  
- **Required Reviewers:** At least one reviewer must approve the changes before merging.  
- **Status Checks Required:** Automated tests, builds, and security scans must pass.  
- **No Force Push:** Prevents rewriting commit history to ensure traceability.  
- **Restrict Deletion:** Critical branches cannot be deleted accidentally.  

---

## 4. Branch Access Levels

| Access Level | Description |
| ------------ | ----------- |
| Read         | Can view the repository and branches but cannot modify code. |
| Write        | Can push to non-protected branches and create Pull Requests. |
| Admin        | Full control, including changing branch policies and deleting branches. |

Access should be granted based on the developer's role and responsibility.

---

## 5. Protected Branches

 Common protected branches:
 
- `main` / `master`  
- `develop`  
- `release/*`  
- `production`  

**Rules for protected branches:**

- Direct push is not allowed.  
- Pull Requests and mandatory code review are required.  
- CI/CD automated checks must pass before merging.  
- Merge permissions are limited to authorized users only.  

---

## 6. Branch Strategy and Workflow

A common workflow using branch policies:
1. Developer creates a feature branch.
2. Code is pushed to the feature branch.
3. Pull Request raised to develop/main.
4. Reviewers approve PR.
5. CI/CD checks run.
6. Code merged after approval.

---

## 7. Best Practices

- Protect main and production branches.  
- Use pull requests for all changes.  
- Enable CI/CD checks.  
- Give minimum required access.  
- Regularly review permissions.

---

## 8. Contact Information

| Contact Type | Details |
| ------------ | ------- |
| Email        | [gunjan.jangra.snaatak@mygurukulam.co](mailto:gunjan.jangra.snaatak@mygurukulam.co) |

---

## 9. References

| Reference Link | Description |
| --------------- | ----------- |
| [GitHub Branch Protection](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches) | GitHub official documentation |
| [GitLab Protected Branches](https://docs.gitlab.com/ee/user/project/protected_branches/) | GitLab guide for protected branches |
