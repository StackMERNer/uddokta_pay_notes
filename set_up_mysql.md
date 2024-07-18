

# MySQL Installation and Setup for UddoktaPay

This guide will help you install MySQL and set it up for use with UddoktaPay on your VPS running Ubuntu.

## 1. Install MySQL

First, install MySQL server on your VPS.

```bash
sudo apt update
sudo apt install mysql-server
```

## 2. Log into MySQL

Log into MySQL as the root user:

```bash
sudo mysql -u root -p
```

Enter the MySQL root password you set during the secure installation process. (or just press enter if you haven't set any password).

## 3. Create Database and User

Create a new database and user for UddoktaPay. Replace `your_password` with a strong password of your choice.

```sql
CREATE DATABASE uddoktapay_db;
CREATE USER 'uddoktapay_user'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON uddoktapay_db.* TO 'uddoktapay_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

This guide provides the steps needed to install and set up MySQL for UddoktaPay. For further details, refer to the official UddoktaPay documentation or support resources.