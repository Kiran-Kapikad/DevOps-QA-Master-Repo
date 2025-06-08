# 02 - File and Directory Operations

This section covers essential file and directory commands used in everyday Linux work.

---

## 📄 Creating Files

| Command                  | Description                          |
|--------------------------|--------------------------------------|
| `touch file.txt`         | Create an empty file                 |
| `nano file.txt`          | Open file in terminal editor         |
| `cat > file.txt`         | Create file with content (Ctrl+D to save) |

---

## 📁 Creating Directories

| Command                        | Description                             |
|--------------------------------|-----------------------------------------|
| `mkdir myfolder`               | Create a new directory                  |
| `mkdir -p parent/child`        | Create nested directories               |

---

## 🔁 Copying Files & Folders

| Command                             | Description                             |
|-------------------------------------|-----------------------------------------|
| `cp file.txt backup.txt`            | Copy file                               |
| `cp -r folder/ new_folder/`         | Copy folder and contents                |

---

## 🔀 Moving and Renaming

| Command                             | Description                             |
|-------------------------------------|-----------------------------------------|
| `mv file.txt /other/location/`      | Move file to a new location             |
| `mv oldname.txt newname.txt`        | Rename a file                           |

---

## ❌ Deleting Files & Folders

| Command                             | Description                             |
|-------------------------------------|-----------------------------------------|
| `rm file.txt`                       | Delete a file                           |
| `rm -r folder/`                     | Delete a directory and contents         |
| `rm -rf folder/`                    | Force delete without prompt             |

---

## 🔍 Viewing File Content

| Command                        | Description                                |
|--------------------------------|--------------------------------------------|
| `cat file.txt`                 | Show file content                          |
| `less file.txt`                | View with scroll (Q to quit)               |
| `head -n 10 file.txt`          | View first 10 lines                        |
| `tail -n 10 file.txt`          | View last 10 lines                         |
| `tail -f /var/log/syslog`      | Real-time log monitoring                   |

---

## 🔎 Finding Files

```bash
find . -name "*.log"         # Find all .log files under current folder
find /etc -type f -name "hosts"

