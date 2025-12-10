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

---

## 🔹 Block, Rescue, and Always in Ansible

### **block**
**Definition:**  
Groups multiple tasks together for structured error handling.  
Similar to a `try{}` block in programming.

---

### **rescue**
**Definition:**  
Executes tasks **only if any task in the block fails**.  
Acts like a `catch{}` block in programming.

---

### **always**
**Definition:**  
Executes tasks **regardless of success or failure** of the block.  
Equivalent to a `finally{}` block in programming.

---

### **Example**
```yaml
- block:
    - name: Task that may fail
      shell: /bin/false
  rescue:
    - name: Rescue tasks
      debug:
        msg: "Rescue executed."
  always:
    - name: Always run this
      debug:
        msg: "Cleanup tasks always run."
```



