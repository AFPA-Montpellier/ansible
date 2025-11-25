# 🧩 Ansible LEMP Multi-Node Infrastructure (TP1–TP3)

This repository contains a complete series of Ansible training projects (TP1, TP2, TP3) built on a real multi-VM environment.  
It progresses from simple ad-hoc commands → to playbooks → to a fully structured role-based automation system.

This project follows professional Infrastructure-as-Code patterns and can be used as a DevOps portfolio reference.

---

## 🚀 Project Overview

The infrastructure is composed of three Debian-based virtual machines:

| Role | Hostname | IP Address | SSH Port |
|------|----------|------------|----------|
| Control Node | controllerNode | N/A | N/A |
| Database Server | dbserver | 172.20.100.107 | 22107 |
| Web Server | webserver | 172.20.100.108 | 22108 |

The final outcome includes automated deployment of:

- ✔️ MariaDB server and secure DB provisioning  
- ✔️ UFW firewall hardening on both nodes  
- ✔️ NGINX + PHP-FPM installation  
- ✔️ WordPress deployment and configuration  
- ✔️ Jinja2 templated `wp-config.php`  
- ✔️ Full multi-role orchestration via Ansible roles  

---

## 🏗️ TP1 — Introduction to Ansible

### Objectives  
- Understand the concept of Control Node and Managed Nodes  
- Configure SSH key-based access  
- Build the first inventory file  
- Run ad-hoc Ansible commands  
- Create first simple playbooks:
  - `ping.yml`
  - `system_update.yml`

### Skills learned  
- Ansible modules (`apt`, `service`, `ping`, `command`)  
- Inventory basics  
- YAML & playbook syntax  
- Becoming comfortable with idempotency  

---

## 🏗️ TP2 — Multi-Node LEMP & WordPress Deployment

This TP introduces real multi-node automation.

### DB Server tasks
- Install MariaDB & required Python modules  
- Create the WordPress database  
- Create a dedicated DB user  
- Restrict DB access using UFW (only allow 3306 from Web server)  
- Disable all other inbound connections except SSH (22107)

### Web Server tasks
- Install Nginx + PHP-FPM and PHP extensions  
- Download & extract WordPress  
- Generate `wp-config.php` using Jinja2 template  
- Create and enable custom Nginx virtual host  
- Allow HTTP, HTTPS and SSH via UFW  
- Deny all other inbound connections  

### Result
A fully functional **LEMP stack distributed between two servers**, with correct security boundaries and database isolation.

---

## 🏗️ TP3 — Role-Based Professional Infrastructure

This TP converts TP2 into a production-quality role-based architecture using:

