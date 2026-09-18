# Phase 1 — Linux Users, Groups & Permissions

## Objective

The objective of this phase was to create a basic company structure on Linux using users, groups, directories, ownership, and permissions.

The practical lab was performed on **Kali Linux**.

## Company Directory Structure

```text
/opt/company/
├── IT/
├── HR/
├── Sales/
└── Shared/
```

## Users

- `ituser`
- `hruser`
- `salesuser`

## Groups

- `IT`
- `HR`
- `Sales`
- `company`

## Permissions and Ownership

The final directory permissions were:

### HR

```text
Path:        /opt/company/HR
Owner:       root
Group:       HR
Permissions: drwxrws---
```

### IT

```text
Path:        /opt/company/IT
Owner:       root
Group:       IT
Permissions: drwxrws---
```

### Sales

```text
Path:        /opt/company/Sales
Owner:       root
Group:       Sales
Permissions: drwxrws---
```

### Shared

```text
Path:        /opt/company/Shared
Owner:       root
Group:       company
Permissions: drwxrws---
```

The directories were configured with:

```bash
chmod 2770 /opt/company/HR
chmod 2770 /opt/company/IT
chmod 2770 /opt/company/Sales
chmod 2770 /opt/company/Shared
```

This gives the owner and group full access while denying access to others.

The **Setgid** bit also ensures that newly created files and directories inherit the directory's group.

## Access Tests

The permissions were tested with different users.

```text
ituser  → IT       : Access successful
ituser  → HR       : Permission denied

hruser  → HR       : Access successful
hruser  → IT       : Permission denied

salesuser → Sales  : Access successful
salesuser → IT     : Permission denied

ituser  → Shared   : Access successful
hruser  → Shared   : Access successful
salesuser → Shared : Access successful
```

These tests confirmed that users could access their assigned department directory while access to other department directories was restricted.

## Write Permission Test

A write test was performed by `ituser`:

```bash
sudo -u ituser touch /opt/company/IT/test.txt
```

The file was successfully created:

```text
-rw-rw-r-- 1 ituser IT 0 ... test.txt
```

The test file was then removed after verification.

## Permission Verification

The final permissions were verified with:

```bash
ls -ld /opt/company/*
```

The result confirmed:

```text
drwxrws--- 2 root HR      ... /opt/company/HR
drwxrws--- 2 root IT      ... /opt/company/IT
drwxrws--- 2 root Sales   ... /opt/company/Sales
drwxrws--- 2 root company ... /opt/company/Shared
```

Additional verification was performed with:

```bash
getfacl /opt/company/IT
```

Result:

```text
owner: root
group: IT
user::rwx
group::rwx
other::---
```

## Troubleshooting

During the practical work, some command errors occurred and were corrected.

### Command Typo

An incorrect command was entered:

```bash
sudo usermd -aG IT salesuser
```

Result:

```text
sudo: usermd: command not found
```

The correct command was identified with:

```bash
which usermod
```

Result:

```text
/usr/sbin/usermod
```

The correct command was then executed:

```bash
sudo /usr/sbin/usermod -aG IT salesuser
```

### Path Typo

Another path typo occurred:

```bash
ls -ld /company/*
```

The correct path was:

```bash
ls -ld /opt/company/*
```

This successfully displayed the company directory permissions.

## What I Learned

Through this phase, I practiced:

- Linux users and groups
- `useradd`
- `usermod`
- `groupadd`
- `id`
- `groups`
- `getent group`
- `chown`
- `chmod`
- Linux ownership and permissions
- Setgid permissions
- Access testing
- Basic Linux troubleshooting

## Practical Evidence

This phase includes practical commands, command results, access tests, permission verification, troubleshooting examples, and screenshots from the Kali Linux lab.

## Practical Status

**Applied / Completed**

This phase was practically performed on Kali Linux and verified using commands, outputs, access tests, and screenshots.
