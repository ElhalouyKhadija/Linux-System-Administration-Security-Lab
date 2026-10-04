# Phase 5 — Linux Security Checks

> **Objective:** Perform and document basic Linux security checks on Kali Linux, focusing on SSH configuration, service status, file permissions, and user access controls.

## Overview

This phase focused on practical Linux security administration tasks, including:

* Inspecting SSH root-login configuration
* Verifying whether the SSH service is enabled and running
* Reviewing active system services
* Searching `/etc` for world-writable files
* Validating directory access permissions
* Troubleshooting an incorrectly entered command
* Verifying supplementary group membership

## 1. SSH Configuration Check

The SSH daemon configuration was inspected to review the root-login policy:

```bash
sudo grep PermitRootLogin /etc/ssh/sshd_config
```

### Result

```text
#PermitRootLogin prohibit-password
```

The directive is commented out, so the effective setting may depend on the applicable SSH defaults or included configuration files. This check confirmed that the root-login configuration was reviewed.

## 2. SSH Service Verification

The SSH service was checked for both startup configuration and current runtime status:

```bash
sudo systemctl is-enabled ssh
sudo systemctl is-active ssh
```

### Results

| Check                     | Result    |
| ------------------------- | --------- |
| Service enabled at boot   | `enabled` |
| Service currently running | `active`  |

These results confirmed that the SSH service was configured to start automatically and was running during the assessment.

## 3. Running Services Review

All currently running system services were listed with:

```bash
sudo systemctl list-units --type=service --state=running
```

The output included the SSH service.

Reviewing active services helps identify running services that may require further configuration or security hardening.

## 4. World-Writable File Check

A search was performed for world-writable files located directly under `/etc`:

```bash
sudo find /etc -maxdepth 1 -type f -perm -002 -ls
```

### Result

No matching files were displayed during the test.

This indicates that no world-writable regular files were found directly inside `/etc` using the specified search criteria.

> **Scope note:** This command checks only regular files directly inside `/etc`; it does not recursively inspect files in subdirectories.

## 5. Permission Verification

Access permissions were tested against the company directory structure.

### Test with an Invalid Username

```bash
sudo -u saleuder ls /opt/company/IT
```

This produced an unknown-user error because `saleuder` was not a valid configured username.

### Test with the Correct Username

```bash
sudo -u salesuser ls /opt/company/IT
```

### Result

```text
Permission denied
```

The result confirmed that the configured directory permissions prevented `salesuser` from accessing the IT directory.

## 6. Troubleshooting an Incorrect Command

An incorrect command was initially entered while attempting to add `salesuser` to the `IT` group:

```bash
sudo usermd -aG IT salesuser
```

The system returned:

```text
sudo: usermd: command not found
```

The correct executable path was located with:

```bash
which usermod
```

### Result

```text
/usr/sbin/usermod
```

The command was then corrected and executed successfully:

```bash
sudo /usr/sbin/usermod -aG IT salesuser
```

Group membership was verified with:

```bash
id salesuser
```

> **Operational note:** A new login session may be required before updated supplementary group membership is reflected in the user's current session.

## Key Learning Outcomes

By completing this phase, I learned how to:

* Inspect SSH daemon configuration
* Check whether a system service is enabled and active
* Review currently running Linux services
* Search for world-writable files
* Test and interpret Linux directory permissions
* Troubleshoot command-not-found errors
* Locate executables using `which`
* Add users to supplementary groups with `usermod`
* Verify group membership with `id`

## Evidence

The practical work was performed on Kali Linux using the commands documented in the `Phase5 commands` file.

One screenshot is included as visual evidence of the practical work performed during this phase.

## Practical Status

**Applied / Partially Applied**

The documented checks were performed during the lab. The available visual evidence is limited to the screenshot included in this phase.
