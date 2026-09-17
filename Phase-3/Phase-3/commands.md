# Phase 3 — SSH Service & Remote Access

# Check OpenSSH installation
sudo apt install openssh-server

# Enable and start SSH
sudo systemctl enable --now ssh

# Check if SSH is active
systemctl is-active ssh

# Check SSH service status
sudo systemctl status ssh

# Test SSH connection locally
ssh localhost

# Check current user
whoami

# Exit SSH session
exit

# Stop SSH service
sudo systemctl stop ssh

# Check SSH status
sudo systemctl status ssh

# Start SSH service
sudo systemctl start ssh

# Check SSH status again
sudo systemctl status ssh

# Check SSH root login configuration
sudo grep PermitRootLogin /etc/ssh/sshd_config

# Check if SSH is enabled
sudo systemctl is-enabled ssh

# Check if SSH is active
sudo systemctl is-active ssh

# List running services
sudo systemctl list-units --type=service --state=running