# Task 3 - Web Application Security

## Overview

Task 3 focused on identifying and understanding common web application security vulnerabilities using Damn Vulnerable Web Application (DVWA) in a controlled local laboratory environment.

## Lab Environment

Operating System:
Kali Linux

Web Application:
Damn Vulnerable Web Application (DVWA)

Container Platform:
Docker

DVWA Address:
http://127.0.0.1:4280

Web Security Proxy:
Burp Suite

Security Header Scanner:
SecurityHeaders.com

Browser:
Firefox

DVWA Security Levels:
Low / High depending on the test

## Vulnerabilities Studied

The following web application security vulnerabilities were investigated:

- SQL Injection
- Stored Cross-Site Scripting (XSS)
- Reflected Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- File Inclusion
- HTTP Security Headers

## SQL Injection

SQL Injection was tested using the DVWA SQL Injection module.

The testing demonstrated that unsafe input handling could allow SQL conditions to be manipulated and laboratory database records to be returned.

A UNION-based SQL Injection test also demonstrated retrieval of laboratory usernames and password hashes.

### SQL Injection Mitigation

A separate PHP demonstration was created using prepared statements and parameterized input.

The implementation used:

SELECT first_name, last_name FROM users WHERE user = ?

User input was passed as a parameter rather than directly concatenated into the SQL query.

Input was also safely displayed using htmlspecialchars().

## Cross-Site Scripting

### Stored XSS

Stored XSS was tested in the DVWA XSS Stored module.

The test demonstrated that malicious input could be stored by the application and executed when the affected page was viewed.

### Reflected XSS

Reflected XSS was tested by submitting user-controlled input that was reflected into the web page without appropriate output encoding.

### XSS Mitigation

A secure PHP demonstration used htmlspecialchars() to encode user input.

Content Security Policy (CSP) was also implemented as an additional security control.

## Cross-Site Request Forgery

CSRF was tested using the DVWA CSRF module.

At Low security, a forged password-change request successfully demonstrated the vulnerability.

The DVWA security level was then increased to High.

A CSRF token was observed in the application, and the previous forged request was no longer able to change the password.

### CSRF Mitigation

Recommended protections include:

- Use unpredictable CSRF tokens
- Validate tokens on state-changing requests
- Use SameSite cookies where appropriate
- Require authentication for sensitive operations
- Avoid state-changing operations through unsafe GET requests

## File Inclusion

The DVWA File Inclusion module was tested.

Normal file inclusion functionality was observed.

A Local File Inclusion attempt targeting /etc/passwd was also performed.

The attempted system-file disclosure was unsuccessful and resulted in an application warning.

Potential protections include:

- Input validation
- Path restrictions
- File allowlisting
- Server configuration
- Application-level filtering

## Burp Suite

Burp Suite was explored as a web application security testing platform.

Firefox was configured to use Burp Suite as a local proxy.

Proxy Address:
127.0.0.1

Proxy Port:
8080

The Burp proxy listener was confirmed to be running.

Reliable interception of DVWA traffic could not be completed during the laboratory session, so no successful request modification or Intruder fuzzing result is claimed.

## HTTP Security Headers

SecurityHeaders.com was used to analyze a safe public test website.

The test website received an F grade from the scanner.

Security headers studied included:

- Content-Security-Policy
- Strict-Transport-Security
- X-Content-Type-Options
- X-Frame-Options
- Referrer-Policy
- Permissions-Policy

## Security Header Mitigation

Example Apache security header configuration was studied:

X-Content-Type-Options: nosniff

X-Frame-Options: SAMEORIGIN

Referrer-Policy: strict-origin-when-cross-origin

Content-Security-Policy: default-src 'self'; script-src 'self'

## Overall Findings

SQL Injection:
Successfully demonstrated - High

Stored XSS:
Successfully demonstrated - Medium/High

Reflected XSS:
Successfully demonstrated - Medium

CSRF:
Successfully demonstrated at Low security - Medium

CSRF Token Protection:
Successfully demonstrated at High security - Mitigated

File Inclusion:
Tested; LFI unsuccessful - Potential

Burp Suite:
Proxy configured; interception incomplete - Not completed

Security Headers:
Test website received F - Security weakness

## Key Mitigation Techniques

SQL Injection:
Use parameterized queries and prepared statements.

XSS:
Use input validation, output encoding, and Content Security Policy.

CSRF:
Use unpredictable anti-CSRF tokens and secure cookie settings.

File Inclusion:
Use allowlists for permitted files and never directly trust user-controlled file paths.

HTTP Security Headers:
Configure appropriate security headers at the web server or application level.

## Ethical Consideration

All security testing was performed against the intentionally vulnerable DVWA application running locally in a controlled laboratory environment.

No unauthorized testing was performed against external systems.

The techniques documented in this task should only be used on systems for which explicit authorization has been obtained.

## Conclusion

Task 3 provided practical experience in identifying common web application vulnerabilities and understanding their mitigation techniques.

SQL Injection, Stored XSS, Reflected XSS and CSRF were successfully demonstrated in the controlled DVWA environment.

File Inclusion was tested, but successful system-file disclosure was not achieved.

Burp Suite was configured as a local proxy, although reliable interception could not be completed.

SecurityHeaders.com was used to analyze HTTP security headers and understand their role in web application protection.
