## 📌 1. Create Custom Systemd Service

### **1.1 Create a systemd Unit File**

Create `/etc/systemd/system/myapp.service`:

```ini
[Unit]
Description=My Application Service
After=network.target

[Service]
User=appuser
Group=app
WorkingDirectory=/var/www/myapp
ExecStart=/usr/bin/java -jar myapp.jar
Restart=always
RestartSec=5
EnvironmentFile=/etc/myapp/myapp.env

[Install]
WantedBy=multi-user.target
```

### **1.2 Reload, Enable, and Start Service**

```bash
sudo systemctl daemon-reload
sudo systemctl enable myapp
sudo systemctl start myapp
```

### **1.3 Check Logs**

```bash
journalctl -u myapp -f
```

---
