# 02-PHM_PRIR_Report_V1.0: Gap Analysis and Control Recommendations

## 🎯 Target Policy: BeginnerCorp Access Control Policy V1.0 (AS-IS)
The current policy was evaluated against the fundamental security principles: **Confidentiality, Integrity, Availability (CIA Triad)**, and **Authentication, Authorization, Accounting (AAA)**, plus **Non-Repudiation**.

---

## I. CIA TRIAD Analysis

### A. Confidentiality

* **Policy Gap:** **GAP FOUND.** Weak 8-character password requirement and allowing all employees access to all files dramatically increases the risk of unauthorized disclosure.
* **Recommendation (Security Control):** Enforce **Multi-Factor Authentication (MFA)** for all logins and implement **Role-Based Access Control (RBAC)** to ensure users can only view data necessary for their job (**Need-to-Know**).

### B. Integrity

* **Policy Gap:** **GAP FOUND.** The policy permits any employee to modify (and potentially corrupt) any file, and there is no mechanism to verify a file's authenticity after modification.
* **Recommendation (Security Control):** Implement **File Hashing** and **Digital Signatures** to verify the data's integrity and source.

### C. Availability

* **Policy Gap:** **GAP FOUND.** The policy makes no mention of backups, redundancy, or disaster recovery. A single system failure could lead to complete data loss or service disruption.
* **Recommendation (Security Control):** Mandate a **daily, off-site backup schedule** and implement **server redundancy** (e.g., a high-availability cluster) to ensure continuous access.

---

## II. AAA and Non-Repudiation Analysis

### A. Authentication

* **Policy Gap:** **PARTIAL GAP.** While passwords are required, the 8-character minimum is considered weak and highly vulnerable to **brute-force attacks**.
* **Recommendation (Security Control):** Require stronger authentication methods, such as **passphrases** (16+ characters) or **MFA**, to verify the user's identity more robustly.

### B. Authorization

* **Policy Gap:** **MAJOR GAP.** Granting all employees the right to "read and modify all files" violates the **Principle of Least Privilege (PoLP)**.
* **Recommendation (Security Control):** Implement **RBAC** to strictly limit user permissions based on their job function, granting only the minimum access (e.g., read-only) required to perform tasks.

### C. Accounting & Non-Repudiation

* **Policy Gap:** **MAJOR GAP.** The policy only logs a successful login. It fails to log critical actions like file deletions, modifications, or attempted access failures. This makes **Non-Repudiation** impossible.
* **Recommendation (Security Control):** **Log all critical user activities** (file operations, system changes, administrative actions). Protect these logs and send them to a **SIEM** system for auditing to ensure the user cannot deny their actions (**Non-Repudiation**).
