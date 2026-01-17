# secure-wordpress-aws

# Secure WordPress Deployment on AWS (EC2 + LAMP)

This project demonstrates the secure deployment of a WordPress website on AWS EC2 with a strong focus on **system hardening, application security, monitoring, and resilience**.  
The environment was built and secured following industry best practices (NIST CSF, OWASP Top 10, ISO 27001).

The goal was to create a **realistic, production-style deployment** while working within AWS Academy constraints.

---

## 🧱 Architecture Overview

- Cloud Platform: AWS EC2 (t2.micro)
- OS: Amazon Linux 2023
- Web Stack: LAMP (Linux, Apache, MariaDB, PHP)
- Application: WordPress
- Domain: DuckDNS + Elastic IP
- Encryption: Let’s Encrypt SSL/TLS
- Monitoring: Datadog, AWS GuardDuty

---

## 🔧 Project Workflow

1. EC2 instance provisioning
2. LAMP stack installation
3. WordPress deployment
4. Network and domain configuration
5. Security hardening (system + application)
6. Monitoring and logging
7. Backup and recovery testing
8. Documentation and validation

---

## ☁️ EC2 Setup & Network Security

- Launched Amazon Linux 2023 EC2 instance (t2.micro)
- Configured **key-based SSH authentication** (RSA)
- Security group restricted to:
  - 22 (SSH)
  - 80 (HTTP)
  - 443 (HTTPS)
- All unnecessary ports blocked
- Public + private IP assigned
- Elastic IP attached for stable access

---

## 🧰 LAMP Stack Installation

- **Apache** configured to host WordPress
- **MariaDB** configured with dedicated database and user
- **PHP** enabled for dynamic content
- Installed via SSH terminal
- Verified via Apache test page and phpinfo()

---

## 📝 WordPress Deployment

- Created database `wordpress_db` and user
- Configured `wp-config.php`
- Corrected file permissions
- Verified admin panel access and functionality
- Plugins installed and tested

---

## 🔐 HTTPS & Encryption

- DuckDNS domain mapped to Elastic IP
- Certbot + Let’s Encrypt used for SSL/TLS
- Apache configured with automatic HTTP → HTTPS redirect
- Certificate renewal automated
- Verified with browser padlock and curl checks

---

## 🛡️ Security Hardening

### System Level
- Key-only SSH authentication
- Firewall restricted to essential services
- Password authentication disabled

### Web & Application Level
- Wordfence WAF installed
- Brute-force protection enabled
- MFA enforced for admin users
- Directory listing disabled
- Unused plugins removed

---

## 💾 Backup & Recovery

- UpdraftPlus configured for scheduled backups
- Manual backup testing performed
- Full restore options validated
- Supports business continuity & disaster recovery (BC/DR)

---

## 📊 Monitoring & Detection

- Datadog agent installed on EC2
- Real-time metrics:
  - CPU
  - Memory
  - Disk
  - Network
  - Apache performance
- AWS GuardDuty enabled for threat detection
- Logs and metrics validated in dashboard

---

## 🔍 Vulnerability Testing

- Nessus vulnerability scan performed
- Results reviewed and remediated where possible
- Baseline security posture validated post-hardening

---

## 📚 Frameworks & Best Practices Used

- **NIST Cybersecurity Framework** (Identify, Protect, Detect, Respond, Recover)
- **OWASP Top 10** (Authentication, Access Control, Transport Security)
- **ISO/IEC 27001** (Access control, logging, backup)
- **UN SDGs** (efficient resource usage, open-source tooling)

---

## 🧠 What I Learned

- Secure cloud deployment requires layered security (system, network, app)
- Monitoring is as important as prevention
- Hardening must be tested, not assumed
- Documentation is critical for reproducibility
- Cloud security is a blend of architecture + operations

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|--------|
| AWS EC2 | Cloud infrastructure |
| Apache | Web server |
| MariaDB | Database |
| PHP | Application runtime |
| Wordfence | WAF + MFA |
| Fail2Ban | Host-based intrusion prevention |
| Certbot / Let’s Encrypt | HTTPS encryption |
| DuckDNS | Domain mapping |
| Datadog | Monitoring & logging |
| AWS GuardDuty | Threat detection |
| Nessus | Vulnerability scanning |
| UpdraftPlus | Backup & recovery |

---

## ⚠️ Notes & Limitations

- Deployed within AWS Academy environment
- Free-tier resource constraints applied
- Intended for educational and demonstration purposes
