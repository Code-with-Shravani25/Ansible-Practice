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
