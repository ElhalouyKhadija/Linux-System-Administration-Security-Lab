Phase 5 — Linux Security Checks

Objective

The objective of this phase was to perform basic security checks on Kali Linux.

The practical work focused on checking SSH configuration, running services, and identifying world-writable files in /etc.

SSH Configuration Check

The SSH root login configuration was inspected using:

sudo grep PermitRootLogin /etc/ssh/sshd_config

The result showed:

#PermitRootLogin prohibit-password

SSH Service Verification

The SSH service was checked using:

sudo systemctl is-enabled ssh
sudo systemctl is-active ssh

Results:
	•	SSH service: enabled
	•	SSH service: active

This confirmed that the SSH service was enabled and currently running.

Running Services

Running services were reviewed using:

sudo systemctl list-units --type=service --state=running

The list included the SSH service.

World-Writable File Check

A security check was performed to search for world-writable files directly under /etc:

sudo find /etc -maxdepth 1 -type f -perm -002 -ls

No matching files were displayed during the test.

Permission Verification

Access permissions were also checked for the company directories.

An incorrect username was first tested:

sudo -u saleuder ls /opt/company/IT

This resulted in an unknown-user error.

The correct username was then tested:

sudo -u salesuser ls /opt/company/IT

The result was:

Permission denied

This confirmed that the configured directory permissions were restricting access.

Troubleshooting

During the practical work, a command was entered incorrectly:

sudo usermd -aG IT salesuser

The system returned:

sudo: usermd: command not found

The correct path was identified using:

which usermod

Result:

/usr/sbin/usermod

The correct command was then used:

sudo /usr/sbin/usermod -aG IT salesuser

The user group membership was verified with:

id salesuser

What I Learned
	•	How to inspect SSH configuration
	•	How to check whether a service is enabled and active
	•	How to review running Linux services
	•	How to check for world-writable files
	•	How Linux permissions restrict access
	•	How to troubleshoot an incorrect command
	•	How to verify user group membership

Evidence

The practical work was performed on Kali Linux and verified using terminal commands and screenshots.

Practical Status

Applied / Partially Applied