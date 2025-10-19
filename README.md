# <img width="80" height="80" alt="image" src="https://github.com/user-attachments/assets/1d67d697-03bf-466c-a71c-e118e5fd2614" /> Module 15 – Configuration Management with Ansible.

This exercise is part of Module 15 from the TWN DevOps Bootcamp. In Module 15, we focus on automating server setup and application deployment using Ansible. You learn how to configure servers, deploy Node.js and Nexus, integrate with Terraform and Jenkins, manage Docker containers, and organize playbooks with roles. Each demo builds practical automation skills for real-world DevOps environments.

---
<a id="demo7"></a>
# 📦Demo 8 – Structure Playbooks with Ansible Roles
# 📌 Objective
Refactor large Ansible playbooks into smaller, reusable roles to improve maintainability.

# 🚀 Technologies Used
* Ansible: Configuration management tool for automation.
* AWS: Cloud provider.
* Linux: OS.

# 🎯 Features
  ✅ Organizes tasks into roles for clarity and reuse.<br>
  📁 Encourages modular playbook design.<br>
  ⚙️ Simplifies complex server setups<br>
  

# Prerequisites
* AWS account with valid keys.
* For Ansible controller node:
  * python >=3.6
  * boto3 >= 1.26.0
  * botocore >= 1.29.0
* Demo from Dynamic Inventory

  

# 🏗 Project Architecture
<img src=""/>



# ⚙️ Project Configuration
## Refactor the Linux User and Start Container Plays
1. Reuse the deploy-docker-user.yaml file from the previous Ansible demo.
   <img src="" width=800 />
   
2. Create a directory named roles to organize your refactored plays.
   <img src="" width=800 />
   
3. Create a subdirectory for each play you want to refactor, for example: create_user and start_container.
   <img src="" width=800 />
   
4. In each subdirectory, create a main.yaml file to define the play’s tasks.
   <img src="" width=800 />
   
5. Copy the relevant tasks from deploy-docker-user.yaml and paste them into each main.yaml file.
    <img src="" width=800 />
    
6. Deploy the infrastructure using the Terraform files from demo1.
    <img src="" width=800 />
    ```
      terraform init
      terraform plan
      terraform apply --auto-approve
    ```
    
7. Run the Ansible playbook to apply the configuration.
    <img src="" width=800 />
    ```bash
    ansible-playbook ansible-docker-user-with-roles.yaml
    ```
    
8. Connect to each instance via SSH and verify that Docker is running.
    <img src="" width=800 />
    ```
    ssh -i your_key.pem ec2-user@ipaddress.com
    ```
    
9. Create a files directory for static files. Instead of referencing absolute paths, copy the necessary files into this folder and update the playbook to reference them locally.
    <img src="" width=800 />
    
10. Apply the changes to validate the new structure.
    ```
    ansible-playbook ansible-docker-user-with-roles.yaml
    <img src="" width=800 />
    
11. Add a defaults directory inside each role to define variable default values and improve maintainability.
    <img src="" width=800 />
