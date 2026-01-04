# OWASP Top 10 (2025)

### A01:2025 - Broken Access Control
* **What it means:** Users acting outside of intended permissions.
* **Examples:** IDOR (changing URL IDs), bypassing frontend access checks.
* **How to test:** Manual IDOR testing; automated endpoint scanning with OWASP ZAP.
* **How to fix:** Enforce "Deny by Default" and server-side authorization checks.

---

### A02:2025 - Security Misconfiguration
* **What it means:** Improperly secured app stacks or cloud environments.
* **Examples:** Default admin credentials; unhardened cloud buckets (S3).
* **How to test:** Configuration audits (Scout Suite); checking for verbose error headers.
* **How to fix:** Use Infrastructure as Code (IaC) with hardened, automated templates.

---

### A03:2025 - Software Supply Chain Failures
* **What it means:** Vulnerabilities from 3rd-party libraries or CI/CD tools.
* **Examples:** Compromised npm packages; outdated libraries (e.g., Log4j).
* **How to test:** Audit SBOMs (Software Bill of Materials); use SCA tools like Snyk.
* **How to fix:** Pin dependency versions and verify signatures/checksums.

---

### A04:2025 - Cryptographic Failures
* **What it means:** Weak encryption for data at rest or in transit.
* **Examples:** Using HTTP instead of HTTPS; weak hashing (MD5/SHA-1).
* **How to test:** SSL Labs for TLS config; scanning code for hardcoded keys.
* **How to fix:** Enforce TLS 1.3 and use modern hashing like Argon2 or bcrypt.

---

### A05:2025 - Injection
* **What it means:** Untrusted data sent to an interpreter as a command.
* **Examples:** SQLi, OS Command Injection, XSS.
* **How to test:** Input fuzzing; Static Analysis (SAST) for unparameterized queries.
* **How to fix:** Use parameterized queries and strict "Allow-list" input validation.

---

### A06:2025 - Insecure Design
* **What it means:** Architectural flaws that code patches cannot fix.
* **Examples:** Lack of lockout mechanisms; missing "least privilege" architecture.
* **How to test:** Threat Modeling during design; architectural review.
* **How to fix:** Implement Secure Development Lifecycle (SDL) and secure design patterns.

---

### A07:2025 - Authentication Failures
* **What it means:** Weaknesses in user identity or session management.
* **Examples:** Permitting weak passwords; session tokens that don't expire.
* **How to test:** Brute-force testing; checking session fixation in Burp Suite.
* **How to fix:** Implement MFA and use managed, secure session handlers.

---

### A08:2025 - Software or Data Integrity Failures
* **What it means:** Data/code modified without verification during updates.
* **Examples:** Unsigned software updates; insecure deserialization.
* **How to test:** Verify CI/CD signing; test for tampering in serialized objects.
* **How to fix:** Use digital signatures to verify the integrity of all payloads.

---

### A09:2025 - Security Logging and Alerting Failures
* **What it means:** Security events are not logged or monitored.
* **Examples:** Silent login failures; no alerts for database dumps.
* **How to test:** Manually trigger suspicious acts and verify logs in a SIEM.
* **How to fix:** Centralize logs and ensure they contain User ID, IP, and Timestamps.

---

### A10:2025 - Mishandling of Exceptional Conditions
* **What it means:** Systems failing "open" or leaking data during errors.
* **Examples:** Stack traces shown to users; auth bypass during service timeout.
* **How to test:** Force error states (kill DB connections) and observe behavior.
* **How to fix:** Use global error handlers and ensure the system "fails closed."
