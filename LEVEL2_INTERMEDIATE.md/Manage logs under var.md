## 📌 3. Log Management (`/var/log`)

### **View Logs**

```bash
ls -l /var/log
```

### **Read Logs**

```bash
tail -f /var/log/syslog
tail -f /var/log/nginx/error.log
journalctl -u nginx -f
```

### **Search Within Logs**

```bash
grep -i "error" /var/log/syslog
grep -R "failed" /var/log
```

### **Rotate Logs Manually**

```bash
logrotate /etc/logrotate.conf
```

### **Clear Excess Logs**

```bash
sudo journalctl --vacuum-size=500M
sudo journalctl --vacuum-time=7d
```

---
