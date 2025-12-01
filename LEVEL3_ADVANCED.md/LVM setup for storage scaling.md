## 📌 3. LVM Setup for Storage Scaling (Logical Volume Management)

### **3.1 Identify Disks**

```bash
lsblk
```

### **3.2 Create Physical Volume (PV)**

```bash
sudo pvcreate /dev/sdb
```

### **3.3 Create Volume Group (VG)**

```bash
sudo vgcreate appdata /dev/sdb
```

### **3.4 Create Logical Volume (LV)**

```bash
sudo lvcreate -L 20G -n applv appdata
```

### **3.5 Format LV**

```bash
sudo mkfs.ext4 /dev/appdata/applv
```

### **3.6 Mount LV**

```bash
sudo mkdir /mnt/appdata
sudo mount /dev/appdata/applv /mnt/appdata
```

### **3.7 Auto-mount in `/etc/fstab`**

Add line:

```
/dev/appdata/applv  /mnt/appdata   ext4   defaults   0   0
```

### **3.8 Extend LV (Scaling Storage)**

```bash
sudo lvextend -L +10G /dev/appdata/applv
sudo resize2fs /dev/appdata/applv
```

---
