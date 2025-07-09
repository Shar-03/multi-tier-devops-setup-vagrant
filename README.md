# Vprofile

## 📘 Description
This project sets up a multi-VM DevOps environment using **Vagrant** and **Shell provisioning**. Each virtual machine is configured to run one component of a multi-tier web application stack. The goal is to simulate a real-world microservice deployment pipeline, automated from scratch.

## 🏗️ Architecture Overview
[Client] --> [Nginx] --> [Tomcat (App)] --> [MySQL | Memcache | RabbitMQ]


Each component is installed on a dedicated VM to represent modular microservice-like isolation.

## 📦 Stack & Services

| Component   | VM Role         | Provisioning Script      |
|-------------|------------------|---------------------------|
| Backend App | `tomcat`         | `tomcat.sh`, `tomcat_ubuntu.sh` |
| Database    | `mysql`          | `mysql.sh`                |
| Cache       | `memcached`      | `memcache.sh`             |
| Queue       | `rabbitmq`       | `rabbitmq.sh`             |
| Load Balancer | `nginx`        | `nginx.sh`                |
| Master/Orchestrator | (optional) | `backend.sh`             |

## 📁 Folder Structure

multi-tier-devops-setup-vagrant/
├── Vagrantfile
├── provisioning/
│ ├── backend.sh
│ ├── memcache.sh
│ ├── mysql.sh
│ ├── nginx.sh
│ ├── rabbitmq.sh
│ ├── tomcat.sh
│ └── tomcat_ubuntu.sh
└── README.md


## 🚀 How to Use

### 🔧 Prerequisites
- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

### 🧪 Spin up the stack
```bash
vagrant up

### 💻 SSH into a specific VM
vagrant ssh <vm-name>
Replace <vm-name> with the name defined in your Vagrantfile.

### 🔁 Re-provision a VM (after editing a script)
vagrant provision <vm-name>

### ✅ Status
🛠️ In Progress
✅ Manual setup and basic provisioning complete

### 📌 Notes
Built as part of a DevOps course project (Section 8 of [Udemy: DevOps Beginner to Advanced])
Useful for simulating multi-tier deployments on local VMs
Good foundation to practice CI/CD, monitoring, infrastructure automation
