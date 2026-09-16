# ☸️ Multi-Tier Java Web Application Deployment on Kubernetes

## 📌 Project Overview

This project demonstrates the end-to-end orchestration and deployment of a scalable, fault-tolerant, **Multi-Tier Java Web Application** onto a **Kubernetes Cluster**.

It covers the complete infrastructure setup using declarative YAML manifests, establishing internal and external network communication, implementing persistent storage, managing sensitive credentials, and executing zero-downtime **Rolling Updates**.

<img width="1024" height="514" alt="image" src="https://github.com/user-attachments/assets/0e288308-70ec-446d-b841-d7fd032733e5" />

---
[![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)](https://kubernetes.io/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)](https://www.nginx.com/)
[![Apache Tomcat](https://img.shields.io/badge/Apache%20Tomcat-F8DC75?style=for-the-badge&logo=apache-tomcat&logoColor=black)](https://tomcat.apache.org/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge&logo=yaml&logoColor=white)](https://yaml.org/)



---

## 🛠️ Tools & Technologies Used

* **Orchestration:** Kubernetes (k8s)
* **Command Line Interface:** `kubectl`
* **Configuration:** Kubernetes Declarative YAML Manifests
* **Containerization:** Docker
* **Web Server / Reverse Proxy:** Nginx
* **Application Server:** Apache Tomcat (Java App)
* **Database Layer:** MySQL / Stateful Backend

---

## 🏗️ Multi-Tier Architecture & Workflow

```text
                                 [ User Traffic ]
                                        │
                                        ▼
                           [ Nginx LoadBalancer / Ingress ]
                                        │
                                        ▼ (Service: ClusterIP / NodePort)
                      ┌───────────────────────────────────┐
                      │   Java Web Application Tier       │
                      │   (Tomcat Deployments / Pods)     │
                      └─────────────────┬─────────────────┘
                                        │
                         ┌──────────────┴──────────────┐
                         ▼                             ▼
              [ K8s Secrets / ConfigMap ]     [ Database Tier (MySQL) ]
              (DB Passwords & Configs)        (StatefulSet + PVC Storage)
