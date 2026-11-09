# Project 03 – Web Application Security Testing and Browser Traffic Inspection

**Status:** Practical tool exposure and controlled DVWA exercises  
**Tools:** Burp Suite, OWASP ZAP, DVWA, browser  
**Environment:** Controlled training lab

## 1. Objective

Practise observing browser-to-application traffic and understand how web application testing tools help identify potential security weaknesses.

## 2. Scope and authorization

Testing should only be performed against DVWA or another application that is intentionally provided for training, owned by the learner, or explicitly authorized. Never intercept or inspect another person's traffic or test a live website without permission.

## 3. Activities performed

The learner reports using:

- **Burp Suite** for browser traffic monitoring and inspection during practical exercises.
- **OWASP ZAP** for browser traffic monitoring and inspection during practical exercises.
- **DVWA** as a deliberately vulnerable training application.

The DVWA exercises previously practised included navigation through modules for:

- Brute Force
- Command Execution
- CSRF
- File Inclusion
- SQL Injection
- File Upload
- Cross-Site Scripting (XSS)

The DVWA security setting was changed to **Low** for the learning exercise. This is an intentionally insecure training configuration and must not be used for a real application.

## 4. Method

A repeatable lab workflow:

1. Start the isolated DVWA environment.
2. Configure the browser to use the local proxy provided by Burp Suite or OWASP ZAP.
3. Browse the training application and observe HTTP requests and responses.
4. Identify request parameters, headers, cookies and response behaviour.
5. Use only the training modules and test cases within the authorized lab.
6. Record observations and explain potential defensive controls.

## 5. Security concepts explored

- SQL injection: unsafe handling of user-supplied input in database queries.
- Cross-site scripting: untrusted content being interpreted as executable browser script.
- Command execution: application input potentially reaching operating-system commands.
- File inclusion: unsafe handling of file paths or include parameters.
- Brute-force risk: weak authentication controls that permit repeated login attempts.
- CSRF: unintended actions triggered through an authenticated user's browser.

These are topics explored in the DVWA learning environment; this document does not claim that a production application was tested or compromised.

## 6. Defensive recommendations

- Use parameterized database queries and server-side input validation.
- Apply context-aware output encoding and appropriate content security controls.
- Avoid passing untrusted input to operating-system commands.
- Restrict file access to approved directories and validate file paths.
- Enforce rate limiting, strong authentication and MFA.
- Use CSRF tokens and appropriate cookie settings.
- Keep frameworks and application dependencies updated.

## 7. Evidence to add

Add sanitized screenshots that show the local lab and proxy tools, without exposing credentials, session cookies or tokens:

- `evidence/burp-proxy-intercept.png`
- `evidence/zap-sites-or-history.png`
- `evidence/dvwa-training-module.png`

Do not publish live session cookies, authorization headers, passwords or personal data.

## 8. Learning outcome

This exercise developed familiarity with intercepting and reviewing browser traffic and understanding common web application vulnerability categories.

## 9. Limitations

The available notes confirm tool use and DVWA module practice but do not contain a complete request/response evidence set or validated vulnerability report. No production testing is claimed.
