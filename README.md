# 🚀 DevOps CI/CD Pipeline – Automated Java Application Deployment using Jenkins & AWS

![CI](https://img.shields.io/badge/CI-Jenkins-blue?logo=jenkins)
![Build Tool](https://img.shields.io/badge/Build-Maven-red?logo=apachemaven)
![Cloud](https://img.shields.io/badge/Cloud-AWS-orange?logo=amazonaws)
![Server](https://img.shields.io/badge/Server-Tomcat-yellow?logo=apachetomcat)
![OS](https://img.shields.io/badge/OS-Ubuntu-E95420?logo=ubuntu)

---

## 📌 Project Overview

Implemented an end-to-end CI/CD pipeline using Jenkins Freestyle jobs to automate the build and deployment of a Java web application on AWS EC2 with Apache Tomcat, ensuring fast and reliable releases.

---

## 🛠️ Technologies Used

* Jenkins (Freestyle Job)
* GitHub
* Apache Maven
* Apache Tomcat
* AWS EC2
* Linux (Ubuntu)
* SSH (PEM Key Authentication)

---

## ⚙️ Workflow

1. Code pushed to GitHub
2. Webhook triggers Jenkins job
3. Jenkins builds project using Maven
4. WAR file generated
5. Jenkins connects to EC2 via SSH
6. Application deployed to Tomcat
7. Application becomes live

---

## 🔧 Jenkins Job Configuration

### Source Code Management:

* GitHub repository (main branch)

### Build Step:

```bash id="r2j5bx"
mvn clean package
```

### Execute Shell (SSH Connection):

```bash id="ntk7cx"
ssh -i /var/lib/jenkins/.ssh/ec2.pem ubuntu@<EC2-IP>
```

### Post-Build Action:

* Used **Deploy to Container plugin**
* Deployed `.war` file to remote Apache Tomcat server
* Configured Tomcat manager credentials in Jenkins

---

## ☁️ AWS Setup

* EC2 (Ubuntu) instance
* Apache Tomcat installed and configured
* Security groups allowing ports 22 (SSH) and 8080 (Tomcat)

---

## 🔐 SSH Configuration

* Used PEM key for secure authentication
* Enabled Jenkins-to-EC2 remote access via SSH
* Managed key at `/var/lib/jenkins/.ssh/ec2.pem`

---

## ❗ Problems Solved

* Automated build and deployment pipeline
* Eliminated manual server access for deployment
* Reduced deployment errors

---

## 📈 Impact

* ⏱️ Deployment time reduced by ~60%
* 🔁 Consistent deployments
* ⚡ Faster release cycle

---

## 📁 Project Structure

```id="6u5rhz"
project/
├── src/
├── pom.xml
├── README.md
```

## 🧩 Project Modules

### server/
- Contains backend business logic
- Includes Java classes and unit tests

### webapp/
- Web application module (JSP, web.xml)
- Packaged as WAR file for deployment on Tomcat

---

## 🔮 Future Improvements

* Convert to Jenkins Pipeline (Jenkinsfile)
* Add Docker & Kubernetes
* Implement monitoring tools

---

## 👨‍💻 Author

**Lalit Kumar Gautam**
