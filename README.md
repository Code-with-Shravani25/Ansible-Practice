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

## **Problem-03: Create a User**

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
Reboots target servers and waits until they come back online.

---

## **Problem-09: Install Multiple Packages**
**Playbook Description:**  
Installs multiple packages on all managed nodes using a loop.

---

## **Problem-10: Conditional Package Installation**
**Playbook Description:**  
Installs Nginx on Debian-based systems or Apache HTTPD on RedHat-based systems using conditionals, and enables the service.

---

## **Problem-11: Role-Based Nginx Deployment**
**Playbook Description:**  
Deploys an Nginx web server using a role that installs, configures, copies a webpage, and restarts Nginx.

---

## **Problem-12: Daily Cron Job**
**Playbook Description:**  
Ensures a script exists and sets up a daily 3 AM cron job to run it, logging output to `/var/log/cleanup.log`.

---

## **Problem-13: Conditional Command Execution**

### **Playbook 1:**  
Uses the `stat` module to check if a file exists and runs a command only if it does.

### **Playbook 2:**  
Uses a shell inline conditional (`if`) to check file existence and run a command.

---

## **Problem-14: Download and Extract Prometheus**
**Playbook Description:**  
Downloads the Prometheus tarball and extracts it to a specified directory.

---

## **Problem-15: Stop Service on High Disk Usage**
**Playbook Description:**  
Checks root disk usage and stops the Nginx service if it exceeds 80%.

---

## **Problem-16: Add Host Entries Using lineinfile**
**Playbook Description:**  
Ensures each IP–hostname entry exists in a file using Ansible’s `lineinfile` module.

---

## **Problem-17: Fetch Logs from All Servers**
**Playbook Description:**  
Creates a local folder per host and fetches each server’s `/var/log/messages` file into it.

---

## **Problem-18: Rolling Deployment**
**Playbook Description:**  
Performs a rolling deployment by updating and restarting one server at a time using `serial: 1`.


## **Problem-19: Clone a Git Repo and runa  script/Playbook**
**Playbook1**  
Clone a Git repo and run a script.

**Solution2** 
**Play**
Clone a Git repo first and run this play
**Play1** 
Import playbook from this, so after runningplay.yml need to run this play1.yml as import_paybook is static it does not load the playbook at parse time.

---

## **Problem-20: Send Email Alerts**
**Playbook Description:**  
Use block and rescue to handle deployment failures gracefully and send email alerts.

---

## **Problem-21: Send Email Alert**
**Playbook Description:**  
Check service status and send notification if stopped.

---

## **Problem-22: Error Handling in Ansible**
**Playbook Description:**  
Demonstrates error handling with `ignore_errors`, `failed_when`, and `block`, `rescue`, `always` blocks.

---

## **Problem-23: Tags in Ansible Playbook**
**Playbook Description:**  
Uses Ansible tags to run only specific tasks selectively.

---

## **Problem-24: Jinja Template**
**Playbook Description:**  
Deploy a webpage using a jinja2 template and deploy via template module.

---

## **Problem-25: Environment based configuration using Ansible and Jinja Template**
**Playbook Description:**  
This project demonstrates how to dynamically generate environment-specific configuration files using Ansible variables and Jinja2 templates.
The same configuration template is reused across dev, test, and prod environments, with values customized at runtime based on inventory and variable files.

---

## **Problem-26: Install and configure MySQL DB**
**Playbook Description:**  
Install and configure MySQL DB
