# Task 3 - Attack Scenarios

## 1. SQL Injection

### Objective
To demonstrate how improper handling of user input can allow SQL queries to be manipulated.

### Normal Input
1

### SQL Injection Test
1' OR '1'='1' #

The test demonstrated that the SQL query could be manipulated and laboratory database records could be returned.

### UNION-Based SQL Injection
1' UNION SELECT user,password FROM users #

The UNION-based test demonstrated retrieval of laboratory usernames and password hashes from the DVWA database.

### Result
SQL Injection was successfully demonstrated in the controlled DVWA laboratory environment.

---

## 2. Stored Cross-Site Scripting (XSS)

### Objective
To demonstrate how malicious input stored by a web application can execute when the affected page is viewed.

### Test Payload
<img src=x onerror=alert('Stored XSS')>

### Result
The payload demonstrated Stored XSS in the DVWA environment.

---

## 3. Reflected Cross-Site Scripting (XSS)

### Objective
To demonstrate how user-controlled input reflected into a web page without appropriate output encoding can result in XSS.

### Test Payload
<script>alert('Reflected XSS')</script>

### Result
The payload demonstrated Reflected XSS in the controlled DVWA environment.

---

## 4. Cross-Site Request Forgery (CSRF)

### Objective
To understand how an application can be affected when state-changing requests are not protected against forged requests.

### Low Security Level
A forged password-change request was tested at the Low security level.

The request successfully demonstrated the CSRF vulnerability.

### High Security Level
The DVWA security level was increased to High.

A user_token parameter was observed in the request.

The previous forged request was no longer able to change the password because of the CSRF token protection.

### Result
CSRF was successfully demonstrated at Low security, while the High security configuration demonstrated token-based protection.

---

## 5. File Inclusion

### Objective
To test file inclusion functionality and evaluate whether local system files could be accessed.

### Normal Test
Normal file inclusion functionality was observed in the DVWA File Inclusion module.

### Local File Inclusion Test
../../../../etc/passwd

### Result
The attempted system-file disclosure was unsuccessful and resulted in an application warning.

No successful /etc/passwd disclosure was achieved.

---

## 6. Burp Suite Testing

### Objective
To explore Burp Suite as a web application security testing proxy.

### Proxy Configuration
Proxy Address:
127.0.0.1

Proxy Port:
8080

### Result
The Burp Suite proxy listener was configured and running.

Firefox was configured to use the local Burp proxy.

Reliable interception of DVWA traffic could not be completed during the laboratory session.

No successful request modification or Intruder fuzzing result is claimed.

---

## 7. HTTP Security Header Analysis

### Objective
To understand the importance of HTTP security headers in protecting web applications.

### Test
SecurityHeaders.com was used to analyze a safe public test website.

### Result
The test website received an F grade.

The following security headers were studied:

- Content-Security-Policy
- Strict-Transport-Security
- X-Content-Type-Options
- X-Frame-Options
- Referrer-Policy
- Permissions-Policy

---

## Summary of Results

SQL Injection:
Successfully demonstrated

Stored XSS:
Successfully demonstrated

Reflected XSS:
Successfully demonstrated

CSRF:
Successfully demonstrated at Low security

CSRF Token Protection:
Demonstrated at High security

File Inclusion:
Tested; LFI attempt unsuccessful

Burp Suite:
Proxy configured; interception incomplete

HTTP Security Headers:
Security weakness identified using SecurityHeaders.com

---

## Ethical Consideration

All testing was performed against the intentionally vulnerable DVWA application in a controlled local laboratory environment.

The techniques documented here were used only for educational and authorized cybersecurity practice.

No unauthorized testing was performed against external systems.
