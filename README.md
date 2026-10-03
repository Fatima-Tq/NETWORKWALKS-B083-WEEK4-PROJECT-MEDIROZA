# 🔐 Mediroza General Hospital — Web Application Penetration Testing

## 📌 Project Overview

This project presents an **authorized black-box penetration testing assessment** of the Mediroza General Hospital web application.

The assessment was performed in a controlled educational environment over **5 days** with written authorization. The objective was to identify security vulnerabilities, demonstrate their potential impact, and provide practical remediation recommendations.

> ⚠️ **Disclaimer:** This project was performed only in an authorized and controlled environment. The techniques demonstrated must never be used against systems without explicit permission.

---

## 🎯 Objectives

* Perform black-box reconnaissance
* Identify exposed directories and resources
* Test authentication mechanisms
* Identify web application vulnerabilities
* Assess the security of protected PDF documents
* Analyze exposed document metadata
* Investigate publicly accessible backup files
* Evaluate the potential impact of discovered vulnerabilities
* Provide security recommendations and remediation steps

---

## 🛠️ Tools & Technologies

* **curl** — reconnaissance and robots.txt enumeration
* **Manual Browser Testing** — login and application analysis
* **Manual SQL Injection Testing**
* **Networkwalks Hash Calculator** — PDF hash extraction
* **Networkwalks Password Cracker** — authorized password testing
* **qpdf** — PDF decryption
* **ExifTool** — metadata analysis
* **wget** — file retrieval
* **AI-assisted Data Analysis** — SQL dump analysis

The testing methodology followed:

**Reconnaissance → Authentication Testing → Exploitation → Post-Exploitation Analysis → Reporting**

---

## 🔎 Key Findings

### 1. Username Enumeration

The login page returned different error messages for valid and invalid usernames, allowing potential username enumeration.

**Severity:** Medium

---

### 2. SQL Injection — Authentication Bypass

A SQL injection vulnerability was identified in the login mechanism. Testing demonstrated that authentication could be bypassed without valid credentials.

**Severity:** Critical

This vulnerability provided access to the patient portal and demonstrated how an initial web vulnerability could lead to further data exposure.

---

### 3. Weak PDF Passwords

Patient PDF reports were protected with passwords that were susceptible to dictionary-based password testing.

**Severity:** High

The assessment demonstrated that predictable passwords provided limited protection for sensitive documents.

---

### 4. Sensitive PDF Metadata

Metadata contained an internal note that disclosed information about the location of an old database backup.

**Severity:** Medium

This demonstrated how seemingly harmless document metadata can unintentionally expose internal information.

---

### 5. Publicly Accessible Backup Directory

An old backup directory was accessible through the web server with directory listing enabled.

**Severity:** Critical

A database backup file was exposed through the publicly accessible directory.

---

### 6. Sensitive Database Information Exposure

The exposed database backup contained sensitive staff salary and shareholder information in plain text.

**Severity:** Critical

---

## 📊 Risk Summary

| Finding                           | Severity |
| --------------------------------- | -------- |
| Username Enumeration              | Medium   |
| SQL Injection / Login Bypass      | Critical |
| Patient PDF Exposure              | High     |
| Weak PDF Passwords                | High     |
| Sensitive PDF Metadata            | Medium   |
| Exposed Backup Directory          | Critical |
| Confidential Database Information | Critical |

The report identified **7 security findings** ranging from Medium to Critical severity.

---

## 🛡️ Remediation Recommendations

### SQL Injection

* Use parameterized queries / prepared statements
* Never concatenate raw user input into SQL queries
* Implement proper input validation
* Consider a Web Application Firewall as an additional security layer

### PDF Security

* Store sensitive documents outside the public web root
* Implement proper authentication and access control
* Use strong, unique passwords where PDF password protection is required

### Metadata Protection

* Remove unnecessary metadata before distributing documents
* Add document sanitization to the file-generation workflow

### Backup Security

* Disable directory listing
* Remove old backups from public directories
* Store database backups outside publicly accessible web directories
* Perform regular audits for forgotten or orphaned files

### General Security

* Conduct regular penetration testing and vulnerability scanning
* Provide secure coding and data-handling training
* Apply least-privilege principles to sensitive data

These recommendations are based on the remediation section of the assessment report.

---

## 📚 Skills Demonstrated

* Web Application Security
* Penetration Testing
* Reconnaissance
* Authentication Testing
* SQL Injection Testing
* Vulnerability Identification
* PDF Security Assessment
* Metadata Analysis
* Data Exposure Analysis
* Risk Assessment
* Security Reporting
* Vulnerability Remediation

---

## ⚠️ Ethical & Legal Notice

This project was conducted for educational purposes in an authorized testing environment. The target was tested only with written authorization.

**Never perform penetration testing, vulnerability exploitation, password testing, or data extraction against systems without explicit permission from the owner.**
