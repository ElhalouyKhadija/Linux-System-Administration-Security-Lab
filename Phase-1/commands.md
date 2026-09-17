┌──(kali㉿kali)-[~]
└─$ sudo -i
[sudo] password for kali:

┌──(root㉿kali)-[~]
└─# mkdir -p /opt/company

┌──(root㉿kali)-[~]
└─# mkdir /opt/company/IT /opt/company/HR /opt/company/Sales /opt/company/Shared

┌──(root㉿kali)-[~]
└─# groupadd IT
groupadd: group 'IT' already exists

┌──(root㉿kali)-[~]
└─# groupadd HR
groupadd: group 'HR' already exists

┌──(root㉿kali)-[~]
└─# groupadd Sales

┌──(root㉿kali)-[~]
└─# groupadd company
groupadd: group 'company' already exists

┌──(root㉿kali)-[~]
└─# useradd -m ituser
useradd: user 'ituser' already exists

┌──(root㉿kali)-[~]
└─# useradd -m hruser
useradd: user 'hruser' already exists

┌──(root㉿kali)-[~]
└─# useradd -m Salesuser

┌──(root㉿kali)-[~]
└─# usermod -aG IT,company ituser

┌──(root㉿kali)-[~]
└─# usermod -aG HR,company hruser

┌──(root㉿kali)-[~]
└─# usermod -aG Sales,company Salesuser

┌──(root㉿kali)-[~]
└─# passwd ituser
New password:
Retype new password:
passwd: password updated successfully

┌──(root㉿kali)-[~]
└─# passwd hruser
New password:
Retype new password:
passwd: password updated successfully

┌──(root㉿kali)-[~]
└─# passwd Salesuser
New password:
Retype new password:
passwd: password updated successfully

┌──(root㉿kali)-[~]
└─# id ituser
uid=1001(ituser) gid=1001(ituser) groups=1001(ituser),100(users),1004(IT),1007(company)

┌──(root㉿kali)-[~]
└─# id hruser
uid=1003(hruser) gid=1003(hruser) groups=1003(hruser),100(users),1005(HR),1007(company)

┌──(root㉿kali)-[~]
└─# id Salesuser
uid=1004(Salesuser) gid=1009(Salesuser) groups=1009(Salesuser),1007(company),1008(Sales)

┌──(root㉿kali)-[~]
└─# getent group IT
IT:x:1004

┌──(root㉿kali)-[~]
└─# getent group HR
HR:x:1005

┌──(root㉿kali)-[~]
└─# getent group Sales
Sales:x:1008

┌──(root㉿kali)-[~]
└─# getent group company
company:x:1007,hruser,salesuser,Salesuser

┌──(root㉿kali)-[~]
└─# chown root /opt/company/IT

┌──(root㉿kali)-[~]
└─# chown root /opt/company/HR

┌──(root㉿kali)-[~]
└─# chown root /opt/company/HR

┌──(root㉿kali)-[~]
└─#

┌──(root㉿kali)-[~]
└─# ls -ld /opt/company/HR /opt/company/Sales
drwxr-xr-x 2 root Sales 4096 Sep 14 13:19 /opt/company/HR
drwxr-xr-x 2 root root  4096 Sep 14 13:19 /opt/company/Sales

┌──(root㉿kali)-[~]
└─# chown root /opt/company/HR

┌──(root㉿kali)-[~]
└─# chown root /opt/company/Sales

┌──(root㉿kali)-[~]
└─# chown root /opt/company/IT

┌──(root㉿kali)-[~]
└─# chown root /opt/company/Shared

┌──(root㉿kali)-[~]
└─# chmod 2770 /opt/company/IT

┌──(root㉿kali)-[~]
└─# chmod 2770 /opt/company/HR

┌──(root㉿kali)-[~]
└─# chmod 2770 /opt/company/Sales

┌──(root㉿kali)-[~]
└─# chmod 2770 /opt/company/Shared

┌──(root㉿kali)-[~]
└─# ls -ld /opt/company/*
drwxrws--- 2 root HR      4096 Sep 14 13:19 /opt/company/HR
drwxrws--- 2 root IT      4096 Sep 14 13:19 /opt/company/IT
drwxrws--- 2 root Sales   4096 Sep 14 13:19 /opt/company/Sales
drwxrws--- 2 root company 4096 Sep 14 13:19 /opt/company/Shared

┌──(root㉿kali)-[~]
└─# sudo -u ituser ls /opt/company/IT

┌──(root㉿kali)-[~]
└─# sudo -u ituser ls /opt/company/HR
ls: cannot open directory '/opt/company/HR': Permission denied

┌──(root㉿kali)-[~]
└─# sudo -u hruser ls /opt/company/HR

┌──(root㉿kali)-[~]
└─# sudo -u hruser ls /opt/company/IT
ls: cannot open directory '/opt/company/IT': Permission denied

┌──(root㉿kali)-[~]
└─# sudo -u Salesuser ls /opt/company/Sales

┌──(root㉿kali)-[~]
└─# sudo -u Salesuser ls /opt/company/IT
ls: cannot open directory '/opt/company/IT': Permission denied

┌──(root㉿kali)-[~]
└─# sudo -u ituser ls /opt/company/Shared

┌──(root㉿kali)-[~]
└─# sudo -u hruser ls /opt/company/Shared

┌──(root㉿kali)-[~]
└─# sudo -u Salesuser ls /opt/company/Shared

┌──(root㉿kali)-[~]
└─# sudo -u ituser touch /opt/company/IT/test.txt

┌──(root㉿kali)-[~]
└─# ls -l /opt/company/IT/test.txt
-rw-rw-r-- 1 ituser IT 0 Sep 14 15:32 /opt/company/IT/test.txt

┌──(root㉿kali)-[~]
└─# rm /opt/company/IT/test.txt

┌──(root㉿kali)-[~]
└─# ls -ld /company/*
ls: cannot access '/company/*': No such file or directory

┌──(root㉿kali)-[~]
└─# ls -ld /opt/company/*
drwxrws--- 2 root HR      4096 Sep 14 13:19 /opt/company/HR
drwxrws--- 2 root IT      4096 Sep 14 15:37 /opt/company/IT
drwxrws--- 2 root Sales   4096 Sep 14 13:19 /opt/company/Sales
drwxrws--- 2 root company 4096 Sep 14 13:19 /opt/company/Shared


