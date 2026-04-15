# Three-Tier-Deployment-of-a-Netflix-Clone
Used a manually provisioned three-tier architecture to deploy a full-stack Netflix clone over three AWS EC2 instances. Every layer is set up from scratch via SSH; there are no containers or managed services.

# 🎬 Movie-Gold: Full-Stack Hybrid Cloud Deployment

An end-to-end movie application demonstrating a professional manual deployment strategy across a hybrid cloud environment. This project integrates a **React** frontend and a **Spring Boot** backend, hosted on separate **AWS EC2** instances with a **MongoDB Atlas** cloud database.

## 🏗️ Architecture & Infrastructure
This project was deployed manually to simulate a production-grade DevOps environment, moving away from local development to a distributed cloud architecture.

* **Frontend Tier:** React.js application served via `serve` on an Ubuntu AWS EC2 instance.
* **Backend Tier:** Spring Boot (Java) REST API hosted on an independent Ubuntu AWS EC2 instance.
* **Database:** MongoDB Atlas (Cloud) cluster for persistent storage of movie metadata and reviews.
* **Process Management:** Background execution managed via `nohup` and Linux process management to ensure service persistence.

## 🚀 Technical Stack
* **Frontend:** React.js, Axios (API Handling), Bootstrap (UI), CSS3.
* **Backend:** Java 17, Spring Boot, Spring Data MongoDB.
* **Database:** MongoDB Atlas.
* **Cloud/DevOps:** AWS (EC2, VPC, Security Groups), Azure DevOps (CI/CD Pipeline), Git/GitHub.

## 🔧 Technical Documentation

### 1. Networking & Security (AWS Security Groups)
To allow communication between the tiers and the public internet, the following Inbound Rules were configured:

| Server | Port | Protocol | Purpose |
| :--- | :--- | :--- | :--- |
| **Frontend** | 3000 | TCP | React Production Build Access |
| **Backend** | 8080 | TCP | Spring Boot API Endpoint |
| **Both** | 22 | TCP | SSH Management |

### 2. Backend Configuration
The Spring Boot application was configured for production readiness:
* **Environment Variables:** Managed via `.env` file for secure MongoDB URI and Database credentials.
* **CORS Management:** Implemented `@CrossOrigin` annotations to allow secure requests from the Frontend IP.
* **Database Migration:** Successfully migrated and renamed collections via `mongosh` to match application schemas.

### 3. Frontend Deployment
* **Production Build:** Compiled using `npm run build` to create a minified, optimized deployment package.
* **Static Hosting:** Served the production build using the `serve` library on port 3000.
* **API Configuration:** Dynamically updated `axiosConfig.js` to route traffic to the Backend Elastic IP.

## 📋 Key Achievements
* **Manual Cloud Orchestration:** Successfully configured Virtual Machines, Networking, and Firewalls manually to understand the underlying infrastructure.
* **Cross-Origin Resolution:** Diagnosed and resolved CORS policy issues between distributed servers.
* **Database Integrity:** Managed remote MongoDB Atlas clusters, including namespace corrections and data imports.
* **Deployment Persistence:** Implemented background processes to maintain application uptime without active terminal sessions.

**Repositories**

Frontend--https://github.com/Lablezzon/netflix_frontend.git

Backend--https://github.com/Lablezzon/netflix_backend2.git


## 🖥️ Preview

My Instances
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f8193d7c-2c4c-4c9c-99bf-69bdd23d0026" />


**The UI Dashboard:**
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/5b6ecdef-71f9-4e01-a13d-cf3c42df7d73" />




## ✍️ Author
Blessing Taiwo

*GIS Analyst | Cloud & DevOps Engineer | Software Developer*

Ado Ekiti, Nigeria

LinkedIn Profile: https://www.linkedin.com/in/blessing-umanu-taiwo-mgeoson-21a23b78/ | Portfolio: https://github.com/Lablezzon
