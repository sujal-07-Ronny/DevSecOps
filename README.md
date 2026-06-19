# DevSecOps Security Scanning Project

## Overview

This project demonstrates the integration of security and code quality checks into a CI/CD pipeline using Trivy and SonarQube.

The objective was to identify vulnerabilities in container images and improve code quality through automated scanning.

---

## Tools Used

- Trivy
- SonarQube
- Docker
- Jenkins CI/CD

---

## Project Components

### Trivy

Implemented vulnerability scanning for container images.

Features:
- Container image scanning
- Vulnerability detection
- Security report generation

---

### SonarQube

Implemented automated code quality analysis.

Features:
- Static code analysis
- Code smell detection
- Bug detection
- Quality gate validation

---

## DevSecOps Workflow

Developer Code
↓
GitLab CI/CD Pipeline
↓
SonarQube Code Analysis
↓
Trivy Security Scan
↓
Security & Quality Reports

---

## Key Learnings

- Shift-left security approach
- Automated vulnerability scanning
- Static code analysis
- Security integration in CI/CD
- DevSecOps best practices

---

## Screenshots

### Trivy Scan Results

![Trivy](Trivy/screenshots/trivy.png)

### SonarQube Dashboard

![SonarQube](SonarQube/screenshots/sonarqube.png)

### Pipeline Execution

![Pipeline](screenshots/pipeline.png)
