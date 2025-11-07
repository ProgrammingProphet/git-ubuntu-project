
# Virtual Machine Setup with Ubuntu & Git (Azure / AWS)

This project demonstrates how to create and configure a Virtual Machine (VM) using Azure or AWS, connect to it via SSH, install Git, initialize a Git repository, and clone a repository from GitHub.  
This practical helps students understand basic cloud VM setup and version control operations.

---

## 👤 Author
**Aditya Vishwakarma**  
GitHub: https://github.com/ProgrammingProphet

---

## 🎯 Objective
- Create and configure a virtual machine (VM)
- Install and configure Git
- Initialize a Git repository and push it to GitHub
- Clone an existing GitHub repository into the VM

---

## 🧠 Skills Developed
| Skill | Description |
|------|-------------|
| Cloud VM Setup | Creating and managing Ubuntu-based virtual machines |
| SSH Remote Access | Securely accessing servers using terminal |
| Git Basics | Installing, configuring, and using Git for version control |
| GitHub Collaboration | Managing remote repositories and cloning |

---

## 🏗️ Part A — Create Virtual Machine

### On **AWS**
1. Open **AWS Console → EC2 → Launch Instance**
2. Select **Ubuntu 22.04 LTS**
3. Instance type: `t2.micro` (Free Tier)
4. Enable **Auto-assign Public IP**
5. Set Security Group rules:
   - SSH (22) → Your IP
   - HTTP (80) → 0.0.0.0/0
6. Launch and download `.pem` key

### On **Azure**
1. Go to **Azure Portal → Virtual Machines → Create**
2. Select **Ubuntu 22.04 LTS**
3. Authentication: SSH Key
4. Networking:
   - Public IP: Enabled
   - Allow SSH (22) and HTTP (80)

---

## 🔗 Part B — Connect to VM

```bash
ssh -i yourkey.pem ubuntu@YOUR_PUBLIC_IP
````

---

## ⚙️ Part C — Install Git

```bash
sudo apt update -y
sudo apt install git -y
git --version
```

Configure your identity:

```bash
git config --global user.name "Aditya Vishwakarma"
git config --global user.email "adityasraazvishwakarma@gmail.com"
```

---

## 📁 Part D — Initialize Local Repo

```bash
mkdir vm-git-practical && cd vm-git-practical
echo "# VM + Git Practical" > README.md
git init
git add .
git commit -m "Initial commit"
```

---

## ☁️ Part E — Push to GitHub

```bash
git remote add origin git@github.com:ProgrammingProphet/git-ubuntu-project.git
git branch -M main
git push -u origin main
```

---

## 📥 Part F — Clone Any Repository

```bash
git clone https://github.com/ProgrammingProphet/REPO_NAME.git
```
