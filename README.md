# task4-EL-


## 🛠 Tools Used
* **Primary:** Hashcat, John the Ripper
* **Identification:** Online Hash Identifiers (CrackStation, Hash Analyzer)
* **Wordlists:** RockYou.txt

---

## 🔍 Analysis Methodology

### 1. Hashing vs. Encryption
Unlike encryption, which is a two-way process (encrypt/decrypt), **hashing** is a one-way cryptographic function. Once a password is hashed, it cannot be reversed. Authentication works by hashing the user's input and comparing it to the stored hash in the database.

### 2. Hash Identification Table
Using online identification tools, we categorized various hashes based on their bit-length and character encoding.

| Algorithm | Sample Length | Security Level | Common Use Case |
| :--- | :--- | :--- | :--- |
| **MD5** | 32 chars | 🔴 Critical | Legacy systems (Highly insecure) |
| **SHA-1** | 40 chars | 🟠 Weak | Git integrity (Insecure for passwords) |
| **SHA-256** | 64 chars | 🟡 Moderate | Blockchain and file integrity |
| **bcrypt** | 60 chars | 🟢 Strong | Modern web application passwords |

### 3. Attack Vectors
We analyzed two primary methods used to bypass password security:
* **Dictionary Attack:** Uses a pre-defined list of common passwords (e.g., `RockYou.txt`). If a user chooses "password123", it is cracked instantly.
* **Brute Force Attack:** Systematically tries every possible combination of characters. This is effective against short passwords but computationally expensive for long ones.

---

## 🛡️ Defenses & Recommendations

To protect user credentials effectively, the following security controls are recommended:

1.  **Salting:** Adding a unique, random string to each password before hashing. This ensures that two users with the same password have different hashes, defeating **Rainbow Table** attacks.
2.  **Key Stretching:** Using algorithms like **bcrypt** or **Argon2** that include a "work factor" to intentionally slow down the hashing process, making brute force economically unfeasible.
3.  **Multi-Factor Authentication (MFA):** Implementing a second layer of security (e.g., TOTP, SMS, or Biometrics) so that a stolen password alone is not enough to gain access.
4.  **Rate Limiting:** Implementing account lockouts or time delays after multiple failed login attempts.

---

## 🏁 Final Outcome
Through this analysis, I have gained a deep understanding of:
* How to identify cryptographic hash types.
* The vulnerabilities inherent in legacy hashing algorithms.
* The critical importance of MFA and salted hashing in modern security architecture.

---
*Note: This project was completed for educational purposes as part of a Cybersecurity Analysis Task.*
