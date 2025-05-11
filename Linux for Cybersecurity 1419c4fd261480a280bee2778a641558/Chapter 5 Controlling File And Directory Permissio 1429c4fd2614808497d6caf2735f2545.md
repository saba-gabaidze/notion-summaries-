# Chapter 5 Controlling File And Directory Permissions

# there are different types of users

1. **Root User**: The most powerful user with full control over the system. The root user can do anything, including changing system settings and accessing all files.
2. **Regular Users**: These users have limited access, mainly to their own files and specific system resources. They don't have the privileges of the root user.
3. **Groups**: Users are often organized into groups based on their roles (e.g., developers, network admins). Groups help manage permissions more easily, granting similar rights to all members of a group.

# `chown “username” /etc/file`  -Change the ownership of a file to a different user

# `chgrp “group” /etc/file` -  transfer ownership of a file to a different group

# Indicator

`-rw-r--r-- 1 root root 33685504 June 28 2018 hashcat.hcstat`

- `-` : Indicates it's a file.
- `rw-`: The owner can read and write.
- `r--`: The group can only read.
- `r--`: Others can only read.

# Changing Permissions with Decimal Notation `chmod`

### **Octal Values**:

- `0`: `--` (no permissions)
- `1`: `-x` (execute)
- `2`: `w-` (write)
- `4`: `r--` (read)
- Combine permissions (e.g., `rwx = 7`, `r-x = 5`).

### Example

`chmod  774 “example”` 

**Setting Permissions**:

- Use `chmod [octal][filename]`.
- Example: `chmod 774 file` gives:
    - Owner: `rwx` (7)
    - Group: `rwx` (7)
    - Others: `r--` (4).

# UGO

### **UGO Syntax**:

- **u**: User (Owner)
- **g**: Group
- **o**: Others

### **Operators**

- `-`: Remove permission
- `+`: Add permission
- `=`: Set specific permission

### **command Format**

`chmod g+w “file”`

`chmod [u/g/o][operator][permission] [filename]`

- `Remove write permission for user: chmod u-w file`
- `Add execute permission for user and others: chmod u+x,o+x file`

## Giving Root Execute Permission on a New Tool

- Use `chmod` to grant execute permission.
- Example: `chmod 766 newhackertool` grants:
    - Owner: `rwx` (7).
    - Group and Others: `rw-` (6).

# Default Permissions with Masks

### **Default Base Permissions**

- Files: `666`.
- Directories: `777`.

### How it Works

- `umask 022` results in:
    - Files: `644` (`666 - 022`).
    - Directories: `755` (`777 - 022`).

### **Current Default in Kali/Debian**

- Files: `644` (Owner: `rw`, Group/Others: `r`).
- Directories: `755` (Owner: `rwx`, Group/Others: `r-x`).

### **Customization**:

- Users can modify their default `umask` in `/home/username/.profile`.
- Example: Setting `umask 007` allows:
    - Owner: full permissions (`rwx`).
    - Group: full permissions (`rwx`).
    - Others: no permissions (`--`).

# **SUID** (Set User ID)

SUID (Set User ID) is a special permission in Unix-like operating systems that allows a user to execute a program with the privileges of the program's owner, rather than the privileges of the user running the program

`chmod 4”665” "filename"` -   `4644` (the `4` is for SUID, followed by the usual permissions).
SUID (Set User ID) is a special permission in Unix-like operating systems that allows a user to execute a program with the privileges of the program's owner, rather than the privileges of the user running the program

# SGID (Set Group ID)

`chmod 2”644” "filename"` -  With SGID: `2644` (the `2` is for SGID, followed by the usual permissions).

# Key Point on **Sticky Bit**

- **Purpose**: The sticky bit was used to allow users to delete or rename files in a shared directory.
- **Modern Relevance**: It is largely outdated and ignored by modern Linux systems.
- **Important Note**: You might still come across the term in Linux discussions.

# Hacker threats

The command `find / -user root -perm -4000` searches the entire filesystem (`/`) for files that are owned by the `root` user and have the **SUID** (Set User ID) permission set (`-4000`). The SUID bit allows a file to be executed with the privileges of the file’s owner (typically root). This is useful for identifying files that can be exploited for privilege escalation.

- **Privilege Escalation**: Hackers can exploit special permissions (like SUID and SGID) to gain elevated privileges (e.g., root access).
- **SUID Exploitation**: Programs with the SUID bit set allow users to execute them with the owner's privileges (often root), potentially granting unauthorized access to critical files (e.g., `/etc/shadow` for passwords).
- **Finding SUID Files**: Use the `find` command to locate files with the SUID bit set. For example:
- **SUID Representation**: Files with the SUID bit will show an "s" in place of the execute permission for the owner (e.g., `rwsr-xr-x`).
- **Risk**: Files like `sudo` with the SUID bit set allow anyone to run them with root privileges, posing a security risk. Hackers can exploit this to gain control of sensitive files or escalate privileges.

## `find / -user root -perm -4000`