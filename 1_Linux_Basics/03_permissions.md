
# 03 - Linux File Permissions (Full Guide)

Linux uses a permission system to protect files and directories by controlling **who can read, write, or execute** them.

---

## 🛡️ 1. Permission Types

Each file and folder has three sets of permissions:

- **User (u)** – the file owner  
- **Group (g)** – users in the same group  
- **Others (o)** – everyone else

Each set can have:

| Symbol | Permission | Description                            |
|--------|------------|----------------------------------------|
| r      | Read       | View file contents or list directory   |
| w      | Write      | Modify file or directory contents      |
| x      | Execute    | Run file or access directory           |

---

## 🔍 2. Viewing File Permissions

Use the `ls -l` command to view permissions:

```bash
ls -l filename
```

Example output:

```
-rwxr-xr-- 1 user group 123 Jun 8 17:00 script.sh
```

Breakdown:
- `-` → File type (`d` for directory, `-` for file)
- `rwx` → User (owner) permissions → read, write, execute
- `r-x` → Group permissions → read, execute
- `r--` → Others → read only

---

## 🔧 3. Changing Permissions – `chmod`

You can modify permissions using the `chmod` command in symbolic or numeric (octal) format.

### A. Symbolic Format:

```bash
chmod u+x script.sh     # Add execute for user
chmod g-w file.txt      # Remove write for group
chmod o+r file.txt      # Add read for others
chmod a+x file.sh       # Add execute for all (user, group, others)
```

### B. Numeric Format:

| Number | Permissions | Meaning               |
|--------|-------------|-----------------------|
| 7      | rwx         | Read, write, execute  |
| 6      | rw-         | Read, write           |
| 5      | r-x         | Read, execute         |
| 4      | r--         | Read only             |
| 0      | ---         | No permissions        |

```bash
chmod 755 file.sh   # User: rwx, Group: r-x, Others: r-x
chmod 644 file.txt  # User: rw-, Group: r--, Others: r--
```

---

## 👤 4. Changing Ownership – `chown`

Use `chown` to change the owner or group of a file or directory.

```bash
chown newuser filename            # Change file owner
chown newuser:newgroup file.txt   # Change owner and group
chown -R user:group folder/       # Recursive ownership change
```

---

## 🎭 5. Default Permissions – `umask`

When you create a new file or folder, it doesn’t get full permissions (`777` or `666`). Instead, `umask` subtracts permissions from defaults.

Check your current umask:

```bash
umask
```

### Example:

```bash
umask 0022
```

This means:
- New files → `rw-r--r--` (644)
- New folders → `rwxr-xr-x` (755)

---

## ⚙️ 6. Special Permissions (SUID, SGID, Sticky Bit)

### A. Sticky Bit (`t`)

Used on shared directories (e.g., `/tmp`). It allows only the file owner to delete their files.

```bash
chmod +t /shared/folder
```

Result:
```
drwxrwxrwt   7 root root 4096 /tmp
```

---

### B. SUID (`s` on user)

When set, the file executes with **owner’s privileges** (often root).

```bash
chmod u+s /usr/bin/somebinary
```

Result:
```
-rwsr-xr-x  1 root root /usr/bin/passwd
```

---

### C. SGID (`s` on group)

- On files: Executes with **group's permissions**
- On directories: New files inherit the group

```bash
chmod g+s /project/teamdir
```

Result:
```
drwxrwsr-x  2 devteam devteam /project/teamdir
```

---

## 🧪 7. Practice Examples

```bash
chmod 777 test.sh         # Full access to everyone (⚠️ avoid in production)
chmod 700 secrets.txt     # Only user can read/write/execute
chmod 750 deploy.sh       # User full, group r+x, others none

chown kiran:kiran file.txt    # Change owner and group
umask 0027                    # Block all permissions for others by default
```

---

## 📌 Summary

| Task                | Command                         |
|---------------------|----------------------------------|
| View permissions    | `ls -l`                          |
| Change permissions  | `chmod 755 file.sh`              |
| Change ownership    | `chown user:group file.txt`      |
| Check default umask | `umask`                          |
| Add sticky bit      | `chmod +t /dir`                  |
| Set SUID            | `chmod u+s file`                 |
| Set SGID            | `chmod g+s file`                 |

---

