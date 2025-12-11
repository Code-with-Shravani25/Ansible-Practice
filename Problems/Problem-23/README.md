# ✅ Using Tags in Ansible Playbooks

Tags allow you to run only selected tasks inside a playbook instead of running the entire playbook.

---

## 📌 Example Playbook With Tags

```yaml
---
- name: Install and configure web server
  hosts: web
  become: yes

  tasks:
    - name: Install nginx
      apt:
        name: nginx
        state: present
      tags:
        - install
        - nginx

    - name: Start nginx service
      service:
        name: nginx
        state: started
        enabled: yes
      tags:
        - start
        - nginx

    - name: Copy index.html
      copy:
        src: files/index.html
        dest: /var/www/html/index.html
      tags:
        - copy
        - deploy

    - name: Restart nginx
      service:
        name: nginx
        state: restarted
      tags:
        - restart
        - nginx
```

## 🏃 Running Playbook With Tags

### ✔ Run only install tagged tasks
```bash
ansible-playbook site.yml --tags install
```

### ✔ Run only nginx-related tasks
```bash
ansible-playbook site.yml --tags nginx
```

### ✔ Run only deploy tasks
```bash
ansible-playbook site.yml --tags deploy
```

---

## 🚫 Running Playbook by Skipping Certain Tags

### ✔ Run all tasks except restart
```bash
ansible-playbook site.yml --skip-tags restart
```

### ✔ Run everything except nginx-related tasks
```bash
ansible-playbook site.yml --skip-tags nginx
```

---

## 🏷 Run Multiple Tags Together
```bash
ansible-playbook site.yml --tags "start,deploy"
```

