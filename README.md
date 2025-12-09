## **Problem-01: Ping Test**
**Playbook Description:**  
Runs a simple ping test on all hosts to verify connectivity.

---

## **Problem-02: Gather System Facts**

### **Playbook 1:**  
Gathers system facts using the setup module and displays IP, OS, and hostname.

### **Playbook 2:**  
Automatically gathers system facts (using `gather_facts: yes`) and displays IP, OS, and hostname.

---

## **Problem-03: Create a Single User**

### **Playbook 1:**  
Creates a user with a password generated using variables.

### **Playbook 2:**  
Creates a user with a password securely stored and retrieved from an Ansible Vault file.

### **Playbook 3:**  
Creates a user with a password directly hashed inside the playbook.

---

## **Problem-04: Create Multiple Users**

### **Playbook 1:**  
Creates multiple users using a simple list and loop.

### **Playbook 2:**  
Creates multiple users with individual passwords defined in variables.

### **Playbook 3:**  
Creates multiple users with usernames and passwords stored securely in an Ansible Vault file.

---

## **Problem-05: Copy File**
**Playbook Description:**  
Copies a file from the Ansible controller to all managed nodes with specific ownership and permissions.

---

## **Problem-06: Fetch File**
**Playbook Description:**  
Fetches a file from each managed node and saves it to a specified path on the controller.

---

## **Problem-07: Change File Ownership**
**Playbook Description:**  
Updates the ownership and permissions of a file on all managed nodes.

---

## **Problem-08: Reboot Servers**
**Playbook Description:**  
Reboots the target servers and waits until they come back online.

---

## **Problem-09: Install Multiple Packages**
**Playbook Description:**  
Installs multiple packages on all managed nodes using a loop.

---

## **Problem-10: Conditional Package Installation**
**Playbook Description:**  
Installs Nginx on Debian-based systems or Apache HTTPD on RedHat-based systems using conditional tasks, and starts/enables the service when required.

---

## **Problem-11: Role-Based Nginx Deployment**
**Playbook Description:**  
Deploys an Nginx web server using an Ansible role that installs Nginx, configures the service, copies a webpage, and restarts Nginx when needed.

---
