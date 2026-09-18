## Practical Commands

The following commands were used during the practical lab.

### 1. Enter Root Shell

```bash
# Enter root shell
sudo -i
```

### 2. Create Company Directory

```bash
# Create company directory
mkdir -p /opt/company

# Create department directories
mkdir /opt/company/IT /opt/company/HR /opt/company/Sales /opt/company/Shared
```

### 3. Create Groups

```bash
# Create groups
groupadd IT
groupadd HR
groupadd Sales
groupadd company
```

### 4. Create Users

```bash
# Create users
useradd -m ituser
useradd -m hruser
useradd -m Salesuser
```

### 5. Add Users to Groups

```bash
# Add users to groups
usermod -aG IT,company ituser
usermod -aG HR,company hruser
usermod -aG Sales,company Salesuser
```

### 6. Set Passwords

```bash
# Set passwords
passwd ituser
passwd hruser
passwd Salesuser
```

### 7. Verify Users

```bash
# Verify users
id ituser
id hruser
id Salesuser
```

### 8. Verify Groups

```bash
# Verify groups
getent group IT
getent group HR
getent group Sales
getent group company
```

### 9. Set Directory Ownership

```bash
# Set directory ownership
chown root /opt/company/IT
chown root /opt/company/HR
chown root /opt/company/Sales
chown root /opt/company/Shared
```

### 10. Set Permissions

```bash
# Set permissions
chmod 2770 /opt/company/IT
chmod 2770 /opt/company/HR
chmod 2770 /opt/company/Sales
chmod 2770 /opt/company/Shared
```

### 11. Verify Directory Permissions

```bash
# Verify directory permissions
ls -ld /opt/company/*
```

### 12. Test User Access

```bash
# Test user access
sudo -u ituser ls /opt/company/IT
sudo -u ituser ls /opt/company/HR

sudo -u hruser ls /opt/company/HR
sudo -u hruser ls /opt/company/IT

sudo -u Salesuser ls /opt/company/Sales
sudo -u Salesuser ls /opt/company/IT

sudo -u ituser ls /opt/company/Shared
sudo -u hruser ls /opt/company/Shared
sudo -u Salesuser ls /opt/company/Shared
```

### 13. Test Write Permission

```bash
# Test write permission
sudo -u ituser touch /opt/company/IT/test.txt
ls -l /opt/company/IT/test.txt
rm /opt/company/IT/test.txt
```

### 14. Verify ACL Permissions

```bash
# Verify ACL permissions
getfacl /opt/company/IT
```

### 15. Troubleshooting — Incorrect Command

```bash
# Troubleshooting: incorrect command
sudo usermd -aG IT salesuser
```

The command produced an error because `usermd` was not a valid command.

### 16. Find the Correct `usermod` Path

```bash
# Find the correct usermod path
which usermod
```

### 17. Correct Command

```bash
# Correct command
sudo /usr/sbin/usermod -aG IT salesuser
```

### 18. Troubleshooting — Incorrect Path

```bash
# Troubleshooting: incorrect path
ls -ld /company/*
```

### 19. Correct Path

```bash
# Correct path
ls -ld /opt/company/*
```
