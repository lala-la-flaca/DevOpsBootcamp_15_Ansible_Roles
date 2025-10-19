# <img width="80" height="80" alt="image" src="https://github.com/user-attachments/assets/1d67d697-03bf-466c-a71c-e118e5fd2614" /> Module 15 – Configuration Management with Ansible.

This exercise is part of Module 15 from the TWN DevOps Bootcamp. In Module 15, we focus on automating server setup and application deployment using Ansible. You learn how to configure servers, deploy Node.js and Nexus, integrate with Terraform and Jenkins, manage Docker containers, and organize playbooks with roles. Each demo builds practical automation skills for real-world DevOps environments.

---
<a id="demo7"></a>
# 📦Demo 8 – Ansible Roles
# 📌 Objective
Integrate Ansible execution into a Jenkins pipeline to automate the configuration of multiple EC2.

Files available in branch: feature/ansible 
[Ansible_Demo7_Files](https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Jenkins_AWS/tree/feature/ansible)

# 🚀 Technologies Used
* Ansible: Configuration management tool for automation.
* AWS: Cloud provider.
* Linux: OS.
* DigitalOcean: Cloud provider

# 🎯 Features
  ✅ Jenkins triggers remote Ansible playbooks.<br>
  🧩 Configures multiple servers from a single pipeline.<br>
  

# Prerequisites
* AWS account with valid keys.
* For Ansible controller node:
  * python >=3.6
  * boto3 >= 1.26.0
  * botocore >= 1.29.0
* Python modules require these dependencies to execute the K8 module:
  * python >= 3.6
  * kubernetes >= 12.0.0
  * PyYAML >= 3.11
  * jsonpatch
* DigitalOcean account.
* Demo from Dynamic Inventory
* Jenkins server from module 8.
  

# 🏗 Project Architecture
<img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Jenkins_AWS/blob/main/Img/Demo15-Jenkins.drawio.png" width=800 />



# ⚙️ Project Configuration

