# AWS Hosted Password Management System

A secure, self-hosted deployment of **Passbolt** running on AWS. This project demonstrates deploying an open-source password manager to the cloud with HTTPS, domain hosting, and secure storage of complex passwords.

---

## Table of Contents

* [Features](#features)


* [Technologies & AWS Services](#technologies--aws-services)

* [Screenshots](#screenshots)

* [Getting Started](#getting-started)

  * [Prerequisites](#prerequisites)
  * [Quick Deploy (summary)](#quick-deploy-summary)

* [Security Considerations](#security-considerations)


* [Testing & Validation](#testing--validation)


---


Key goals:

* Securely host Passbolt in AWS
* Ensure HTTPS/TLS for all traffic
* Provide guidelines for scalability and availability

---

## Features

* Self-hosted Passbolt instance
* HTTPS/TLS encryption for all web traffic
* Secure storage of complex passwords and secrets
* Recommended AWS architecture for reliability and scalability

---


Add an architecture diagram image here: `assets/arch-diagram.png`.

---

## Technologies & AWS Services

* **Passbolt** (Community Edition)
* **EC2** — compute for Passbolt application
* **AWS Certificate Manager (ACM)** or **Let's Encrypt** — SSL/TLS certs
* **Security Groups** — firewall rules
* **IAM** — least-privilege roles for backups and automation

---

## Screenshots

Screenshots of the deployed Passbolt instance are included in the directory. 

* `img5.jpg`
* `img9.jpg`
* `img12.jpg`
* `img15.jpg`
* `img18.jpg`
* `img21.jpg`
* `img24.jpg`
* `img25.jpg`
* `img28.jpg`
* `img31.jpg`
* `img34.jpg`
* `img37.jpg`
* `img40.jpg`
---

## Getting Started

### Prerequisites

* AWS account with administrative privileges to provision EC2
* Linux

### Quick Deploy (summary)

2. Provision an EC2 instance (Ubuntu 22.04 LTS recommended).
3. Install prerequisites (nginx, php-fpm, composer, git, php extensions required by Passbolt).
4. Clone Passbolt and configure `app.php` with DB and domain settings.
5. Configure HTTPS using ACM (ALB) or Let's Encrypt with Certbot + nginx.


### Manual Deployment Steps (detailed)


1. **Provision EC2 for Passbolt**

   * Instance: t3.small or larger depending on load
   * OS: Ubuntu 22.04 LTS
   * Security Group: allow inbound 80/443 from ALB; SSH from your IP


2. **Install Passbolt**

   * Clone repo: `git clone https://github.com/passbolt/passbolt_api.git` (or use official install instructions)
   * Run composer install and configure `config/app.php` or `config/passbolt.php` with DB credentials
   * Generate GPG keys and configure them for Passbolt users


3. **Monitoring & Logging**

   * Monitor EC2 metrics and set alarms

---

## Security Considerations

* Use HTTPS for all traffic. 
* Protect GPG private keys — store them encrypted and restrict access.
* Use security groups to limit inbound access; allow SSH only from trusted IPs.
* Regularly rotate credentials and audit access logs

---

## Testing & Validation

* Verify HTTPS (Cert validity) and redirect HTTP -> HTTPS
* Test a user login and password retrieval flow
* Run security scans and dependency checks

---

