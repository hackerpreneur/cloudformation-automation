# 🚀 AWS CloudFormation Automation Lab

<div style="display: flex; justify-content: center; gap: 15px;">
  <img src="https://github.com/user-attachments/assets/d32023b2-687c-48ed-9dc0-ba7b97b877e4" width="200">
  <img src="https://github.com/user-attachments/assets/63034a5e-1879-4c71-ad4f-1507cc0b6c9a" width="200">
  <img src="https://github.com/user-attachments/assets/307c0840-0e0d-4576-8e0e-e8764bc50304" width="200">
  <img src="https://github.com/user-attachments/assets/bd55efb3-9cb2-4c58-bc08-eb2acfd6a30a" width="200">
</div>

## 📖 Introduction
This project demonstrates **Infrastructure as Code (IaC)** using **AWS CloudFormation**, enabling automated and repeatable AWS infrastructure deployment.

By using **CloudFormation templates**, we eliminate manual AWS setup and ensure **consistency, scalability, and version control** for AWS resources.

> **🔹 Why This Project?**  
> ✅ Automates AWS infrastructure deployment  
> ✅ Uses Infrastructure as Code (IaC) principles  
> ✅ Demonstrates DevOps best practices  

---

## ⚡ Features
✅ **Creates an AWS Virtual Private Cloud (VPC) and Security Group**  
✅ **Adds an Amazon S3 Bucket for storage**  
✅ **Deploys an EC2 instance with networking and security configurations**  
✅ **Manages the full infrastructure lifecycle (Create, Update, Delete)**  

📌 **No manual AWS setup required! Just deploy the CloudFormation stack, and AWS automatically provisions resources.**  

---

## 📂 Project Structure
```
cloudformation-automation-lab/
│── templates/            # CloudFormation YAML files
│   ├── task1.yaml        # Deploys VPC & Security Group
│   ├── task2.yaml        # Adds an S3 Bucket
│   ├── task3.yaml        # Deploys an EC2 Instance
│── README.md             # Project Documentation
```

---

## 🚀 How to Deploy This Project
You can deploy this CloudFormation stack using **AWS CLI** or the **AWS Management Console**.

### **1️⃣ Deploy the CloudFormation Stack (VPC + Security Group)**
```sh
aws cloudformation create-stack --stack-name Lab --template-body file://templates/task1.yaml
```
**What happens?**  
- A **VPC** with a **Public Subnet** and **Internet Gateway** is created.
- A **Security Group** is deployed to allow HTTP (Port 80) access.

---

### **2️⃣ Add an S3 Bucket to the Stack**
```sh
aws cloudformation update-stack --stack-name Lab --template-body file://templates/task2.yaml
```
**What happens?**  
- An **Amazon S3 bucket** is created for storing files and objects.

---

### **3️⃣ Deploy an EC2 Instance**
```sh
aws cloudformation update-stack --stack-name Lab --template-body file://templates/task3.yaml
```
**What happens?**  
- A **t3.micro EC2 instance** is deployed.
- It is placed inside the **Public Subnet** with a **Security Group** attached.
- It uses **Amazon Linux 2 AMI** (fetched dynamically using AWS Systems Manager Parameter Store).

---

### **4️⃣ Clean Up: Delete the Stack**
```sh
aws cloudformation delete-stack --stack-name Lab
```
This removes **all AWS resources** created by the stack to **avoid additional AWS charges**.

---

## 📌 Understanding the CloudFormation Templates
Each CloudFormation template is **modular** and serves a different purpose.

### **📝 `task1.yaml` (VPC & Security Group)**
- **Creates a Virtual Private Cloud (VPC)** with a **Public Subnet**.
- **Attaches an Internet Gateway** for external internet access.
- **Deploys a Security Group** that allows HTTP traffic (port 80).

### **📝 `task2.yaml` (S3 Bucket)**
- **Creates an Amazon S3 bucket** for storage.
- No additional configurations (default settings are applied).

### **📝 `task3.yaml` (EC2 Instance)**
- **Deploys an EC2 instance** inside the Public Subnet.
- Uses **AWS SSM Parameter Store** to dynamically fetch the latest **Amazon Linux 2 AMI**.
- **Assigns a Security Group** to allow HTTP access.

---

## 🔧 Technologies Used
- **AWS CloudFormation** – Infrastructure as Code (IaC)
- **Amazon VPC** – Private cloud networking
- **Amazon EC2** – Cloud virtual machines
- **Amazon S3** – Object storage
- **AWS CLI** – Command-line automation

---

## 💡 Why This Project Stands Out
✅ **Hands-on AWS CloudFormation Experience**  
✅ **Follows DevOps Best Practices** (Infrastructure as Code)  
✅ **Reusable & Scalable Infrastructure**  
✅ **Automated Stack Creation & Management**  

---

## 💡 Future Enhancements
🔹 **Auto Scaling & Load Balancer** – Improve EC2 scalability.  
🔹 **AWS Lambda for Rollbacks** – Automate CloudFormation error handling.  
🔹 **GitHub Actions for CI/CD** – Automate deployments using GitHub workflows.  
🔹 **Terraform Version** – Convert CloudFormation templates into **Terraform**.  

---

