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
