Phase 1 — Linux Users, Groups & Permissions

Objective

The objective of this phase was to create a basic company structure on Linux using users, groups, directories, ownership, and permissions.

The practical lab was performed on Kali Linux.

Company Directory Structure

/opt/company/
├── IT/
├── HR/
├── Sales/
└── Shared/

Users
	•	ituser
	•	hruser
	•	Salesuser

Groups
	•	IT
	•	HR
	•	Sales
	•	company

Permissions and Ownership

The final directory permissions were:

/opt/company/HR
Owner: root
Group: HR
Permissions: drwxrws---

/opt/company/IT
Owner: root
Group: IT
Permissions: drwxrws---

/opt/company/Sales
Owner: root
Group: Sales
Permissions: drwxrws---

/opt/company/Shared
Owner: root
Group: company
Permissions: drwxrws---

The directories were configured with chmod 2770.

This gives the owner and group full access while denying access to others. The setgid bit also keeps the directory group for newly created files and directories.

Access Tests

The permissions were tested with different users.

ituser → IT       : Access successful
ituser → HR       : Permission denied

hruser → HR       : Access successful
hruser → IT       : Permission denied

Salesuser → Sales : Access successful
Salesuser → IT    : Permission denied

ituser → Shared   : Access successful
hruser → Shared   : Access successful
Salesuser → Shared: Access successful

Write Permission Test

A write test was performed by ituser:

sudo -u ituser touch /opt/company/IT/test.txt

The file was successfully created:

-rw-rw-r-- 1 ituser IT 0 ... test.txt

The test file was then removed.

Permission Verification

The final permissions were verified with:

ls -ld /opt/company/*

The result confirmed:

drwxrws--- 2 root HR      ... /opt/company/HR
drwxrws--- 2 root IT      ... /opt/company/IT
drwxrws--- 2 root Sales   ... /opt/company/Sales
drwxrws--- 2 root company ... /opt/company/Shared

Additional verification was performed with:

getfacl /opt/company/IT

Result:

owner: root
group: IT
user::rwx
group::rwx
other::---

Troubleshooting

During the practical work, some command errors occurred and were corrected.

Example:

sudo usermd -aG IT salesuser

Result:

sudo: usermd: command not found

The correct command was identified with:

which usermod

Result:

/usr/sbin/usermod

Then:

sudo /usr/sbin/usermod -aG IT salesuser

Another path typo occurred:

ls -ld /company/*

The correct path was:

ls -ld /opt/company/*

What I Learned

Through this phase, I practiced:
	•	Linux users and groups
	•	useradd
	•	usermod
	•	groupadd
	•	id
	•	groups
	•	getent group
	•	chown
	•	chmod
	•	Linux ownership and permissions
	•	Setgid permissions
	•	Access testing
	•	Basic Linux troubleshooting

Practical Status

Applied / Completed

This phase was practically performed on Kali Linux and verified using commands, outputs, access tests, and screenshots.