````markdown
# Phase 3 — SSH Service & Remote Access

## Objective

The objective of this phase was to install, enable, manage, and test the SSH service on Kali Linux.

## Practical Commands

The following commands were used during the practical lab.

### 1. Check OpenSSH Installation

```bash
# Check OpenSSH server installation
sudo apt install openssh-server
```

**Result:**

```text
openssh-server is already the newest version
```

### 2. Enable and Start SSH

```bash
# Enable and start the SSH service
sudo systemctl enable --now ssh
```

### 3. Check if SSH Is Active

```bash
# Check if the SSH service is active
systemctl is-active ssh
```

**Result:**

```text
active
```

### 4. Check SSH Service Status

```bash
# Check SSH service status
sudo systemctl status ssh
```

The service was running and listening on port `22`.

### 5. Test SSH Connection

```bash
# Test a local SSH connection
ssh localhost
```

### 6. Verify the Current User

After connecting through SSH, the current user was verified:

```bash
# Check the current user
whoami
```

**Result:**

```text
kali
```

### 7. Exit the SSH Session

```bash
# Exit the SSH session
exit
```

### 8. Stop the SSH Service

The SSH service was stopped to verify service management:

```bash
# Stop the SSH service
sudo systemctl stop ssh
```

### 9. Verify SSH Service Is Stopped

```bash
# Check SSH service status
sudo systemctl status ssh
```

**Result:**

```text
inactive (dead)
```

### 10. Start the SSH Service Again

```bash
# Start the SSH service
sudo systemctl start ssh
```

### 11. Verify SSH Service Is Running

```bash
# Check SSH service status
sudo systemctl status ssh
```

**Result:**

```text
active (running)
```

### 12. Check SSH Configuration

```bash
# Check the PermitRootLogin SSH configuration
sudo grep PermitRootLogin /etc/ssh/sshd_config
```

**Result:**

```text
#PermitRootLogin prohibit-password
```

### 13. Verify SSH Service Is Enabled

```bash
# Check if SSH is enabled at system startup
sudo systemctl is-enabled ssh
```

### 14. Verify SSH Service Is Active

```bash
# Check if the SSH service is currently active
sudo systemctl is-active ssh
```

**Results:**

```text
SSH service: enabled
SSH service: active
```

## What I Learned

Through this phase, I practiced:

- Checking OpenSSH installation
- Enabling and starting the SSH service
- Stopping and starting a system service
- Checking service status with `systemctl`
- Testing a local SSH connection
- Verifying the current SSH user
- Inspecting basic SSH configuration
- Understanding SSH port `22`

## Practical Evidence

This phase includes practical SSH service management, connection testing, configuration checks, command results, and screenshots collected from the Kali Linux lab.

## Practical Status

**Applied / Completed**

This phase was practically performed and verified on Kali Linux using terminal commands, service status checks, SSH connection tests, and screenshots.
````
