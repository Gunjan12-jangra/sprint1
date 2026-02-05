# Commit Hooks – Detailed Documentation

---

## Authors

| Author           | Created     | Version | Last updated by  | Last Edited On | L0 Reviewer | L1 Reviewer | L2 Reviewer |
| ---------------- |---------------- | ------- | ---------------- | -------------- | ----------- | ----------- | ----------- |
| Gunjan Jangra  |  5-02-2026     |  1.0     | Gunjan Jangra |  5-02-2026     |               |             |             |

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Purpose of Commit Hooks](#2-purpose-of-commit-hooks)
3. [Types of Commit Hooks](#3-types-of-commit-hooks)
   - [pre-commit](#31-pre-commit)
   - [prepare-commit-msg](#32-prepare-commit-msg)
   - [commit-msg](#33-commit-msg)
   - [post-commit](#34-post-commit)
4. [Best Practices for Commit Hooks](#4-best-practices-for-commit-hooks)
5. [FAQ (Frequently Asked Questions)](#5-faq-frequently-asked-questions)
6. [Contact Information](#6-contact-information)
7. [References](#7-references)

---

## 1. Introduction

Git Hooks are scripts that Git automatically runs when certain actions happen in a Git repository, such as committing code, pushing code, or merging branches.

A Commit Hook is a type of Git Hook that runs during the commit process. It helps teams enforce rules, maintain code quality, and prevent mistakes before code is saved in the repository.

---

## 2. Purpose of Commit Hooks

The main purpose of commit hooks is to automate checks and enforce standards before a commit is finalized.

Commit hooks help in:

- Preventing bad or broken code from entering the repository

- Enforcing coding standards (formatting, naming, lint rules)

- Validating commit messages

- Running tests automatically

- Improving overall code quality

---

## 3. Types of Commit Hooks

Commit hooks are part of client-side Git hooks and mainly include:

### 3.1 pre-commit

- Runs before the commit is created

- Used to check code quality, formatting, linting, or run tests

- If this hook fails, the commit is stopped

**Example use cases:**

- Run ESLint or Prettier

- Check for syntax errors

---

### 3.2 prepare-commit-msg

- Runs before the commit message editor opens

- Used to modify or auto-generate commit messages

**Example use cases:**

- Add ticket IDs automatically

- Apply commit message templates

---

### 3.3 commit-msg

- Runs after the commit message is written

- Used to validate commit message format

**Example use cases:**

- Enforce conventional commits (feat, fix, chore)

- Prevent empty or vague commit messages

---

### 3.4 post-commit

- Runs after the commit is completed

- Does not affect the commit result

**Example use cases:**

- Show notifications

- Trigger local scripts or logs

---

## 4. Best Practices for Commit Hooks

- Keep hooks fast and lightweight

- Use tools like Husky for easy management

- Share hook logic via scripts (hooks are not versioned by default)

- Combine hooks with CI pipelines for stronger enforcement

---

## 5. FAQ (Frequently Asked Questions)

**Q1. What is a commit in Git?**

A commit is a snapshot of code changes saved in the Git repository with a message describing the changes.

**Q2. Are Git Hooks shared automatically with the team?**

No. Git hooks are local to each developer. Tools like Husky or custom scripts are used to share them.

**Q3. Can commit hooks stop a commit?**

Yes. Hooks like pre-commit and commit-msg can block a commit if conditions are not met.

**Q4. Are commit hooks mandatory?**

They are optional but highly recommended for maintaining quality and consistency.

**Q5. What happens if a commit hook fails?**

The commit is cancelled, and Git shows the error message from the hook.

---

## 6. Contact Information

| Contact Type | Details                                                             |
| ------------ | ------------------------------------------------------------------- |
| Email        | [gunjan.jangra.snaatak@mygurukulam.co](mailto:gunjan.jangra.snaatak@mygurukulam.co) |

---

## 7. References

| Reference Name | Description |
|----------------|-------------|
| [Git Documentation – Hooks](https://git-scm.com/docs/githooks) | Official Git documentation explaining Git Hooks and their lifecycle |
| [Git Workflow Best Practices](https://www.atlassian.com/git/tutorials/comparing-workflows) | Explains Git workflows, commit standards, and best practices |

---
