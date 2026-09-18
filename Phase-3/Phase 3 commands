# Phase 3 — SSH Service & Remote Access

> **Status:** ✅ Completed & verified on Kali Linux  
> **Service:** OpenSSH  
> **Default port:** `22/tcp`

## Practical Commands

This section contains the terminal commands used to install, enable, verify, and secure the SSH service during the lab.

### 1. Install OpenSSH Server

```bash
sudo apt install openssh-server
```

### 2. Enable and Start the SSH Service

```bash
sudo systemctl enable --now ssh
```

### 3. Verify the Service Is Active

```bash
systemctl is-active ssh
```

### 4. Inspect the SSH Service Status

```bash
sudo systemctl status ssh
```

### 5. Test a Local SSH Connection

```bash
ssh localhost
```

### 6. Check the Authenticated User

```bash
whoami
```

### 7. Stop the SSH Service

```bash
sudo systemctl stop ssh
```

### 8. Start the SSH Service Again

```bash
sudo systemctl start ssh
```

### 9. Inspect the SSH Configuration

```bash
sudo grep PermitRootLogin /etc/ssh/sshd_config
```

### 10. Confirm the Final Service State

```bash
sudo systemctl is-enabled ssh
sudo systemctl is-active ssh
```

## Expected Results

```text
openssh-server is already the newest version
active
inactive (dead)
active (running)
kali
#PermitRootLogin prohibit-password
SSH service: enabled
SSH service: active
```
