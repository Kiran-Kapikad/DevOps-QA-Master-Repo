
# 05 - Linux Package Management (Full Guide)

This file covers package managers used to install, update, remove, and search software packages in Linux.

---

## 📦 1. What is a Package Manager?

A package manager automates the process of:
- Installing software
- Resolving dependencies
- Updating or removing packages

Different distributions use different tools.

---

## 🐧 2. Package Managers by Distribution

| Distribution | Package Manager | File Type     |
|--------------|------------------|---------------|
| Ubuntu/Debian | `apt`, `dpkg`    | `.deb`        |
| RHEL/CentOS   | `yum`, `dnf`, `rpm` | `.rpm`    |
| Arch Linux    | `pacman`         | `.pkg.tar.zst` |
| All distros   | `snap`, `flatpak` | Universal     |

---

## 🧰 3. APT (Ubuntu/Debian)

### A. Update Package Lists

```bash
sudo apt update
```

### B. Upgrade Installed Packages

```bash
sudo apt upgrade
```

### C. Install a Package

```bash
sudo apt install nginx
```

### D. Remove a Package

```bash
sudo apt remove nginx
```

### E. Search for a Package

```bash
apt search curl
```

### F. List Installed Packages

```bash
dpkg -l
```

---

## 🧰 4. YUM / DNF (CentOS, RHEL)

### A. Install a Package

```bash
sudo yum install httpd
```

or (for newer systems)

```bash
sudo dnf install httpd
```

### B. Remove a Package

```bash
sudo yum remove httpd
```

### C. Update All Packages

```bash
sudo yum update
```

### D. Search for a Package

```bash
yum search nginx
```

---

## 📦 5. Snap (Universal)

Install `snapd` if not already installed:

```bash
sudo apt install snapd
```

### A. Find a Package

```bash
snap find code
```

### B. Install a Package

```bash
sudo snap install code --classic
```

### C. Remove a Package

```bash
sudo snap remove code
```

---

## 📦 6. Flatpak (Optional Alternative)

```bash
flatpak install flathub org.gimp.GIMP
flatpak run org.gimp.GIMP
```

---

## 🧪 7. Check Package Version

```bash
apt show nginx
yum info nginx
snap info code
```

---

## 📌 Summary

| Task                     | Command                             |
|--------------------------|--------------------------------------|
| Install a package        | `apt install`, `yum install`         |
| Remove a package         | `apt remove`, `yum remove`           |
| Update all packages      | `apt upgrade`, `yum update`          |
| Search for packages      | `apt search`, `yum search`           |
| View installed packages  | `dpkg -l`, `yum list installed`      |
| Snap install             | `snap install name --classic`        |

---

