# ☸️ Multi-Tier Java Web Application Deployment on Kubernetes

## 📌 Project Overview 

This project demonstrates the end-to-end orchestration and deployment of a scalable, fault-tolerant, Multi-Tier Java Web Application onto a Kubernetes Cluster.

It covers the complete infrastructure setup using declarative YAML manifests, establishing internal and external network communication, implementing persistent storage, managing sensitive credentials, and executing zero-downtime Rolling Updates.



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


<img width="1897" height="804" alt="AdobeExpressPhotos_cbd6e8a633824b7eb32e1457b096905c_CopyEdited" src="https://github.com/user-attachments/assets/5ee06852-6edd-438b-bec3-324e689d6859" />


* app-secret.yml *
<img width="313" height="220" alt="AdobeExpressPhotos_4999f238c9f044728588b6ed5530df7f_CopyEdited" src="https://github.com/user-attachments/assets/e8da5118-faff-41c7-9908-9f2c8830647d" />


* vproapp-service.yml  *

<img width="427" height="356" alt="AdobeExpressPhotos_0a2cff24096c4d56bf1695a20e2ec0ba_CopyEdited" src="https://github.com/user-attachments/assets/48557d59-1b15-4a87-b5c9-74cdd60aa11f" />


* vproappdep.yml *

<img width="1674" height="789" alt="AdobeExpressPhotos_a4f7e8d227fc4051b4316e876f4ca715_CopyEdited" src="https://github.com/user-attachments/assets/a33b9943-82e0-42d7-aaf0-396ecf94570a" />


* vprodbdep.yml *

<img width="702" height="802" alt="AdobeExpressPhotos_fbbc28b5f6334bc790d1b05e9600e791_CopyEdited" src="https://github.com/user-attachments/assets/27716b7f-d004-495f-bc7c-6ac811678f23" />


* Rabbit MQ Deployment.yml * 
<img width="581" height="811" alt="AdobeExpressPhotos_cef7a643178944229724084217a11b15_CopyEdited" src="https://github.com/user-attachments/assets/68277160-7aef-4ea0-ab3c-32d95b01f04c" />

* RabbitMQ-CIP-service.yml *

<img width="434" height="295" alt="AdobeExpressPhotos_7de5757608e043be852ac8cc5be03ac6_CopyEdited" src="https://github.com/user-attachments/assets/59febc3b-176d-4781-a422-e2ace0ee8794" />


* memcache-deployment.yml *
<img width="565" height="799" alt="AdobeExpressPhotos_571d4455f3f64573a8fb45d152540650_CopyEdited" src="https://github.com/user-attachments/assets/144dc426-9e5e-4d5a-abc4-7a3fd97c93e2" />


* memcahe-clusterip.yml *

<img width="488" height="802" alt="AdobeExpressPhotos_bc9a823f0ff646d9bdc71957bacce596_CopyEdited" src="https://github.com/user-attachments/assets/692fec3f-a25e-4f79-9006-944c7d6af595" />


* DB-Cluster-IP.yml *
<img width="417" height="385" alt="AdobeExpressPhotos_1104aeb20e1c4588904cc6d5e62811cd_CopyEdited" src="https://github.com/user-attachments/assets/65e86e9f-5fc5-4e4b-95d3-97b1f4fe7022" />


* 1- Make directory and put all YAML file
  2- Run this Yaml file

<img width="1883" height="485" alt="AdobeExpressPhotos_4797db18ef694b3e99083e42aaa9c8e2_CopyEdited" src="https://github.com/user-attachments/assets/c755d41d-f1dd-4608-a63e-316d4fac3649" />



<img width="1129" height="433" alt="AdobeExpressPhotos_928727f07034488e9fd2a42dedb97523_CopyEdited" src="https://github.com/user-attachments/assets/bcd58004-e6b8-444b-aa28-1197c985d6ca" />


* Final Take copy of the port "Load Balancer Services" To Access App

<img width="1905" height="854" alt="AdobeExpressPhotos_d4e2a67768f149cd97a41421b4b1a67c_CopyEdited" src="https://github.com/user-attachments/assets/8b1536f3-359e-4426-ac60-fd6ca75eceae" />


<img width="1888" height="863" alt="AdobeExpressPhotos_483c471b236c4f78ac799f8ba15d3829_CopyEdited" src="https://github.com/user-attachments/assets/1d5b5274-f1a4-450d-a1cd-4fb981d427bc" />





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








