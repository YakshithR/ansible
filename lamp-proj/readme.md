3-Tier LAMP Stack Automation
📌 Project Overview
This project demonstrates a fully automated, distributed web application architecture. I transformed a static "Travel Agency" landing page into a dynamic, database-driven application using Ansible for configuration management and PHP/MySQL for the backend logic.

🏗️ The Architecture
The infrastructure consists of two AWS EC2 instances communicating over a Private Network:

Web Server (docker-practice): Runs Apache and PHP to handle user requests.

Database Server (instance-for-practice): Runs MySQL to store destination data (e.g., Tokyo).

Control Node (ansible-practice): The "Brain" that manages both servers using Ansible.

🛠️ Technologies Used
Automation: Ansible (Roles, Playbooks, Ad-hoc commands)

Web Server: Apache2

Backend: PHP 8.x

Database: MySQL 8.0

Cloud: AWS (EC2, Security Groups, VPC)

Version Control: Git

🚀 Key Implementation Steps
1. Infrastructure Automation
I used Ansible Playbooks to install the LAMP stack across multiple nodes simultaneously. This included:

Updating system caches and installing dependencies.

Configuring Apache and PHP on the Web Node.

Setting up MySQL and securing the root user on the DB Node.

2. Solving Real-World Conflicts
During the project, I successfully resolved a Port 80 conflict where a previous Nginx installation was blocking the new Apache service.

Solution: Used systemctl to stop Nginx and Ansible file module with state: absent to clean up residual configuration files.

3. Cross-Node Database Connectivity
I configured a secure "Access Key" system where the Database Node only accepts connections from the Web Node's Private IP.

Command used: CREATE USER 'yakshith'@'WEB_PRIVATE_IP' IDENTIFIED BY 'pass123';

Networking: Modified mysqld.cnf to bind to 0.0.0.0, allowing internal AWS traffic on Port 3306.

4. Dynamic Search Feature
I developed a PHP "Chef" script that:

Takes a user's search input (e.g., "Tokyo").

Queries the remote MySQL database.

Fetches destination details and images dynamically.

📊 Results & Validation
Connectivity Test: Verified Port 3306 is open using nc -zv.

Functionality Test: Successfully searched for "Tokyo" and displayed dynamic content via search.php.

Idempotency: The Ansible playbooks can be run multiple times without breaking the environment.

👨‍💻 Author
Yakshith Aspiring DevOps Engineer
