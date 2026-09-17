Phase 3 — SSH Service & Remote Access

Objective

The objective of this phase was to install, enable, manage, and test the SSH service on Kali Linux.

1. Check OpenSSH Installation

The OpenSSH server package was checked using:

sudo apt install openssh-server

Result:

openssh-server is already the newest version

2. Enable and Start SSH

The SSH service was enabled and started using:

sudo systemctl enable --now ssh

The service status was then checked:

systemctl is-active ssh

Result:

active

3. Check SSH Service Status

The SSH service was also inspected using:

sudo systemctl status ssh

The service was running and listening on port 22.

4. Test SSH Connection

A local SSH connection was tested using:

ssh localhost

After connecting, the current user was verified:

whoami

Result:

kali

The SSH session was then closed using:

exit

5. Stop and Start SSH Service

The SSH service was stopped to verify service management:

sudo systemctl stop ssh

The service status showed:

inactive (dead)

The service was then started again:

sudo systemctl start ssh

The status returned to:

active (running)

6. SSH Configuration Check

The SSH configuration was inspected using:

sudo grep PermitRootLogin /etc/ssh/sshd_config

The configuration showed:

#PermitRootLogin prohibit-password

7. Service Verification

The following commands were used to verify the SSH service:

sudo systemctl is-enabled ssh
sudo systemctl is-active ssh

Results:
	•	SSH service: enabled
	•	SSH service: active

What I Learned
	•	How to check OpenSSH installation
	•	How to enable and start SSH
	•	How to stop and restart a system service
	•	How to check service status with systemctl
	•	How to test an SSH connection
	•	How to inspect basic SSH configuration
	•	How SSH uses port 22

Practical Status

Applied / Completed

This phase was practically performed and verified on Kali Linux using terminal commands and screenshots.