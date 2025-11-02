egrep -i "error|warning" file.logs
grep -i "error" file.logs
cat error.log | grep -i "error" | wc -l
cat error.log | grep -i "error" > myfile.logs
cat filename | more (use "enter" to go down)
can't to serch in "more" command
# Linux Log Monitoring 

cd /var/log/
Important files - boot, chron, secure, maillog, httpd(access_log,error_log), messages 

# less
less filename 
to serch word - /word
go to bottom - shift + g 
go to top - p
serch word from bottom to top - ?word  (use "n" to serch for next appearence of that word)
to come out - q

# for live logs 
tail -f filename

# File discriptors (default one is 0)
stdin(0) stdout(1) stderr(2)
for both stdout stderr discriptor - &
> redirect (overide)
>> append

echo "Hello" > myfile 
cd /root/ 2> error.txt (only redirect error)
ls hghhg &>> error.txt (redirect both stdout stderr)
cd /root/ > error.txt2>&1

cat < file.txt  (input is used when feeding file content to file)

ifconfig - to find my ip detail