# Basic Notes for DBA and Linux Commands

## 🔍 System Information Commands
- `ifconfig` - Display network configuration.
- `hostname` - Show the system's hostname.
- `uname -a` - Display kernel and system information.
- `lscpu` - Show CPU architecture information.
- `free -h` - Display available and used memory in human-readable format.
- `cat /etc/group` - List all groups and their members.

---

## 📊 Monitoring and Performance
- `top` - Monitor real-time system processes.
- `iostat` - Report CPU and I/O statistics.
- `vmstat` - Display system performance information.

---

## 🧩 Check User Privileges in Oracle
```sql
-- Check Role Privileges
SELECT * FROM DBA_ROLE_PRIVS WHERE grantee = 'USERNAME';

-- Check System Privileges
SELECT * FROM DBA_SYS_PRIVS WHERE grantee = 'USERNAME';

🖥️ Shell Script to Create Directories and Pfile
#!/bin/bash

# Create directories
mkdir -p coldclo/admin/{pfile,adump,diag} coldclo/oradata/{data,control,log,arch}

# Create and populate the parameter file
cat <<EOF > clone/admin/pfile/initclone.ora
dbname=clone
EOF

# Connect to Oracle using SQL*Plus
sqlplus sys/sys@dev as sysdba

📧 Send Mail from Linux
/usr/sbin/sendmail -t mail < /file/location
