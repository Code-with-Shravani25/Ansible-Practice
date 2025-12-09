# Linux Passwords – Important Concepts

In Linux, passwords are **never stored in plain text**.  
Instead, Linux stores a **hashed version** of the password, and **SHA-512** is one of the commonly used hashing algorithms for secure password storage.

## Key Points

- Passwords are strings, so they must be written inside **double quotes** when used in scripts or Ansible playbooks.
- Linux does **not** store actual passwords — only their **hashed values** in `/etc/shadow`.
- The file `/etc/passwd` stores user account information, but *not* their passwords.

## Useful Commands

### ✔️ Check Existing Users
```bash
cat /etc/passwd
