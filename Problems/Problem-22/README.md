# Ansible Error Handling

Ansible provides multiple ways to control how tasks behave when errors occur.  
By default, when a task fails, the playbook stops.  
Error handling helps you decide whether to continue, stop, or perform corrective actions.

---

## 🔹 1. What is Error Handling in Ansible?

**Error handling** is the mechanism in Ansible used to manage task failures.  
It allows you to:

- Ignore errors and continue execution  
- Define custom failure conditions  
- Group tasks and apply “try–catch–finally” logic  
- Run recovery or cleanup tasks  

Ansible provides several keywords for this:  
`ignore_errors`, `failed_when`, `block`, `rescue`, and `always`.

---

## 🔹 2. `ignore_errors`

### **Definition**
Allows a task to fail **without stopping** the playbook execution.  
The task will be shown as failed, but Ansible continues running.

### **Example**
```yaml
- name: Install a package but ignore if it fails
  apt:
    name: unknown-package
    state: present
  ignore_errors: yes
```
---

## 🔹 3. `failed_when`

### **Definition**
Allows you to define a **custom failure condition** for a task.  
Even if the command succeeds or fails by default, you can control when Ansible should mark it as failed.

### **Example**
```yaml
- name: Check nginx service status
  shell: systemctl status nginx
  register: result
  failed_when: "'inactive' in result.stdout"
```

---

## 🔹 4. `block`

### **Definition**
`block` is used to group multiple tasks together for structured error handling.  
It allows you to handle failures collectively and use `rescue` and `always` blocks.  
Think of it as a `try {}` block in programming.

### **Example**
```yaml
- block:
    - name: Task 1
      shell: echo "Running Task 1"
    - name: Task 2
      shell: /bin/false
```



