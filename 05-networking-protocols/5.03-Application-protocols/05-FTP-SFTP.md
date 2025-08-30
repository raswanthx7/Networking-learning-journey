# FTP vs SFTP

##  Topics Covered
- What is FTP?
- Why FTP is used?
- How FTP works
- FTP Modes
- FTP Commands
- Real-world FTP Usage
- Limitations of FTP
- What is SFTP?
- Why SFTP is used?
- How SFTP works
- SFTP Commands
- Real-world SFTP Usage
- FTP vs SFTP Comparison Table
- Modern Alternatives (Cloud/CI-CD)

---

##  What is FTP?
- FTP = **File Transfer Protocol**
- Used for transferring files between client and server
- Works on **TCP port 21**

### Why FTP is used?
- Upload website files (HTML, CSS, JS, images)
- Download files from server
- Manage remote files (rename, delete, move)

### How FTP Works
1. Client connects to FTP server  
2. Authentication (username/password)  
3. Transfer files between local ↔ remote  

### FTP Modes
- **Active Mode**: Server connects back to client  
- **Passive Mode**: Client connects to server (preferred when firewall is present)  

### FTP Commands
- `open <server-ip>` → Connect to FTP server  
- `ls` / `dir` → List files  
- `get filename` → Download file  
- `put filename` → Upload file  
- `mget *` → Download multiple files  
- `bye` → Exit  

### Real-world FTP Usage
- Legacy web hosting (upload website files)  
- File sharing in old systems  
- Testing network file transfers  

### Limitations of FTP
- **No encryption** (username & password visible in plain text)  
- Insecure for sensitive data  
- Rarely used in modern cloud environments  

---

##  What is SFTP?
- SFTP = **Secure File Transfer Protocol** (over SSH)  
- Runs on **port 22** (same as SSH)  
- Provides **encryption** and secure authentication  

### Why SFTP is used?
- Protects sensitive data during transfer  
- Supports password and SSH key authentication  
- Standard in **cloud/server environments**  

### How SFTP Works
1. Connect with SSH (`sftp user@server`)  
2. Authenticate (password or SSH key)  
3. Transfer files securely  

### SFTP Commands
- `ls` → List files (remote)  
- `pwd` → Show current remote directory  
- `lpwd` → Show current local directory  
- `cd folder` → Change remote directory  
- `lcd folder` → Change local directory  
- `put file.txt` → Upload file  
- `get file.txt` → Download file  
- `bye` → Exit session  

### Real-world SFTP Usage
- Uploading website/app files to **cloud servers** (EC2, DigitalOcean, Azure VM)  
- Transferring **backups, logs, databases** securely  
- Automated secure data exchange between systems  

---

##  FTP vs SFTP Comparison

| Feature        | FTP                        | SFTP (SSH File Transfer)        |
|----------------|----------------------------|---------------------------------|
| Security       |  No encryption            |  Encrypted via SSH            |
| Port           | 21                         | 22                              |
| Authentication | Username/Password          | Username/Password or SSH Keys   |
| Data Safety    | Insecure                   | Secure                          |
| Usage Today    | Rare (legacy)              | Common (cloud & IT companies)   |

---

##  Modern Alternatives (Cloud/CI-CD)
- Instead of FTP/SFTP manual upload:  
  - **CI/CD Pipelines** (GitHub Actions, GitLab, Jenkins)  
  - **AWS S3 hosting** + CloudFront  
  - **Azure Blob Storage / GCP Storage Buckets**  
- Faster, automated, and more secure  

---

