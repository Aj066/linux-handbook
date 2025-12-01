## 📌 4. Firewall Configuration (UFW / Firewalld / iptables)

### **Using UFW (Ubuntu)**

#### Allow Ports

```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw allow 2222/tcp
```

#### Deny Everything Else

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

#### Enable Firewall

```bash
sudo ufw enable
```

---

### **Using Firewalld (RHEL/CentOS)**

#### Allow Services

```bash
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
```

#### Allow Custom Port

```bash
sudo firewall-cmd --permanent --add-port=2222/tcp
```

Reload:

```bash
sudo firewall-cmd --reload
```

---

### **iptables Rule Example**

```bash
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT
sudo iptables -A INPUT -j DROP
```

Persist rules:

```bash
sudo netfilter-persistent save
```

---
