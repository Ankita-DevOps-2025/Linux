

- Config Files
    /etc/logrotate.conf
    /etc/logrotate.d/
- Log Files Location
    /var/log/

for more info and option - man logrotate    

# practical

mkdir /var/log/myapp
mkdir /var/log/myapp/archive
cd /var/log
touch my-app.log / touch /etc/logrotate.d/my-app.log
cd /etc/logrotate.d/
touch myapp 
edit ->
/var/log/myapp/*.log {
   daily
   size 10M
   olddir /var/log/myapp/archive
   compress
}

cd /var/log/myapp
truncate -s 15M my-app.log
ls -lh
logrotate -d /etc/logrotate.conf
logrotate /etc/logrotate.conf (to trigger manually)

systemctl status logrotate.timer (to see when it will do its next logrotation)

cd /etc/cron.daily/