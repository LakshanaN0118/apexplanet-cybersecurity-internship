# Task 3 - Mitigation Notes

## 1. SQL Injection Mitigation

SQL Injection can be reduced by avoiding direct concatenation of user input into SQL queries.

### Prepared Statements

A secure PHP demonstration used a parameterized query:

SELECT first_name, last_name FROM users WHERE user = ?

User input was passed as a parameter instead of being directly concatenated into the SQL query.

### Recommended Controls

- Use prepared statements.
- Use parameterized queries.
- Validate user input.
- Avoid constructing SQL queries directly from user input.
- Apply appropriate database permissions.

---

## 2. Cross-Site Scripting (XSS) Mitigation

XSS can be reduced by safely encoding user-controlled output.

### Output Encoding

The PHP demonstration used:

htmlspecialchars($name, ENT_QUOTES, "UTF-8")

This converts special characters into safe HTML representations.

### Content Security Policy

An additional CSP example was studied:

Content-Security-Policy: default-src 'self'; script-src 'self'

### Recommended Controls

- Validate input where appropriate.
- Encode output before displaying it.
- Use htmlspecialchars() for HTML output in PHP.
- Implement an appropriate Content Security Policy.
- Avoid inserting untrusted input directly into HTML or JavaScript.

---

## 3. CSRF Mitigation

CSRF protection prevents unauthorized state-changing requests from being accepted by the application.

### Recommended Controls

- Use unpredictable CSRF tokens.
- Validate CSRF tokens on state-changing requests.
- Use SameSite cookies where appropriate.
- Require authentication for sensitive operations.
- Avoid state-changing operations through unsafe GET requests.

### Laboratory Observation

The DVWA High security level used a user_token parameter.

The previous forged request was no longer able to change the password after CSRF token protection was enabled.

---

## 4. File Inclusion Mitigation

File inclusion vulnerabilities can occur when applications directly trust user-controlled file paths.

### Recommended Controls

- Validate file-related input.
- Use allowlists for permitted files.
- Restrict accessible directories.
- Avoid directly using user-controlled paths.
- Apply appropriate server configuration.
- Use application-level filtering and validation.

### Laboratory Observation

A Local File Inclusion attempt targeting:

../../../../etc/passwd

was unsuccessful and resulted in an application warning.

---

## 5. HTTP Security Header Mitigation

Security headers provide additional protection against several classes of web attacks.

### Important Headers

Content-Security-Policy:
Helps control which content and scripts a browser is allowed to load.

Strict-Transport-Security:
Helps enforce HTTPS connections.

X-Content-Type-Options:
Helps prevent MIME-type sniffing.

X-Frame-Options:
Helps control whether the application can be loaded inside frames.

Referrer-Policy:
Controls how referrer information is shared.

Permissions-Policy:
Controls access to selected browser features.

### Example Security Headers

X-Content-Type-Options: nosniff

X-Frame-Options: SAMEORIGIN

Referrer-Policy: strict-origin-when-cross-origin

Content-Security-Policy: default-src 'self'; script-src 'self'

---

## 6. General Web Application Security Practices

- Validate and sanitize user input.
- Encode untrusted output.
- Use secure authentication and authorization controls.
- Protect state-changing requests against CSRF.
- Use secure HTTP response headers.
- Apply least-privilege principles.
- Keep web applications and dependencies updated.
- Perform security testing in authorized environments.

---

## 7. Security Testing Ethics

All mitigation techniques and security testing activities in this task were performed in the controlled DVWA laboratory environment.

Security testing should only be performed on systems for which explicit authorization has been obtained.

The objective of the exercises was to understand common web application vulnerabilities and their corresponding security controls.

---

## Conclusion

The mitigation exercises demonstrated that secure input handling, output encoding, CSRF tokens, file allowlisting, and appropriate HTTP security headers can significantly improve web application security.

The techniques documented in this file are based on the controlled laboratory work completed during Task 3.
