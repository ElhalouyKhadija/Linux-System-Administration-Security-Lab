Phase 1 — Raw Kali Commands

The following commands and outputs document the practical work performed during Phase 1 on Kali Linux.

1. Create company directories

sudo -i
mkdir -p /opt/company
mkdir /opt/company/IT /opt/company/HR /opt/company/Sales /opt/company/Shared

2. Create groups

groupadd IT
groupadd HR
groupadd Sales
groupadd company

Some groups already existed during the lab.

3. Create users

useradd -m ituser
useradd -m hruser
useradd -m Salesuser

Some users already existed during the lab.

4. Add users to groups

usermod -aG IT,company ituser
usermod -aG HR,company hruser
usermod -aG Sales,company Salesuser

5. Set passwords

passwd ituser
passwd hruser
passwd Salesuser

6. Verify users and groups

id ituser
id hruser
id Salesuser

getent group IT
getent group HR
getent group Sales
getent group company

7. Configure ownership and permissions

chown root /opt/company/IT
chown root /opt/company/HR
chown root /opt/company/Sales
chown root /opt/company/Shared

chmod 2770 /opt/company/IT
chmod 2770 /opt/company/HR
chmod 2770 /opt/company/Sales
chmod 2770 /opt/company/Shared

8. Verify directory permissions

ls -ld /opt/company/*

Expected final structure observed during the lab:

drwxrws--- 2 root HR      ... /opt/company/HR
drwxrws--- 2 root IT      ... /opt/company/IT
drwxrws--- 2 root Sales   ... /opt/company/Sales
drwxrws--- 2 root company ... /opt/company/Shared

9. Test user access

sudo -u ituser ls /opt/company/IT
sudo -u ituser ls /opt/company/HR

sudo -u hruser ls /opt/company/HR
sudo -u hruser ls /opt/company/IT

sudo -u Salesuser ls /opt/company/Sales
sudo -u Salesuser ls /opt/company/IT

sudo -u ituser ls /opt/company/Shared
sudo -u hruser ls /opt/company/Shared
sudo -u Salesuser ls /opt/company/Shared

The department access tests confirmed that users could access their assigned department directory and that unauthorized department access returned Permission denied.

10. Test write access

sudo -u ituser touch /opt/company/IT/test.txt
ls -l /opt/company/IT/test.txt
rm /opt/company/IT/test.txt

The file was successfully created with ownership:

-rw-rw-r-- 1 ituser IT ... test.txt

11. Additional permission verification

getfacl /opt/company/IT

Result included:

owner: root
group: IT
user::rwx
group::rwx
other::---

12. Troubleshooting examples

A typo was made when trying to use usermod:

sudo usermd -aG IT salesuser

Result:

sudo: usermd: command not found

The correct command was located with:

which usermod

Result:

/usr/sbin/usermod

Then the command was executed using:

sudo /usr/sbin/usermod -aG IT salesuser

Another path typo occurred:

ls -ld /company/*

Result:

ls: cannot access '/company/*': No such file or directory

The correct path was:

ls -ld /opt/company/*