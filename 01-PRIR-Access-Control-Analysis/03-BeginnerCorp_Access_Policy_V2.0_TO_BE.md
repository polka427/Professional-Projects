# BeginnerCorp Access Control Policy - Version 2.0 (TO-BE)

## 1. Authentication and Confidentiality Controls (CIA)

* **Authentication & Confidentiality:** All users must log in using **Multi-Factor Authentication (MFA)**. Passwords (Passphrases) must be a minimum of **16 characters** and include a mix of uppercase, lowercase, numbers, and symbols.
* **Confidentiality:** Access to critical data is managed via **Role-Based Access Control (RBAC)** to enforce the **Need-to-Know** principle. Data classified as "Confidential" must be stored using **AES-256 encryption**.

## 2. Authorization and Integrity Controls (IAA)

* **Authorization & Integrity:** **Principle of Least Privilege (PoLP)** is strictly enforced. Users are only granted the minimum permissions required to perform their tasks (e.g., Read-Only access for non-editors).
* **Integrity & Non-Repudiation:** All critical file modifications and transfers must be authenticated and verified using **Digital Signatures** (PKI concepts) and **Hashing** (e.g., SHA-256) to ensure the data is accurate and untampered.

## 3. Accounting and Availability Controls (AA)

* **Accounting & Non-Repudiation:** Detailed **Audit Logs** must capture all critical user activities, including logons/logoffs, failed access attempts, and all file operations (**read, write, delete**). These logs are protected and sent to a **SIEM** system for centralized, non-editable storage.
* **Availability:** All critical file servers must have an automated **daily backup schedule**. The backups must be stored **off-site** (or in a secure cloud) and verified quarterly. **Redundant servers** must be maintained for immediate failover in case of hardware failure.
