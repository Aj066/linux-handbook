## 📌 4. System Information & Validation

### **Check CPU Info**

```bash
lscpu
cat /proc/cpuinfo
```

### **Check RAM**

```bash
free -h
cat /proc/meminfo
```

### **Check Disks**

```bash
df -h
lsblk
```

### **Inspect Running Processes**

```bash
top
```

Install & run htop:

```bash
sudo apt install htop -y
htop
```

List processes:

```bash
ps aux | grep service-name
```

---
