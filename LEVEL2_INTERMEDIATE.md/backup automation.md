## 📌 1. Automate Backups with Cron

### **Create Backup Script**

Create `/usr/local/bin/backup.sh`:

```bash
#!/bin/bash
SOURCE="/var/www/app"
DEST="/backup/app-$(date +%F).tar.gz"
tar -czf "$DEST" "$SOURCE"
```

Make it executable:

```bash
sudo chmod +x /usr/local/bin/backup.sh
```

### **Schedule with Cron**

Edit crontab:

```bash
crontab -e
```

Run backup every day at 2AM:

```
0 2 * * * /usr/local/bin/backup.sh >> /var/log/backup.log 2>&1
```

View logs:

```bash
cat /var/log/backup.log
```

---
