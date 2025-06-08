
# 06 - Linux Networking Commands (Full Guide)

This file covers essential Linux networking commands used to troubleshoot, configure, and monitor networks.

---

## 🌐 1. Check Connectivity

### A. Ping a Website or IP

```bash
ping google.com
```

- Press `Ctrl + C` to stop
- Use `-c` to limit pings:

```bash
ping -c 4 google.com
```

---

## 🌐 2. View Network Interfaces

### A. Using `ifconfig` (older systems)

```bash
ifconfig
```

### B. Using `ip` (modern alternative)

```bash
ip addr show
ip link show
```

---

## 🌐 3. View Routing Table

```bash
route -n         # Older
ip route         # Modern
```

---

## 🔌 4. DNS Resolution

### A. Check DNS info

```bash
nslookup google.com
```

### B. Test DNS with `dig`

```bash
dig google.com
```

> Note: You may need to install `dnsutils` first:
```bash
sudo apt install dnsutils
```

---

## 📡 5. View Open Ports

```bash
netstat -tuln          # TCP/UDP listening ports
ss -tuln               # Recommended modern tool
```

---

## 🔁 6. Test HTTP Requests

### A. Using `curl`

```bash
curl https://example.com
```

### B. Using `wget`

```bash
wget https://example.com
```

---

## 🔐 7. SSH Access

### A. SSH into a Remote Server

```bash
ssh username@hostname
```

### B. SSH with Custom Port

```bash
ssh -p 2222 user@hostname
```

---

## 📥 8. Download Files

```bash
wget https://example.com/file.zip
curl -O https://example.com/file.zip
```

---

## 🔧 9. Network Troubleshooting Tools

| Tool     | Use Case                          |
|----------|-----------------------------------|
| `ping`   | Check connectivity                |
| `traceroute` | View path to remote host     |
| `netstat` / `ss` | View ports and connections |
| `nmap`   | Scan open ports (requires install)|
| `tcpdump` | Capture network packets          |

---

## 📌 Summary

| Task                    | Command Example                  |
|-------------------------|----------------------------------|
| Check connectivity      | `ping`, `traceroute`             |
| View interfaces         | `ip addr`, `ifconfig`            |
| View routing table      | `ip route`, `route -n`           |
| Open ports              | `ss -tuln`, `netstat -tuln`      |
| DNS resolution          | `nslookup`, `dig`                |
| HTTP request testing    | `curl`, `wget`                   |
| Remote login            | `ssh user@host`                  |

---

