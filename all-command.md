pwd           #Print current working directory
ls            #List directory contents
cd            #Change directory
cp            #Copy files or directories
mv            #Move or rename files/directories
rm            #Remove files or directories
mkdir         #Create a new directory
rmdir         #Remove empty directory
cat           #Display file contents
more          #View file page by page
less          #View file with navigation
head          #Show first few lines of a file
tail          #Show last few lines of a file
touch         #Create empty file or update timestamp
find          #Search for files in directory hierarchy
locate        #Find files using prebuilt database

chmod         #Change file permissions
chown         #Change file owner
chgrp         #Change group ownership
umask         #Set default permission mask

useradd       #Create a new user
usermod       #Modify user properties
userdel       #Delete a user account
passwd        #Change user password
groupadd      #Create a new group
id            #Show user ID and groups
whoami        #Display current logged-in user

apt           #Package manager for Debian/Ubuntu
yum           #Package manager for RHEL/CentOS
dnf           #Modern package manager for RHEL/Fedora
rpm           #Low-level package manager (RHEL)
dpkg          #Low-level package manager (Debian)
snap          #Install/manage snap packages

systemctl     #Manage systemd services
service       #Start/stop services (legacy)
journalctl    #View logs from systemd

ps            #List running processes
top           #Show active processes in real-time
htop          #Interactive process viewer
kill          #Terminate process by PID
pkill         #Kill process by name
nice          #Start process with priority
renice        #Change priority of a running process
jobs          #List background jobs
fg            #Bring job to foreground
bg            #Run stopped job in background
&             #Run process in background

df            #Show disk space usage
du            #Display file/folder size
lsblk         #List block devices
fdisk         #Partition a disk
mkfs          #Create filesystem
mount         #Mount filesystem
umount        #Unmount filesystem
/etc/fstab    #Auto-mount configuration file

ip            #Show or configure network interfaces
ifconfig      #Display network config (legacy)
ping          #Test network connectivity
netstat       #Show network connections (legacy)
ss            #Display socket statistics
curl          #Transfer data from/to URL or API
wget          #Download files from web
traceroute    #Trace network route to destination
nslookup      #Query DNS records
dig           #DNS lookup utility
hostname      #Show or set system hostname
/etc/hosts    #Local hostname resolution file

ufw           #Manage firewall (Ubuntu)
firewalld     #Manage firewall (RHEL)
iptables      #Packet filtering firewall tool
ssh           #Securely connect to remote system
/etc/ssh/sshd_config  #SSH server configuration file

syslog        #System logging service (concept)
dmesg         #Kernel ring buffer messages
journalctl    #Show logs from systemd
tail          #View end of file (usually logs)
grep          #Search text patterns in files

crontab       #Schedule recurring tasks
at            #Schedule one-time task
sleep         #Pause for a specified duration

export        #Set environment variable
set           #Display shell variables
env           #Show environment variables
echo          #Print message or variable
.bashrc       #User shell configuration file
.profile      #User profile configuration
.bash_profile #Login shell configuration file

grep          #Search for text in files
awk           #Pattern scanning & text processing
sed           #Stream editor for find/replace
cut           #Extract sections from lines
sort          #Sort lines of text
uniq          #Remove duplicate lines
tr            #Translate or delete characters
wc            #Count lines, words, and characters
xargs         #Build commands from standard input

|             #Pipe output of one command into another
>             #Redirect output (overwrite)
>>            #Append redirected output
<             #Redirect input
2>            #Redirect error output
&>            #Redirect both output and error
/dev/null     #Discard unwanted output

tar           #Archive files
gzip          #Compress files
gunzip        #Decompress .gz files
zip           #Compress files into .zip
unzip         #Extract .zip files
scp           #Securely copy files between systems
rsync         #Efficiently sync files/directories

ssh           #Login to remote server
sftp          #Secure file transfer
ssh-keygen    #Generate SSH key pair
authorized_keys #Stores public keys for SSH login
known_hosts   #List of verified remote hosts

top           #Monitor processes in real time
htop          #Enhanced version of top
vmstat        #Display virtual memory stats
free          #Show memory usage
iostat        #Display I/O stats
sar           #System activity report
uptime        #Show system uptime and load average
dstat         #Display multiple system resources

rsync         #Backup/sync data between systems
scp           #Copy files between servers
tar           #Archive data for backup
dump          #Backup filesystem
restore       #Restore filesystem backup

ulimit        #Set or view resource limits
quota         #Show disk usage limits for users

getenforce    #Check SELinux mode
setenforce    #Set SELinux enforcing/permissive mode
/etc/selinux/config  #SELinux configuration file

systemctl status #Check service status
systemctl enable #Enable service at boot
systemctl start  #Start service manually
grub          #Bootloader configuration tool
init          #Legacy system initializer
systemd       #Modern init and service manager

ping          #Test host connectivity
traceroute    #Trace path to remote host
df            #Check available disk space
ps            #List processes
netstat       #Show network status and ports
journalctl -xe #Show detailed logs with errors
