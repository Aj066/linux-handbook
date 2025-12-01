## 📌 2. SSH Hardening (Security Best Practices)

### **2.1 Disable Root Login**

Edit SSH config:

```bash
sudo nano /etc/ssh/sshd_config
```

Set:

```
PermitRootLogin no
```

### **2.2 Disable Password Login**

```
PasswordAuthentication no
```

### **2.3 Change Default SSH Port**

```
Port 2222
```

### **2.4 Allow Only Specific Users**

```
AllowUsers devuser1 devuser2
```

Reload SSH:

```bash
sudo systemctl reload sshd
```

### **2.5 Configure Firewall to Allow New Port**

```bash
sudo ufw allow 2222/tcp
sudo ufw reload
```

---
