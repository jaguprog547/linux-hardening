# Linux System Hardening Project 🔐.
## Objective
This project demonstrates how to secure a Linux (Ubuntu) system by applying fundamental cybersecurity practices.
## System Update
Performed a full system update to ensure all packages are patched and protected against known vulnerabilities.
Commands used:
sudo apt update && sudo apt upgraded -y
## User Management
Created a new user and assigned appropriate privileges. Avoided direct use of the root account to improve security and applied the principle of least privilege.

Commands used: 
sudo adduser securityuser
sudo usermod -aG sudo securityuser
cat /etc/passwd
#note: After adding a user to the sudo group, a new session is required for the chages to take effect.
## Tools Used
- Ubuntu Linux
- Terminal
- Linux user management tools

## Key Learnings
- Importance of keeping systems updated
- Managing user access securely
- Applying least privilege principle

  ##. Dynamic Security with Fail2ban (IPS)
Installed and configured **Fail2ban** to act as a Host-based Intrusion Prevention System (HIPS), automatically banning suspicious IPs at the firewall level.

## 🛠️ Case Study: Resilience & Troubleshooting (Maintaining Availability)
During the security tools installation phase, the system experienced a critical storage failure that interrupted the package manager. Below is the disaster recovery process implemented:

### **The Challenge**
- **Error:** `E: Write error - write (28: No space left on device)`
- **Impact:** Broken dependencies (`Unmet dependencies`) and a locked `dpkg` manager. This compromised the **Availability** of the system to implement further security measures.

### The Solution (Disaster Recovery Workflow)**
To restore the operating system's integrity, the following technical steps were taken:

1. **Storage Cleanup:**
   ```bash
   sudo apt clean
2. Repairing the Locked Package Manager:
   sudo dpkg --configure -a
3.  Resolving Broken Dependencies & Finalizing Installation:
   sudo apt --fix-broken install -y
   sudo apt install fail2ban -y
