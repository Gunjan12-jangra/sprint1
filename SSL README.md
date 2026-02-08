# SSL (Secure Sockets Layer) Documentation

---

## Authors

| Author           | Created     | Version | Last updated by  | Last Edited On | L0 Reviewer | L1 Reviewer | L2 Reviewer |
| ---------------- |---------------- | ------- | ---------------- | -------------- | ----------- | ----------- | ----------- |
| Gunjan Jangra  |  8-02-2026     |  1.0     | Gunjan Jangra |  8-02-2026     |                |             |             |

---


## Table of Contents
1. [Introduction](#1-introduction)
2. [Why SSL is Required](#2-why-ssl-is-required)
3. [What is SSL](#3-what-is-ssl)
4. [How SSL Works](#4-how-ssl-works)
5. [How to Get an SSL Certificate](#5-how-to-get-an-ssl-certificate)
6. [Types of SSL Certificates](#6-types-of-ssl-certificates)
7. [SSL Providers](#7-ssl-providers)
8. [Detailed Comparison of SSL Providers](#8-detailed-comparison-of-ssl-providers)
9. [Recommendation](#9-recommendation)
10. [Contact Information](#10-contact-information)
11. [References](#11-references)

---

## 1. Introduction

The purpose of this document is to explain why SSL is important and how it is used to secure web communication.

SSL (Secure Sockets Layer) is a security technology that creates a secure connection between a user’s web browser and a server. It protects data so that it cannot be read or changed by unauthorized users.

Websites using SSL show:

- HTTPS in the URL

- A lock icon in the browser

---

## 2. Why SSL is Required

SSL is required to keep data safe and build trust. It:

- Protects passwords and sensitive information

- Prevents hacking and data theft

- Builds trust with users

- Mandatory for login, payment, and business websites

- Improves website ranking on search engines

---

## 3. What is SSL

SSL is a digital certificate that:

- Confirms the identity of a website

- Encrypts the data exchanged between the browser and the server

Each SSL certificate is issued for a specific domain name, such as example.com.

---

## 4. How SSL Works

SSL works using a process called the SSL handshake:

- A user opens a website

- The browser requests the SSL certificate from the server

- The certificate is verified by a trusted Certificate Authority (CA)

- A secure encrypted connection is established

- Data is safely transmitted between the browser and the server

---

## 5. How to Get an SSL Certificate

Steps to obtain an SSL certificate:

### Step 1: Choose an SSL Provider

Select a trusted Certificate Authority such as Let’s Encrypt or DigiCert.

### Step 2: Generate CSR

Generate a Certificate Signing Request (CSR) on the server.
It contains domain and organization details.

### Step 3: Domain Verification

Verify ownership of the domain using:

- Email verification

- DNS record

- File upload on the server

### Step 4: Install the Certificate

Install the SSL certificate on the web server.

---

## 6. Types of SSL Certificates

### 1. Domain Validation (DV)

- Checks only domain ownership

- Basic security

- Mostly free or low cost

### 2. Organization Validation (OV)

- Verifies company details

- Medium security level

### 3. Extended Validation (EV)

- Full company verification

- Highest level of trust

---

## 7. SSL Providers

Some commonly used SSL providers are:

| Provider |	Cost |	Best Use |
| -------------------- | -------------- | ------------------ |
| Let’s Encrypt |	Free |	Small and personal websites |
| DigiCert	| Paid	| Enterprise websites |
| GlobalSign |	Paid |	Business websites |
| GoDaddy |	Paid |	Easy setup |

---

## 8. Detailed Comparison of SSL Providers

| Feature |	Let’s Encrypt |	DigiCert |	GlobalSign |
| -------------- | ---------------- | ---------------- | -------------- |
| Cost	| Free | 	High |	Medium |
| Certificate Types |	DV |	DV, OV, EV |	DV, OV, EV |
| Validity Period |	90 Days |	1 Year |	1 Year |
| Automation Support	| Yes (Fully automated) |	Limited | Limited |

---

## 9. Recommendation

| Use Case | Recommended SSL Provider |
|----------|--------------------------|
| Small or test websites | Let’s Encrypt |
| Business websites | GlobalSign |
| Enterprise or financial systems | DigiCert |

---

## 10. Contact Information

| Contact Type | Details                                                             |
| ------------ | ------------------------------------------------------------------- |
| Email        | [gunjan.jangra.snaatak@mygurukulam.co](mailto:gunjan.jangra.snaatak@mygurukulam.co) |

---

## 11. References

| References Link | Description |
|-----------------|-------------|
| [SSL Overview](https://www.cloudflare.com/learning/ssl/what-is-ssl/) | Basic explanation of SSL |
| [Let’s Encrypt Documentation](https://letsencrypt.org/docs/) | Official guide for free SSL certificates |

---
