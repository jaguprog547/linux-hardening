# Linux System Hardening Project 🔐
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
