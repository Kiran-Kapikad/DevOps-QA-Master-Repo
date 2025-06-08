
# 04 - Linux Process Management (Full Guide)

This file covers how to view, manage, and control processes in a Linux environment. Knowing how to monitor and manipulate processes is essential for DevOps, QA, and sysadmin roles.

---

## ⚙️ 1. What is a Process?

A process is a running instance of a program or command. Each process has:
- A unique **Process ID (PID)**
- A **parent process**
- Resource allocations (CPU, memory)

---

## 🔍 2. View Running Processes

### A. Using `ps`

```bash
ps aux
```

- `a` → show processes for all users
- `u` → show user-oriented format
- `x` → show processes not attached to a terminal

### B. Using `top`

```bash
top
```

- Real-time view of CPU/memory usage
- Press `q` to quit
- Press `k` then enter PID to kill

### C. Using `htop` (advanced)

```bash
htop
```

- Colorful, user-friendly `top` alternative
- Navigate using arrow keys
- Requires installation: `sudo apt install htop`

---

## 🆔 3. Get Specific Process by Name

```bash
ps aux | grep nginx
```

Or use:

```bash
pgrep nginx
```

---

## 🛑 4. Killing Processes

### A. Kill by PID

```bash
kill <PID>
```

### B. Force Kill (SIGKILL)

```bash
kill -9 <PID>
```

### C. Kill by Name

```bash
pkill -f process_name
```

Example:

```bash
pkill -f node
```

---

## 🚀 5. Running Jobs in Background

### A. Run in Background

```bash
sleep 60 &
```

### B. View Background Jobs

```bash
jobs
```

### C. Bring Job to Foreground

```bash
fg %1
```

### D. Move Job to Background

```bash
bg %1
```

---

## 🛠 6. Process States

| State | Code | Description                  |
|-------|------|------------------------------|
| R     | Running                            |
| S     | Sleeping                           |
| T     | Stopped (e.g., by Ctrl+Z)          |
| Z     | Zombie (process completed but not cleaned up) |
| D     | Uninterruptible sleep (usually IO wait) |

---

## 🧪 7. Useful Commands

```bash
ps -ef                    # Full format process list
ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu  # Sorted view
top -u username           # Top for a specific user
killall firefox           # Kill all processes by name
```

---

## 📌 Summary

| Task                      | Command Example                  |
|---------------------------|----------------------------------|
| View processes            | `ps aux`, `top`, `htop`          |
| Kill a process            | `kill PID`, `kill -9 PID`        |
| Run in background         | `command &`                      |
| View background jobs      | `jobs`                           |
| Resume job                | `fg %1`, `bg %1`                  |
| Kill by name              | `pkill -f name`, `killall name`  |
| Find by name              | `ps aux | grep name`, `pgrep`    |

---

