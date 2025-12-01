## 📌 2. Shell Scripts for Automation

### **Log Cleanup Script**

`/usr/local/bin/log_cleanup.sh`:

```bash
#!/bin/bash
find /var/log -type f -mtime +7 -exec rm -f {} \;
```

Run monthly:

```
0 0 1 * * /usr/local/bin/log_cleanup.sh
```

---

### **Service Restart Script**

`/usr/local/bin/restart_service.sh`:

```bash
#!/bin/bash
SERVICE="nginx"
systemctl restart $SERVICE
systemctl status $SERVICE --no-pager
```

---

### **Health Check Script**

`/usr/local/bin/health_check.sh`:

```bash
#!/bin/bash
URL="http://localhost/health"
STATUS=$(curl -o /dev/null -s -w "%{http_code}" $URL)

if [ "$STATUS" -ne 200 ]; then
    echo "$(date): Health check failed (status $STATUS)" >> /var/log/health_check.log
    systemctl restart myapp
fi
```

Schedule every 5 minutes:

```
*/5 * * * * /usr/local/bin/health_check.sh
```

---

✔ **Level 3 (advanced production-ready Linux admin) in README format**
✔ **Full Level 1–3 combined 
