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
   <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/1%20create%20roles%20directory%20and%20subfolder%20for%20each%20role.png" width=800 />
   
2. Create a directory named roles to organize your refactored plays.
   
3. Create a subdirectory for each play you want to refactor, for example: create_user and start_container.
   
4. In each subdirectory, create a main.yaml file to define the play’s tasks.
   
   <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/2%20create%20tasks%20subdirectory%20inside%20each%20role%20folder%20and%20the%20main%20file.png" width=800 />
   
5. Copy the relevant tasks from deploy-docker-user.yaml and paste them into each main.yaml file.
   
    <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/3%20copy%20the%20task%20section%20of%20each%20play%20in%20each%20main%20file.PNG" width=800 />
    
6. Deploy the infrastructure using the Terraform files from demo1.
    ```
      terraform init
      terraform plan
      terraform apply --auto-approve
    ```
    <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/8%20ssh%20to%20ec2%20and%20check%20containers.png" width=800 />
    
7. Verify AWS infrastructure

   <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/6%20aws%20console%20ec2s.png" width=800/>    
    
8. Run the Ansible playbook to apply the configuration.
    ```bash
    ansible-playbook ansible-docker-user-with-roles.yaml
    ```
    <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/7%20runnin%20gplaybook.png" width=800 />
    
09. Connect to each instance via SSH and verify that Docker is running.
    ```
    ssh -i your_key.pem ec2-user@ipaddress.com
    ```
    <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/8%20ssh%20to%20ec2%20and%20check%20containers.png" width=800 />
    
10. Create a files directory for static files. Instead of referencing absolute paths, copy the necessary files into this folder and update the playbook to reference them locally.

    <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/9%20files%20directory%20for%20static%20files.png" width=800 />
    
11. Apply the changes to validate the new structure.
    ```
    ansible-playbook ansible-docker-user-with-roles.yaml
    ```
    <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/10%20ansible%20ok%20afetr%20using%20static%20files.PNG" width=800 />
    
12. Add a defaults directory inside each role to define variable default values and improve maintainability.
    <img src="https://github.com/lala-la-flaca/DevOpsBootcamp_15_Ansible_Roles/blob/main/Img/11%20defaults%20folder.png" width=800 />
