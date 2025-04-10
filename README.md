
---

## 🔐 **File Permissions and Access Rights in Linux**

Understanding Linux file permissions and ownership is **critical** for system security and access control.

---

### 🧮 **Numeric Representation of Permissions**

Each permission has a value:
- **Read (r)** = 4  
- **Write (w)** = 2  
- **Execute (x)** = 1  
- **No permission** = 0

Permissions are grouped into three user classes:
- **User (Owner)**
- **Group**
- **Others**

You sum up the values to represent each class's permissions.

#### 📌 Examples:
| Numeric | Symbolic | Meaning                | Use Case                           |
|---------|----------|------------------------|------------------------------------|
| 7       | rwx      | Read, write, execute   | Script file (owner access)         |
| 6       | rw-      | Read, write            | Config file (non-executable)       |
| 5       | r-x      | Read, execute          | Shared command tool or script      |

---

### 📄 **Symbolic (Shorthand) Representation**

User classes:
- **Owner (u)** – File creator
- **Group (g)** – Group of users
- **Others (o)** – Everyone else

File type indicators:
- `-` → regular file  
- `d` → directory  
- `l` → symbolic link  

Permission string format:  
`-rwxr-xr--`  
→ file type | user | group | others

**Hyphens (-)** indicate absence of permission.

---

### 🛠️ **Permission Management Commands**

#### ✅ `ls -latr`
List detailed information about files:
```bash
ls -latr
```

#### ✅ `chmod`
Used to **change permissions**.

**Symbolic:**
```bash
chmod +x script.sh        # Adds execute permission
chmod u+x script.sh       # Adds execute to owner only
```

**Numeric:**
```bash
chmod 755 script.sh       # rwxr-xr-x
chmod 777 note.txt        # rwxrwxrwx
```

#### ✅ `chown`
Used to **change ownership** of files/directories:
```bash
chown john:developer filename.txt
```

---

## 🔐 **Superuser Privileges**

Use `sudo` for one-time elevated privileges:
```bash
sudo command
```

Switch to root shell:
```bash
sudo -i
```

Exit root shell:
```bash
exit
```

---

## 👤 **User and Group Management**

### ✅ Create a User:
```bash
sudo adduser johndoe
```
Creates user and `/home/johndoe`.

### ✅ Give User Admin Rights:
```bash
sudo usermod -aG sudo johndoe
```

### ✅ Switch User:
```bash
su johndoe
```

### ✅ Change Password:
```bash
sudo passwd johndoe
```

---

## 👥 **Group Management**

### ✅ Create Group:
```bash
sudo groupadd developers
```

### ✅ Add User to Group:
```bash
sudo usermod -aG developers johndoe
```

---

## 📌 Tasks Checklist

✅ Create a file and modify permissions using `chmod`  
✅ Use `ls -latr` to inspect permissions  
✅ Create new users and switch between them  
✅ Assign users to groups  
✅ Use `chown` and `chmod` in practice  
✅ Practice privilege escalation with `sudo`

---

