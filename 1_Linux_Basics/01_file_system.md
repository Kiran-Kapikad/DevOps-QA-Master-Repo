# 01 - Linux File System Basics

This file covers the basic structure of the Linux file system and how to navigate it using common terminal commands.

---

## 📂 Linux Directory Structure

| Directory | Description |
|-----------|-------------|
| `/`       | Root of the file system |
| `/home`   | User home directories (e.g., `/home/kiran`) |
| `/etc`    | Configuration files for system and apps |
| `/bin`    | Essential system binaries (commands like `ls`, `cp`) |
| `/sbin`   | System administration binaries |
| `/var`    | Logs, mail, spool files |
| `/tmp`    | Temporary files (cleared on reboot) |
| `/usr`    | User-installed software and libraries |
| `/opt`    | Optional third-party software |
| `/dev`    | Device files (e.g., disks, USB) |
| `/proc`   | System and process information (virtual files) |

---

## 🧭 Navigation Commands

| Command       | Description |
|---------------|-------------|
| `pwd`         | Print working directory (shows current location) |
| `cd`          | Change directory (e.g., `cd /etc`) |
| `cd ..`       | Move one directory up |
| `cd ~`        | Go to home directory |
| `ls`          | List directory contents |
| `ls -l`       | Long listing (permissions, size, date) |
| `ls -a`       | Show hidden files (starting with `.`) |
| `ls -lh`      | Human-readable file sizes |

---

## 🛠️ Useful Tips

- Press `Tab` to auto-complete directory/file names.
- Use `cd -` to return to the previous directory.
- Use `clear` to clear the terminal screen.

---

## 📌 Summary

Mastering file system structure and navigation is essential for:
- Navigating servers and containers
- Troubleshooting file paths in scripts
- Working inside Jenkins, Docker, or K8s environments


