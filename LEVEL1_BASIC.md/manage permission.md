## 📌 2. File & Directory Permissions

### **Apply Correct Ownership**

```bash
sudo chown -R devuser1:dev /var/www/app
```

### **Use Groups for Collaboration**

```bash
sudo chmod -R 770 /var/www/app
```

### **Manage Directory ACLs (setfacl)**

Grant dev group RWX:

```bash
sudo setfacl -m g:dev:rwx /var/www/app
```

Grant ops group read-only:

```bash
sudo setfacl -m g:ops:rx /var/www/app
```

Check ACL:

```bash
getfacl /var/www/app
```

### **Understanding umask**

Temporary:

```bash
umask 022
```

Permanent (add to `/etc/profile` or `~/.bashrc`):

```bash
umask 002
```

---
