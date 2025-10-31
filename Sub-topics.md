========================
# LINUX — COMPLETE NOTES
========================

1. LINUX BASICS & ARCHITECTURE
------------------------------
Concepts: Kernel vs Shell vs User space, distributions, boot process
Keywords: Kernel, Shell, init, systemd, tty, grub, runlevel, /etc, /bin, /usr, /var, /home
Logic: Kernel interacts with hardware; Shell interprets commands; systemd/init manages services at boot

2. FILE SYSTEM STRUCTURE
------------------------
Concepts: Linux directory hierarchy
Keywords: /etc, /bin, /usr, /var, /tmp, /opt, /root, /home
Logic: /etc config, /var logs, /usr binaries, /tmp temp, /opt optional software

3. BASIC COMMANDS
-----------------
Concepts: Navigation & file management
Keywords: pwd, ls, cd, cp, mv, rm, mkdir, rmdir, cat, more, less, head, tail, touch, find, locate
Logic: Explore dirs, view/manipulate files, combine with |, grep, >, >>, <

4. FILE PERMISSIONS & OWNERSHIP
-------------------------------
Concepts: Users, groups, permissions
Keywords: chmod, chown, chgrp, umask, rwx, 777, root, sudo
Logic: Owner/Group/Others, r=4,w=2,x=1, e.g. -rwxr-xr--

5. USER & GROUP MANAGEMENT
--------------------------
Concepts: Manage users/groups
Keywords: useradd, usermod, userdel, passwd, groupadd, id, whoami, /etc/passwd, /etc/group
Logic: UID, home, shell; groups define access boundaries

6. PACKAGE MANAGEMENT
---------------------
Concepts: Install/remove/update software
Keywords: apt, yum, dnf, rpm, dpkg, snap
Logic: Debian/Ubuntu: apt install nginx; RHEL/CentOS: yum install nginx

7. SYSTEM SERVICES & DAEMONS
----------------------------
Concepts: Manage background services
Keywords: systemctl, service, systemd, journalctl, enable, start, stop, status
Logic: systemd manages services
Example:
systemctl enable nginx
systemctl start nginx
systemctl status nginx

8. PROCESS MANAGEMENT
---------------------
Concepts: Monitor/manage processes
Keywords: ps, top, htop, kill, pkill, nice, renice, jobs, fg, bg, &
Logic: PID per process; foreground/background; kill -9 PID to force terminate

9. DISK/STORAGE & FILESYSTEM
----------------------------
Concepts: Manage disks/partitions/filesystems
Keywords: df, du, lsblk, fdisk, mkfs, mount, umount, /etc/fstab, swap
Logic:
df -h → disk usage
du -sh * → folder size
mount /dev/xvdf /data

10. NETWORKING & TROUBLESHOOTING
--------------------------------
Concepts: Network config & connectivity
Keywords: ip, ifconfig, ping, netstat, ss, curl, wget, traceroute, nslookup, dig, hostname, /etc/hosts
Logic:
ip addr show → check IP
nslookup google.com → DNS test
ss -tuln → listening ports

11. FIREWALL & SECURITY
-----------------------
Concepts: Network access control
Keywords: ufw, firewalld, iptables, sudo, ssh, /etc/ssh/sshd_config
Logic:
ufw allow 22/tcp
ufw deny 80/tcp
Secure SSH: key-based, disable root

12. LOG MANAGEMENT
-----------------
Concepts: Monitor system/app logs
Keywords: /var/log, syslog, dmesg, journalctl, tail -f, grep
Logic:
tail -f /var/log/syslog
journalctl -xe

13. CRON JOBS & SCHEDULING
--------------------------
Concepts: Automate tasks
Keywords: crontab, /etc/cron.d, /etc/cron.daily, at, sleep
Logic:
* * * * * user command
0 2 * * * /usr/local/bin/backup.sh

14. ENVIRONMENT VARIABLES & SHELL
---------------------------------
Concepts: Manage env & shell configs
Keywords: export, set, env, .bashrc, .profile, .bash_profile, $PATH
Logic:
export APP_ENV=dev
echo $APP_ENV

15. TEXT PROCESSING & FILTERING
-------------------------------
Concepts: Search/manipulate text
Keywords: grep, awk, sed, cut, sort, uniq, tr, wc, xargs
Logic:
grep "error" /var/log/syslog
awk '{print $1,$2,$5}' data.txt
sed 's/old/new/g' file.txt

16. REDIRECTION & PIPES
-----------------------
Concepts: Combine/redirect outputs
Keywords: |, >, >>, <, 2>, &>, /dev/null
Logic:
cat file.txt | grep "hello" > result.txt

17. COMPRESSION & ARCHIVING
---------------------------
Concepts: Backup/transfer files
Keywords: tar, gzip, gunzip, zip, unzip, scp, rsync
Logic:
tar -czvf backup.tar.gz /var/www/
rsync -avz source/ user@remote:/backup/

18. SSH & REMOTE ACCESS
----------------------
Concepts: Secure remote access
Keywords: ssh, scp, sftp, ssh-keygen, authorized_keys, known_hosts
Logic:
ssh user@server
scp file.txt user@server:/tmp/

19. SYSTEM MONITORING & PERFORMANCE
----------------------------------
Concepts: CPU, memory, resources
Keywords: top, htop, vmstat, free, iostat, sar, uptime, dstat
Logic:
top → processes
free -m → memory
uptime → load

20. SHELL SCRIPTING BASICS
--------------------------
Concepts: Automate tasks
Keywords: #!/bin/bash, variables, if, for, while, case, functions
Logic:
#!/bin/bash
for file in *.log; do
  echo "Processing $file"
done

21. BACKUP & RECOVERY
---------------------
Concepts: Backup/restore
Keywords: rsync, scp, tar, cron, snapshot, dump, restore
Logic: Schedule backups via cron, store remotely

22. DISK QUOTA & RESOURCE MGMT
------------------------------
Concepts: Limit user resources
Keywords: ulimit, quota, df, du
Logic: Prevent users from filling disk space

23. SELINUX & APPARMOR
---------------------
Concepts: Security access control
Keywords: SELinux, getenforce, setenforce, /etc/selinux/config
Logic: Mandatory Access Control policies

24. SYSTEM STARTUP & BOOT
-------------------------
Concepts: Boot sequence
Keywords: BIOS, bootloader, kernel, init, systemd, target, grub
Logic: BIOS → GRUB → Kernel → init/systemd → login shell

25. TROUBLESHOOTING
------------------
Concepts: Identify/fix issues
Keywords: dmesg, journalctl, systemctl, ping, traceroute, df, ps, netstat
Logic: Check logs/system state; combine info to find root cause
