# Web Application Security Lab: SQL Injection & Authentication Weakness

## Overview
This project demonstrates practical exploitation of web application vulnerabilities using a controlled lab environment.

The focus areas include:
- SQL Injection (SQLi)
- Authentication Weakness (Brute Force)
- Poor Input Validation

Testing was conducted using DVWA (Damn Vulnerable Web Application) in a local lab environment.

---

## Lab Environment

- OS: Kali Linux
- Web App: DVWA
- Database: MySQL
- Web Server: Apache
- Network: Localhost

---

## Vulnerability 1: SQL Injection

### Description
SQL Injection occurs when user input is directly inserted into a database query without proper sanitization.

---

### Exploitation

**Payload Used:**
```sql
' OR '1'='1
```

---

### Evidence

![SQL Injection Result](screenshots/sql-injection.png)

---

### Result
- Successfully retrieved multiple user records from the database
- Demonstrated lack of input validation

---

### Impact
- Exposure of sensitive user data
- Full database compromise possible

---

## Vulnerability 2: Brute Force / Weak Authentication

### Description
The login system allows repeated login attempts without restriction.

---

### Evidence

![Brute Force Login](screenshots/bruteforce.png)

---

### Exploitation Method
- Multiple login attempts with common credentials
- No account lockout or rate limiting

---

### Impact
- Unauthorized account access
- Credential compromise

---

## Attack Flow

1. Access DVWA login interface  
2. Perform brute-force attempts  
3. Identify weak authentication controls  
4. Execute SQL Injection  
5. Extract database records  

---

## MITRE ATT&CK Mapping

| Stage | Technique | ID |
|------|----------|----|
| Initial Access | Exploit Public-Facing Application | T1190 |
| Credential Access | Brute Force | T1110 |
| Persistence | Valid Accounts | T1078 |

---

## Mitigation Strategies

- Use parameterized queries (Prepared Statements)
- Implement input validation and sanitization
- Enforce strong password policies
- Enable account lockout after failed attempts
- Deploy Web Application Firewall (WAF)
- Use Multi-Factor Authentication (MFA)

---

## Key Takeaways

- SQL Injection remains a critical web vulnerability
- Weak authentication mechanisms increase attack surface
- Proper validation and security controls are essential

---

## Disclaimer

This project was conducted in a controlled lab environment for educational purposes only.  
No real systems were targeted.

---
