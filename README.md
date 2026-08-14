# 🔐 Linux User Security Auditor

A lightweight Bash-based security auditing tool for reviewing local Linux user accounts and identifying potentially risky account configurations.

The script automates several account-security checks and generates a dated text report containing the audit findings.

---

## ✨ Features

The current script checks for:

- 👑 Users with UID 0 (root privileges)
- 🔑 Users with empty password fields
- 🕒 Users who have never logged in
- 📁 Potentially risky user home-directory permissions
- ⚠️ Users present in `/etc/passwd` but missing from `/etc/shadow`
- 📄 Automatic generation of a dated audit report

---

## 🧰 Technologies

- Bash
- Linux
- Shell Scripting
- Linux User Management
- System Administration
- Security Auditing

---

## 📋 Prerequisites

To run the script, you need:

- A Linux operating system
- Bash shell
- Standard Linux utilities such as `awk`, `grep`, `cut`, and `lastlog`
- Appropriate permissions to inspect system account information
- `sudo` access for checks involving `/etc/shadow`

---

## 🚀 Getting Started

### Clone the Repository

`git clone https://github.com/abdullah-al-rafid/linux-user-security-auditor.git`

`cd linux-user-security-auditor`

### Make the Script Executable

`chmod +x automated.sh`

---

## ▶️ Usage

Run the security auditor:

`./automated.sh`

Depending on your system permissions, you may be prompted for sudo access during checks involving `/etc/shadow`.

After the audit completes, the script creates a report using the following naming format:

`user_audit_YYYY-MM-DD.txt`

---

## 🔎 Security Checks

### 1. Root-Privilege Accounts

Identifies accounts with UID `0`.

On a typical Linux installation, root is expected to have UID 0. Additional UID 0 accounts should be reviewed.

### 2. Empty Password Fields

Checks `/etc/shadow` for user entries with an empty password field.

### 3. Never-Logged-In Users

Uses `lastlog` to identify accounts reported as never having logged in.

These results should be reviewed in context because some legitimate system or service accounts may never require interactive login.

### 4. Home-Directory Permission Check

Reviews user home directories for the permission condition implemented by the script.

Potential findings should be manually verified before making permission changes.

### 5. `/etc/shadow` Consistency

Checks whether users listed in `/etc/passwd` also have corresponding entries in `/etc/shadow`.

---

## 📊 Audit Report

An example generated report is included in this repository:

`user_audit_2025-04-11.txt`

The report records the results of each security check and can be reviewed after the script finishes.

---

## 📁 Project Structure

- `automated.sh` — Main Bash security auditing script
- `user_audit_2025-04-11.txt` — Example generated audit report
- `README.md` — Project documentation

---

## 🔐 Why This Project?

User-account configuration is an important part of Linux system security.

This project demonstrates how Bash scripting can automate repetitive account-auditing tasks and consolidate findings into a simple report for further review.

> **Note:** This project is intended for educational and authorized security-auditing purposes. A reported condition is not automatically a confirmed vulnerability and should be manually reviewed before remediation.

---

## 🎯 Project Goals

This project was created to strengthen practical knowledge of:

- Linux user and account management
- Bash scripting
- Linux file and account structures
- Security auditing fundamentals
- Command-line automation
- System administration

---

## 🔮 Future Improvements

Planned improvements:

- Add configurable audit checks
- Add severity levels for findings
- Improve home-directory permission validation
- Add color-coded terminal output
- Improve report formatting
- Add optional CSV or JSON report export
- Add command-line arguments and help documentation

---

## 👨‍💻 Author

**Abdullah Al Rafid**

Computer Science & Engineering Student  
Daffodil International University

GitHub: [@abdullah-al-rafid](https://github.com/abdullah-al-rafid)

LinkedIn: [Abdullah Al Rafid](https://www.linkedin.com/in/abdullah-al-rafid)
