## 📌 5. Implement Logrotate for Application Logs

### **5.1 Create Logrotate Rule**

Create `/etc/logrotate.d/myapp`:

```conf
/var/log/myapp/*.log {
    daily
    rotate 14
    compress
    missingok
    notifempty
    delaycompress
    create 640 appuser app
    sharedscripts
    postrotate
        systemctl restart myapp >/dev/null 2>&1 || true
    endscript
}
```

### **5.2 Test Logrotate**

```bash
sudo logrotate -d /etc/logrotate.conf
```

### **5.3 Force Rotation**

```bash
sudo logrotate -f /etc/logrotate.conf
```

---

## 📌 6. Additional Production Best Practices

### **Fail2ban Setup (Optional but Recommended)**

```bash
sudo apt install fail2ban -y
sudo systemctl enable --now fail2ban
```

### **Disable Unused Services**

```bash
systemctl disable avahi-daemon
systemctl disable cups
```

### **Monitor System Logs**

```bash
journalctl -xe
```

---
