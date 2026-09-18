# Phase 3 — SSH Service & Remote Access

> **Status:** ✅ Completed & verified on Kali Linux  
> **Service:** OpenSSH  
> **Default port:** `22/tcp`

## Objective

Install, enable, manage, test, and perform basic security verification of the SSH service on Kali Linux.

## Lab Overview

| Item | Details |
| --- | --- |
| Operating system | Kali Linux |
| Service | OpenSSH Server (`sshd`) |
| Protocol | SSH |
| Default port | `22/tcp` |
| Final state | Enabled and active |
| Connection test | `ssh localhost` |
| Test user | `kali` |

## Procedure

### 1. Install OpenSSH Server

Install the OpenSSH server package. If it is already installed, the package manager confirms that it is up to date.

```bash
sudo apt install openssh-server
```

**Expected result:**

```text
openssh-server is already the newest version
```

### 2. Enable and Start the Service

Enable SSH to start automatically at boot and start it immediately.

```bash
sudo systemctl enable --now ssh
```

### 3. Verify the Service State

Confirm that the service is currently active.

```bash
systemctl is-active ssh
```

**Expected result:**

```text
active
```

### 4. Inspect the SSH Service

Display the detailed service status and verify that SSH is listening on port `22`.

```bash
sudo systemctl status ssh
```

### 5. Test a Local SSH Connection

Connect to the local machine through SSH.

```bash
ssh localhost
```

After connecting, verify the authenticated user:

```bash
whoami
```

**Expected result:**

```text
kali
```

Exit the SSH session:

```bash
exit
```

## Service Management Tests

### Stop the SSH Service

```bash
sudo systemctl stop ssh
```

Verify that the service has stopped:

```bash
sudo systemctl status ssh
```

**Expected result:**

```text
inactive (dead)
```

### Start the SSH Service Again

```bash
sudo systemctl start ssh
```

Verify that the service is running:

```bash
sudo systemctl status ssh
```

**Expected result:**

```text
active (running)
```

## SSH Configuration Check

Inspect the `PermitRootLogin` directive in the SSH server configuration:

```bash
sudo grep PermitRootLogin /etc/ssh/sshd_config
```

**Observed configuration:**

```text
#PermitRootLogin prohibit-password
```

> **Security note:** Avoid permitting direct root login unless there is a documented administrative requirement. Prefer individual user accounts with `sudo`, strong authentication, and—where appropriate—SSH keys.

## Final Verification

Verify that SSH is configured to start automatically and is currently running:

```bash
sudo systemctl is-enabled ssh
sudo systemctl is-active ssh
```

**Final results:**

```text
SSH service: enabled
SSH service: active
```

## Skills Practiced

- Installing and verifying the OpenSSH server package
- Enabling and starting a system service with `systemctl`
- Stopping and restarting SSH safely
- Checking service status and runtime state
- Testing a local SSH connection
- Verifying the authenticated SSH user
- Inspecting SSH server configuration
- Understanding the role of port `22/tcp`
- Applying basic SSH security considerations

## Practical Evidence

This phase includes terminal output, service status checks, SSH connection tests, configuration verification, and screenshots collected during the Kali Linux lab.

## Completion Checklist

- [x] OpenSSH server installed
- [x] SSH service enabled at startup
- [x] SSH service started successfully
- [x] Local SSH connection tested
- [x] Current SSH user verified
- [x] Stop/start service operations tested
- [x] `PermitRootLogin` configuration inspected
- [x] Final service state confirmed as enabled and active
