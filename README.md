# 🔐 Automated Secure Software Delivery Pipeline | Jenkins + SonarQube + Trivy + Docker

![Jenkins](https://img.shields.io/badge/CI%2FCD-Jenkins-red?logo=jenkins)
![SonarQube](https://img.shields.io/badge/Code%20Quality-SonarQube-blue?logo=sonarqube)
![Trivy](https://img.shields.io/badge/Security-Trivy-critical?logo=aqua)
![Docker](https://img.shields.io/badge/Container-Docker-blue?logo=docker)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Overview

A fully automated **DevSecOps CI/CD pipeline** built with Jenkins that integrates **SonarQube** for static code analysis and **Trivy** for container image vulnerability scanning — with security gates that **block builds** when HIGH or CRITICAL vulnerabilities are detected.

> ⚠️ Infrastructure is torn down to avoid costs. All pipeline configs, Jenkinsfile, and screenshots are preserved in this repo.

---

## 🏗️ Pipeline Architecture

```
Developer pushes code
        ↓
Jenkins CI/CD Pipeline triggers
        ↓
SonarQube — Static Code Analysis
(Code smells, bugs, vulnerabilities)
        ↓
Docker Image Build
        ↓
Trivy — Container Image Scan
(HIGH & CRITICAL vulnerability check)
        ↓
🚫 Security Gate: HIGH/CRITICAL found? → Pipeline FAILS
✅ Security Gate: Clean? → Image Delivered
```

---

## ⚙️ Tech Stack

| Category | Tools |
|---|---|
| CI/CD | Jenkins |
| Code Quality & SAST | SonarQube |
| Container Security | Trivy |
| Containerization | Docker |
| Version Control | Git |

---

## 🎯 What Was Implemented

- ✅ Built **Jenkins CI/CD pipeline** to automate source code integration and Docker image creation
- ✅ Integrated **SonarQube** for static code analysis — detects bugs, code smells, and security vulnerabilities
- ✅ Implemented **Trivy image scanning** to detect HIGH and CRITICAL vulnerabilities before delivery
- ✅ Enforced **security gates** — pipeline blocked automatically when HIGH/CRITICAL issues found
- ✅ Demonstrated both **pipeline failure** (vulnerabilities detected) and **pipeline success** (clean image) scenarios

---

## 📸 Project Screenshots

### 🔴 Trivy — Pipeline Failed (HIGH/CRITICAL Vulnerabilities Detected)
![Failed Pipeline](Trivy/OutPut/Failed%20Pipeline.png)

### 🛡️ Trivy — Security Gate Blocking Build
![Security Gate](Trivy/OutPut/Security%20Gate.png)

### 📋 Trivy — Vulnerability Report
![Trivy Report](Trivy/OutPut/Report.png)

### 📊 Trivy — Vulnerability Table
![Table of Vulnerabilities](Trivy/OutPut/Table%20of%20vul.png)

### ✅ SonarQube — Pipeline Success
![Success Pipeline](SonarQube/OutPut/success%20pipeline.png)

### 📈 SonarQube — Dashboard
![SonarQube Dashboard](SonarQube/OutPut/Dashboard.png)

### 📝 SonarQube — Success Logs
![Success Logs](SonarQube/OutPut/Success%20logs.png)

---

## 📂 Repository Structure

```
DevSecOps/
├── Trivy/
│   └── OutPut/
│       ├── Failed Pipeline.png
│       ├── Report.png
│       ├── Security Gate.png
│       └── Table of vul.png
├── SonarQube/
│   └── OutPut/
│       ├── Dashboard.png
│       ├── Success logs.png
│       └── success pipeline.png
└── README.md
```

---

## 🧠 Challenges Faced & Solved

| Challenge | Solution |
|---|---|
| SonarQube not connecting to Jenkins | Configured SonarQube token in Jenkins credentials manager |
| Trivy not blocking pipeline on HIGH findings | Added `--exit-code 1` flag to Trivy scan command |
| Docker build failing inside Jenkins | Fixed by adding Jenkins user to docker group |

---

## 🔁 How to Reproduce

```bash
# 1. Start Jenkins and SonarQube (Docker)
docker run -d -p 8080:8080 jenkins/jenkins:lts
docker run -d -p 9000:9000 sonarqube:community

# 2. Install Jenkins plugins
# - SonarQube Scanner
# - Docker Pipeline

# 3. Configure SonarQube token in Jenkins credentials

# 4. Create Jenkins pipeline and add Jenkinsfile

# 5. Trivy scan in pipeline stage
trivy image --exit-code 1 --severity HIGH,CRITICAL your-image:tag

# 6. Push code → Pipeline triggers automatically
```

---

## 💡 Key DevSecOps Concepts Demonstrated

- **Shift-Left Security** — security checks happen early in pipeline, not after deployment
- **Security as Code** — vulnerability thresholds enforced automatically, no manual checks
- **Quality Gates** — code cannot proceed if it fails SonarQube or Trivy standards
- **Fail Fast** — pipeline stops immediately on HIGH/CRITICAL findings, saving time and cost

---

## 👨‍💻 Author

**Sujal Shaha** | [LinkedIn Profile](https://www.linkedin.com/in/sujal-shaha-15832b286/) | [GitHub](https://github.com/sujal-07-Ronny)

🏅 AWS Certified Cloud Practitioner (CLF-C02)
