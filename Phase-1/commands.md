# Enter root shell
sudo -i

# Create company directory
mkdir -p /opt/company

# Create department directories
mkdir /opt/company/IT /opt/company/HR /opt/company/Sales /opt/company/Shared

# Create groups
groupadd IT
groupadd HR
groupadd Sales
groupadd company

# Create users
useradd -m ituser
useradd -m hruser
useradd -m Salesuser

# Add users to groups
usermod -aG IT,company ituser
usermod -aG HR,company hruser
usermod -aG Sales,company Salesuser

# Set passwords
passwd ituser
passwd hruser
passwd Salesuser

# Verify users
id ituser
id hruser
id Salesuser

# Verify groups
getent group IT
getent group HR
getent group Sales
getent group company

# Set directory ownership
chown root /opt/company/IT
chown root /opt/company/HR
chown root /opt/company/Sales
chown root /opt/company/Shared

# Set permissions
chmod 2770 /opt/company/IT
chmod 2770 /opt/company/HR
chmod 2770 /opt/company/Sales
chmod 2770 /opt/company/Shared

# Verify directory permissions
ls -ld /opt/company/*

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

# Test write permission
sudo -u ituser touch /opt/company/IT/test.txt
ls -l /opt/company/IT/test.txt
rm /opt/company/IT/test.txt

# Verify ACL permissions
getfacl /opt/company/IT

# Troubleshooting: incorrect command
sudo usermd -aG IT salesuser

# Find the correct usermod path
which usermod

# Correct command
sudo /usr/sbin/usermod -aG IT salesuser

# Troubleshooting: incorrect path
ls -ld /company/*

# Correct path
ls -ld /opt/company/*
