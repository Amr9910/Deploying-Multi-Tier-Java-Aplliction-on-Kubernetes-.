# 🚀 End-to-End-CI-CD-Pipeline-for-Java-Applications-using-Jenkins-Docker

[![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=Jenkins&logoColor=white)](https://www.jenkins.io/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)](https://www.java.com/)
[![Maven](https://img.shields.io/badge/Apache%20Maven-C71A36?style=for-the-badge&logo=Apache%20Maven&logoColor=white)](https://maven.apache.org/)
[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/)

---

## 📌 Project Overview

This project focuses on building an automated **End-to-End CI/CD Pipeline** using **Jenkins**. It automates the entire software delivery lifecycle for a Java-based application—from source code integration and compilation to automated unit testing, containerization, and deployment.

---

## 🛠️ Tools & Technologies Used

* **Automation Server:** Jenkins
* **Version Control System:** Git & GitHub
* **Build Automation:** Apache Maven
* **Containerization:** Docker
* **Application Server:** Apache Tomcat
* **Programming Language:** Java

---

## 🎯 Purpose & Objectives

The primary goal of this project is to gain practical, hands-on experience in automating software build, test, and deployment workflows using Jenkins, eliminating manual deployment errors, and achieving continuous delivery.

---

## 🧠 Key Learnings & Skills Acquired

* **Jenkins Pipeline Configuration:** Designing declarative pipelines (`Jenkinsfile`) to structure multi-stage CI/CD workflows.
* **Build & Test Automation:** Triggering automated Java builds and executing test suites using Maven.
* **Tool Integration:** Connecting Git, Maven, Docker, and deployment environments into a single pipeline.
* **Containerized Deployment:** Packaging Java artifacts into Docker images and deploying containers to Tomcat servers.

---

## 📋 Prerequisites

To replicate or understand this project implementation, the following background knowledge is recommended:
* Basic understanding of DevOps principles and CI/CD concepts.
* Familiarity with Jenkins dashboard and job configurations.
* Fundamental knowledge of Java application architecture.
* Hands-on experience with Git version control commands.

---

## 🔄 CI/CD Pipeline Workflow

```text
[ Git / GitHub ] ──(Trigger)──> [ Jenkins Pipeline ]
                                       │
                                       ├──> 1. Checkout Source Code
                                       ├──> 2. Build & Test (Maven)
                                       ├──> 3. Package WAR Artifact
                                       ├──> 4. Build Docker Image
                                       └──> 5. Deploy to Tomcat Container
