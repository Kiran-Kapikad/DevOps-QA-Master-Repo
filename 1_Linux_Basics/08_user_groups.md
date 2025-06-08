
# 08 - Linux Users and Groups (Full Guide)

Managing users and groups is essential for access control, testing roles, and multi-user systems.

---

## 👤 1. Who Are You?

```bash
whoami
```

- Shows current logged-in username

```bash
id
```

- Shows user ID (UID), group ID (GID), and all group memberships

---

## 👥 2. Add New User

```bash
sudo adduser newuser
```

- Adds user with home directory and prompts for password

---

## 👥 3. Modify User

### A. Add User to Group

```bash
sudo usermod -aG groupname username
```

Example:

```bash
sudo usermod -aG docker kiran
```

> `-aG` means append to group (don’t remove existing groups)

---

## 👥 4. View Group Membership

```bash
groups username
```

- Shows groups the user belongs to

---

## 👥 5. Create a Group

```bash
sudo groupadd devs
```

---

## 👥 6. Change User Password

```bash
sudo passwd username
```

---

## 🧪 7. Test User Permissions

Switch to another user (if allowed):

```bash
su - username
```

---

## 🔐 8. Grant Sudo Access

To add user to sudoers:

```bash
sudo usermod -aG sudo username
```

Or edit sudoers safely:

```bash
sudo visudo
```

---

## 📋 9. Useful Files

| File Path          | Description                        |
|--------------------|------------------------------------|
| `/etc/passwd`      | All system users                   |
| `/etc/shadow`      | Encrypted passwords (root only)    |
| `/etc/group`       | System groups                      |
| `/etc/sudoers`     | Sudo privileges (edit with visudo) |

---

## 📌 Summary

| Task                        | Command                             |
|-----------------------------|--------------------------------------|
| Who am I?                   | `whoami`, `id`                      |
| Create user                 | `adduser username`                  |
| Add user to group           | `usermod -aG group user`            |
| View groups                 | `groups user`                       |
| Set or change password      | `passwd username`                   |
| View system users/groups    | `cat /etc/passwd`, `/etc/group`     |
| Switch user                 | `su - user`                         |

---

