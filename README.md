# Brute Force Attack Prevention and Penetration Testing Report

**Author:** Dirghayu Pradhanang  
**Project Type:** Academic Cybersecurity Research  
**Date:** Autumn 2024 – Spring 2025  

## 📘 Overview

This project provides an in-depth look into brute force attacks and how to mitigate them. The research includes a practical demonstration using Kali Linux and Medusa to simulate an SSH brute force attack, followed by a series of mitigation techniques to harden system security.

## 🔍 Objectives

- Understand types and mechanics of brute force attacks.
- Execute a brute force attack in a safe, ethical lab environment.
- Test mitigation strategies including MFA, Fail2ban, DenyHosts, and SSH key-based auth.
- Evaluate mitigation methods for effectiveness using PTES methodology.
- Educate others through detailed, PTES-aligned documentation and demonstration.

## 🛠️ Tools Used

- **Kali Linux**
- **Medusa**
- **Nmap**
- **Google Authenticator**
- **Fail2ban**
- **DenyHosts**
- **OpenSSH**

## ⚙️ Demonstration Summary

### Brute Force Attack via Medusa
```bash
medusa -h 127.0.0.1 -u testuser -P passwords.txt -M ssh
```
**Result:**  
`ACCOUNT FOUND: [ssh] Host: 127.0.0.1 User: testuser Password: password123`

### SSH Security Mitigations

| Mitigation Method        | Description                                               | Outcome           |
|--------------------------|-----------------------------------------------------------|-------------------|
| MFA                      | Google Authenticator (PAM module)                         | Login blocked     |
| SSH Keys                 | Disabled password login; used `ssh-keygen -t rsa -b 4096` | Attack blocked    |
| Fail2ban                 | Configured with maxretry=3 in jail.local                  | IP Banned         |
| DenyHosts                | Added brute IPs to /etc/hosts.deny                        | Access blocked    |
| Account Lockout Policy   | `pam_tally2.so deny=5 unlock_time=300`                    | User Locked Out   |

## 🧪 Evaluation Table

| Technique     | Effectiveness | Complexity | Best Used In                         |
|---------------|---------------|------------|--------------------------------------|
| MFA           | High          | Medium     | High-risk environments               |
| SSH Keys      | Very High     | Medium     | Server admin, cloud systems          |
| Fail2ban      | High          | Low        | Public-facing services               |
| DenyHosts     | Medium        | Low        | Lightweight SSH-only systems         |
| Lockout Policy| Medium        | Low        | Small business / intranet services   |

## 🧠 Case Studies

- **Adobe Breach (2013)**: Weak password encryption exposed 153M users.
- **Instagram Attack (2019)**: Automated brute force bots bypassed protections.

## 📋 Methodology: PTES Framework

This project follows PTES (Penetration Testing Execution Standard), encompassing:
- Pre-Engagement
- Information Gathering
- Threat Modeling
- Vulnerability Analysis
- Exploitation
- Post-Exploitation
- Reporting

## 📖 Learning Outcomes

- Ethical hacking using Medusa & Kali Linux
- Cryptographic key generation and SSH hardening
- Real-world incident analysis
- Penetration testing methodology (PTES)
- Technical documentation

---

> ⚠️ **Disclaimer**: This project is conducted solely in a lab environment. All attacks and tests were done under ethical conditions with no harm to real systems or data.

---

## 📁 Repository Structure

```
📂 brute-force-ssh-demo/
├── README.md
├── demo-scripts/
│   └── medusa-demo.sh
├── screenshots/
│   └── *.png
└── mitigation-configs/
    ├── pam_tally2.conf
    ├── sshd_config
    └── fail2ban_jail.local
```

## 🧑‍💻 Author

**Dirghayu Pradhanang**  
Cybersecurity Enthusiast | Ethical Hacker | Linux Tinkerer  
[LinkedIn Profile](https://www.linkedin.com/in/dirghayu-pradhanang/) 
[GitHub Portfolio](https://github.com/Drgauz) 
