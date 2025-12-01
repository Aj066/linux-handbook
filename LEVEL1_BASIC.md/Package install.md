## 📌 3. Install & Manage Essential Packages

### **Update System Packages**

**Ubuntu/Debian**

```bash
sudo apt update && sudo apt upgrade -y
```

**RHEL/CentOS**

```bash
sudo dnf update -y
```

---

### **Install Required Software**

#### Git

```bash
sudo apt install git -y
sudo dnf install git -y
```

#### Nginx

```bash
sudo apt install nginx -y
sudo systemctl enable --now nginx
```

#### Java (OpenJDK)

```bash
sudo apt install openjdk-17-jdk -y
sudo dnf install java-17-openjdk -y
```

#### Curl & Vim

```bash
sudo apt install curl vim -y
sudo dnf install curl vim-enhanced -y
```

---

### **Add Repositories (Examples)**

#### Add Node.js repo:

```bash
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install nodejs -y
```

#### Add Docker repo:

```bash
sudo apt install ca-certificates curl -y
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
  | sudo tee /etc/apt/keyrings/docker.gpg > /dev/null
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" \
| sudo tee /etc/apt/sources.list.d/docker.list

sudo apt update
```

---

### **Validate Package Integrity**

```bash
sha256sum filename.deb
```

Compare output against vendor checksums.

---
