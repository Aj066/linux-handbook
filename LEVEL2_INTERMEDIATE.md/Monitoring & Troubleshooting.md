## 📌 4. Monitor System Performance & Troubleshoot Services

### **Monitor CPU, RAM, and Processes**

```bash
top
htop
vmstat 2 10
free -h
```

### **Check Disk I/O**

```bash
iotop
iostat
```

### **Network Monitoring**

```bash
ss -tulpn
netstat -plnt
```

### **Troubleshoot Services**

```bash
systemctl status nginx
systemctl restart nginx
journalctl -u nginx -b
```

### **Check System Load**

```bash
uptime
```

### **Check Running Services**

```bash
systemctl list-units --type=service
```

---
