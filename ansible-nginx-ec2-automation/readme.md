# 🚀 Ansible Nginx Automation on EC2

## 📌 Project Overview
This project automates the installation and configuration of Nginx on an AWS EC2 instance using Ansible.

## 🛠 Technologies Used
- Ansible
- AWS EC2
- Nginx
- Linux

## 📂 Project Structure
- inventory.ini
- nginx-playbook.yml
- files/index.html

## 🚀 How to Run

1. Update inventory with your EC2 IP and key path
2. Run:
   ansible-playbook nginx-playbook.yml
3. Access:
   http://<http://13.49.73.66:80>

## 🎯 Key Concepts Demonstrated
- Idempotent automation
- SSH-based remote configuration
- Service management
- Infrastructure as Code
