---
We use environment-specific inventories and group_vars combined with Jinja2 templates, which helps enables environment-based behavior without duplicating configuration files.
---

**To run a ansible playbook:**
---
For Dev: ansible-playbook -i inventory/dev.ini playbook.yml
---
For Test: ansible-playbook -i inventory/test.ini playbook.yml
---
For Prod: ansible-playbook -i inventory/prod.ini playbook.yml
---
If you place group_vars in the correct location, Ansible loads it automatically. No extra config, no includes.
project/
├── inventory/
│   ├── dev.ini
│   ├── prod.ini
├── group_vars/
│   ├── dev.yml
│   ├── prod.yml
├── deploy.yml

On running: ansible-playbook -i inventory/dev.ini deploy.yml

👉 Ansible will automatically:

Read dev.ini

See group name dev

Load group_vars/dev.yml

Apply vars to hosts in dev group

✔️ No reference needed in playbook
✔️ No vars_files needed
