# DVWA SQL Injection Lab

## 📌 Project Overview
This project demonstrates a SQL Injection vulnerability discovered in DVWA (Damn Vulnerable Web Application) running in a controlled lab environment.

Environment:
- Kali Linux (Attacker)
- Metasploitable 2 (Target)
- DVWA (Security Level: Low)
- VirtualBox Lab Setup

---

## 🔎 Vulnerability Details

- Vulnerability Type: SQL Injection (Error-Based)
- Endpoint: /dvwa/vulnerabilities/sqli/
- Parameter: id
- Method: GET

---

## 🧪 Proof of Concept

When inserting:

```
1'
```

The application returns:

```
You have an error in your SQL syntax...
```

This confirms unsanitized user input is directly passed into the SQL query.


---
## 📸 Screenshots

![SQL Error](screenshots/Screenshot_2026-02-27_17_02_03.png)

![SQL Error](screenshots/Screenshot_2026-02-27_17_08_39.png)

## 🧠 Technical Analysis

The SQL Injection occurs because the application directly inserts user input into the SQL query without sanitization or parameterized statements.

Example vulnerable pattern:

SELECT * FROM users WHERE id = '$id';

When a single quote is injected (1'), the query breaks and produces a database error, confirming improper input handling.
---
## ⚠️ Impact

An attacker could potentially:
- Extract database information
- Bypass authentication
- Access sensitive data

---

## 🛡️ Remediation

To fix this vulnerability:
- Use prepared statements
- Use parameterized queries
- Validate and sanitize user input
- Disable detailed SQL error messages

---

## 📚 Learning Outcome

This lab improved my understanding of:
- SQL query structure
- Input validation weaknesses
- Error-based SQL Injection detection
- Web application security testing
