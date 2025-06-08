
# 07 - Linux System Information (Full Guide)

This file provides commands to check system-related information such as CPU, memory, disk, uptime, users, and more.

---

## 🖥️ 1. Operating System and Kernel

### A. OS Information

```bash
cat /etc/os-release
```

### B. Kernel Version

```bash
uname -r
uname -a     # Full system info
```

---

## 💾 2. Disk Usage

### A. Disk Space

```bash
df -h
```

- `-h` → human-readable (e.g., GB/MB)

### B. Disk Usage of a Folder

```bash
du -sh /path/to/folder
```

---

## 🧠 3. Memory Usage

### A. RAM Usage

```bash
free -h
```

- Shows total, used, free memory

### B. Top Memory-consuming Processes

```bash
ps aux --sort=-%mem | head
```

---

## ⚙️ 4. CPU Information

### A. Processor Details

```bash
lscpu
```

### B. CPU Load Average

```bash
uptime
```

- Shows current time, uptime, users, and load averages

---

## 🧑‍💻 5. Logged-in Users

```bash
who
w
```

---

## 👁️ 6. System Uptime

```bash
uptime
```

Shows how long the system has been running and average system load.

---

## 🔎 7. Process Tree View

```bash
pstree
```

---

## 📂 8. File System Info

```bash
mount          # Mounted file systems
lsblk          # Block devices
```

---

## 📌 Summary

| Task                      | Command                         |
|---------------------------|----------------------------------|
| OS Info                   | `cat /etc/os-release`           |
| Kernel Version            | `uname -r`, `uname -a`          |
| RAM Usage                 | `free -h`                       |
| Disk Usage                | `df -h`, `du -sh folder/`       |
| CPU Info                  | `lscpu`                         |
| Load Average              | `uptime`                        |
| Logged-in Users           | `who`, `w`                      |
| Process Tree              | `pstree`                        |

---

