mysql-server: MySQL server package, it installs db server itself (db_daemon), configuration files, systemd unit and initial setup.
---
mysql: why not only mysql installs only client tools, command line tools no dbserver.
---
python3-pymysql: Python library needed by Ansible to communicate with MySQL
---
community.mysql is an ansible collection (a package of modules, plugins and roles) maintained by Ansible community for managing MySQL and MariaDB.
---
login_unix_socket: /var/run/mysql/mysqld.sock
When mysql is freshly installed the root account does not have a password yet that means linux system root user can log in without a password only via UNIX socket file (/var/run/mysql/mysqld.sock).
It will not accept normal TCP connection at this point.
MySQL allows system root to connect via socket authentication. So this allows Ansible to connect as root (system root) through local socket and set root password for first time.
---
check_implicit_admin: true
When this is true, Ansible automatically tries to connect using root UNIX socket as an implicit admin, even if no password is configured yet.
---
To login
---
mysql -u root -p
---
mysql -u username -p
---
SHOW DATABASES;
---
CREATE DATABASE test;
---
