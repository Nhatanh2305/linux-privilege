#Linux detailed Enumeration–Commands<br>
<h1>&emsp;Operating System</h1>

<b1>&emsp;&emsp;&emsp;&emsp;What’s the distribution type? What version?</b1>
<p>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/issue<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/*-release<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/lsb-release # Debian based <br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/redhat-release # Redhat based</p><br><br>

<b1>&emsp;&emsp;&emsp;&emsp;What’s the kernel version? Is it 64-bit?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /proc/version<br>
&emsp;&emsp;&emsp;&emsp;&emsp;uname -a<br>
&emsp;&emsp;&emsp;&emsp;&emsp;uname -mrs<br>
&emsp;&emsp;&emsp;&emsp;&emsp;rpm -q kernel dmesg | grep Linux<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls /boot | grep vmlinuz-<br><br>

<b1>&emsp;&emsp;&emsp;&emsp;What can be learned from the environmental variables?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/profile<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/bashrc<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.bash_profile<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.bashrc<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.bash_logout env set<br><br>
<b1>&emsp;&emsp;&emsp;&emsp;Is there a printer?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;lpstat -a<br><br><br>
<h1>&emsp;Applications & Services</h1>
<b1>&emsp;&emsp;&emsp;&emspWhat services are running? Which service has which user privilege?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;ps aux<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ps -ef<br>
&emsp;&emsp;&emsp;&emsp;&emsp;top<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/services<br><br>

<b1>&emsp;&emsp;&emsp;What applications are installed? What version are they? Are they currently running?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /usr/bin/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /sbin/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;dpkg -l rpm -qa<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/cache/apt/archivesO<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/cache/yum/<br><br>

<b1>&emsp;&emsp;&emsp;Any of the service(s) settings misconfigured? Are any (vulnerable) plugins attached?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/syslog.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/chttp.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/lighttpd.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/cups/cupsd.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/inetd.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/apache2/apache2.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/my.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/httpd/conf/httpd.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /opt/lampp/etc/httpd.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -aRl /etc/ | awk '$1 ~ /^.*r.*/<br>
<b1>&emsp;&emsp;&emsp;What jobs are scheduled?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;crontab -l<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/spool/cron<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -al /etc/ | grep cron<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -al /etc/cron*<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/cron*<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/at.allow<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/at.deny<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/cron.allow<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/cron.deny<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/crontab<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/anacrontab<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/spool/cron/crontabs/root<br><br>
<b1>&emsp;&emsp;&emsp;Any plain text usernames and/or passwords?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;grep -i user [filename]<br>
&emsp;&emsp;&emsp;&emsp;&emsp;grep -i pass [filename]<br>
&emsp;&emsp;&emsp;&emsp;&emsp;grep -C 5 "password" [filename]<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find . -name "*.php" -print0 | xargs -0<br>
&emsp;&emsp;&emsp;&emsp;&emsp;grep -i -n "var $password" # Joomla<br><br>






<h1>&emsp;Communications & Networking</h1><br>
<b1>&emsp;&emsp;&emsp;What NIC(s) does the system have? Is it connected to another network?</b1><br>

&emsp;&emsp;&emsp;&emsp;&emsp;/sbin/ifconfig -a<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/network/interfaces<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/sysconfig/network<br><br>

<b1>&emsp;&emsp;&emsp;What are the network configuration settings? What can you find out about this network? DHCP server? DNS server? Gateway?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/resolv.conf<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/sysconfig/network<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/networks<br>
&emsp;&emsp;&emsp;&emsp;&emsp;iptables -L<br>
&emsp;&emsp;&emsp;&emsp;&emsp;hostname<br>
&emsp;&emsp;&emsp;&emsp;&emsp;dnsdomainname<br>
<b1>&emsp;&emsp;&emsp;What other users & hosts are communicating with the system?</b1><br>



&emsp;&emsp;&emsp;&emsp;&emsp;lsof -i<br>
&emsp;&emsp;&emsp;&emsp;&emsp;lsof -i :80<br>
&emsp;&emsp;&emsp;&emsp;&emsp;grep 80 /etc/services<br>
&emsp;&emsp;&emsp;&emsp;&emsp;netstat -antup<br>
&emsp;&emsp;&emsp;&emsp;&emsp;netstat -antpx<br>
&emsp;&emsp;&emsp;&emsp;&emsp;netstat -tulpn<br>
&emsp;&emsp;&emsp;&emsp;&emsp;chkconfig --list<br>
&emsp;&emsp;&emsp;&emsp;&emsp;chkconfig --list | grep 3:on last w<br><br>

<b1>&emsp;&emsp;&emsp;Whats cached? IP and/or MAC addresses</b1><br>

&emsp;&emsp;&emsp;&emsp;&emsp;arp -e route /sbin/route -nee<br><br>


<b1>&emsp;&emsp;&emsp;Is packet sniffing possible? What can be seen? Listen to live traffic</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;tcpdump tcp dst 192.168.1.7 80 and tcp dst 10.5.5.252 21<br><br>


<h1>&emsp;Confidential Information & Users</h1>
<b1>&emsp;&emsp;&emsp;Who are you? Who is logged in? Who has been logged in? Who else is there? Who can do what?</b1><br>

&emsp;&emsp;&emsp;&emsp;&emsp;id<br>
&emsp;&emsp;&emsp;&emsp;&emsp;who<br>
&emsp;&emsp;&emsp;&emsp;&emsp;w<br>
&emsp;&emsp;&emsp;&emsp;&emsp;last<br>

&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/passwd | cut -d: -f1<br>
&emsp;&emsp;&emsp;&emsp;&emsp;# List of users<br>

&emsp;&emsp;&emsp;&emsp;&emsp;grep -v -E "^#" /etc/passwd | awk -F: '$3 == 0 { print $1}' # List of super users<br>

&emsp;&emsp;&emsp;&emsp;&emsp;awk -F: '($3 == "0") {print}' /etc/passwd<br>
&emsp;&emsp;&emsp;&emsp;&emsp;# List of super users<br><br>

&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/sudoers sudo -l <br>
<b1>&emsp;&emsp;&emsp;What sensitive files can be found?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/passwd<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/group<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/shadow<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/mail/<br><br>

<b1>&emsp;&emsp;&emsp;Anything “interesting” in the home directories? If it’s possible to access</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -ahlR /root/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -ahlR /home/<br>

<b1>&emsp;&emsp;&emsp;Are there any passwords in; scripts, databases, configuration files or log files? Default paths and locations for passwords</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/apache2/config.inc<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/lib/mysql/mysql/user.MYD<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /root/anaconda-ks.cfg<br>
<b1>&emsp;&emsp;&emsp;What has the user is doing? Is there any password in plain text? What have they been editing?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.bash_history<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.nano_history<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.atftp_history<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.mysql_history<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.php_history<br><br>

<b1>&emsp;&emsp;&emsp;What user information can be found?</b1><br>


&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.bashrc<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.profile<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/mail/root<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/spool/mail/root<br><br>

<b1>&emsp;&emsp;&emsp;Can private-key information be found?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.ssh/authorized_keys<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.ssh/identity.pub<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.ssh/identity<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.ssh/id_rsa.pub<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.ssh/id_rsa<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.ssh/id_dsa.pub<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat ~/.ssh/id_dsa<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/ssh/ssh_config<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/ssh/sshd_config<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/ssh/ssh_host_dsa_key.pub<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/ssh/ssh_host_dsa_key<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/ssh/ssh_host_rsa_key.pub<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/ssh/ssh_host_rsa_key<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/ssh/ssh_host_key.pub<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/ssh/ssh_host_key<br><br>




<h1>&emsp;File Systems</h1><br>
<b1>&emsp;&emsp;&emsp;Which configuration files can be written in /etc/? Able to reconfigure a service?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -aRl /etc/ | awk '$1 ~ /^.*w.*/' 2>/dev/null # Anyone ls -aRl /etc/ | awk '$1 ~ /^..w/' 2>/dev/null # Owner<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -aRl /etc/ | awk '$1 ~ /^.....w/' 2>/dev/null # Group<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -aRl /etc/ | awk '$1 ~ /w.$/' 2>/dev/null # Other<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find /etc/ -readable -type f 2>/dev/null # Anyone<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find /etc/ -readable -type f -maxdepth 1 2>/dev/null # Anyone<br><br>

<b1>&emsp;&emsp;&emsp;What can be found in /var/?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/mail<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/spool<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/spool/lpd<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/lib/pgsql<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/lib/mysql<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/lib/dhcp3/dhclient.leases
<br>


<b1>&emsp;&emsp;&emsp;Any settings/files (hidden) on the website? Any settings file with database information?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alhR /var/www/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alhR /srv/www/htdocs/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alhR /usr/local/www/apache22/data/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alhR /opt/lampp/htdocs/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alhR /var/www/html/
<br>
<b1>&emsp;&emsp;&emsp;Is there anything in the log file(s) (Could help with “Local File Includes”!)</b1><br>

&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/httpd/logs/access_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/httpd/logs/access.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/httpd/logs/error_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /etc/httpd/logs/error.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/apache2/access_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/apache2/access.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/apache2/error_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/apache2/error.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/apache/access_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/apache/access.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/auth.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/chttp.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/cups/error_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/dpkg.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/faillog<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/httpd/access_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/httpd/access.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/httpd/error_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/httpd/error.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/lastlog<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/lighttpd/access.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/lighttpd/error.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/lighttpd/lighttpd.access.log cat /var/log/lighttpd/lighttpd.error.log cat /var/log/messages<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/secure<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/syslog<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/wtmp<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/xferlog<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/log/yum.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/run/utmp<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/webmin/miniserv.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/www/logs/access_log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;cat /var/www/logs/access.log<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/lib/dhcp3/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/log/postgresql/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/log/proftpd/<br>
&emsp;&emsp;&emsp;&emsp;&emsp;ls -alh /var/log/samba/<br><br>


<b1>&emsp;&emsp;&emsp;What “Advanced Linux File Permissions” are used? Sticky bits, SUID & GUID</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -perm -1000 -type d 2>/dev/null # Sticky bit - Only the owner of the directory or the owner of a file can delete or rename here.<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -perm -g=s -type f 2>/dev/null # SGID (chmod 2000) - run as the group, not the user who started it.<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -perm -u=s -type f 2>/dev/null # SUID (chmod 4000) - run as the owner, not the user who started it.<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -perm -g=s -o -perm -u=s -type f 2>/dev/null # SGID or SUID<br>
&emsp;&emsp;&emsp;&emsp;&emsp;for i in `locate -r "bin$"`; do find $i \( -perm -4000 -o -perm -2000 \) -type f 2>/dev/null; done<br>
&emsp;&emsp;&emsp;&emsp;&emsp;# Looks in ‘common’ places: /bin, /sbin, /usr/bin, /usr/sbin, /usr/local/bin, /usr/local/sbin and any other *bin, for SGID or SUID (Quicker search)<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -perm -g=s -o -perm -4000 ! -type l -maxdepth 3 -exec ls -ld {} \; 2>/dev/null<br>
&emsp;&emsp;&emsp;&emsp;&emsp;# find starting at root (/), SGID or SUID, not Symbolic links, only 3 folders deep, a list with more detail and hide any errors (e.g. permission denied)<br><br>

<b1>&emsp;&emsp;&emsp;Where can written to and executed from? A few ‘common’ places: /tmp, /var/tmp, /dev/shm</b1><br>

&emsp;&emsp;&emsp;&emsp;&emsp;find / -writable -type d 2>/dev/null # world-writeable folders<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -perm -222 -type d 2>/dev/null # world-writeable folders<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -perm -o w -type d 2>/dev/null # world-writeable folders<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -perm -o x -type d 2>/dev/null # world-executable folders<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / \( -perm -o w -perm -o x \) -type d 2>/dev/null # world-writeable & executable folders<br><br>

<b1>&emsp;&emsp;&emsp;Any “problem” files? Word-writeable, “nobody” files</b1><br>


&emsp;&emsp;&emsp;&emsp;&emsp;find / -xdev -type d \( -perm -0002 -a ! -perm -1000 \) -print # world-writeable files<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find /dir -xdev \( -nouser -o -nogroup \) -print # Noowner files<br><br>

<h1>&emsp;Preparation & Finding Exploit Code</h1><br>
<b1>&emsp;&emsp;&emsp;What development tools/languages are installed/supported?</b1><br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -name perl*<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -name python*<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -name gcc* find / -name cc<br><br>

<b1>&emsp;&emsp;&emsp;How can files be uploaded?</b1><br>

&emsp;&emsp;&emsp;&emsp;&emsp;find / -name wget find / -name nc*<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -name netcat*<br>
&emsp;&emsp;&emsp;&emsp;&emsp;find / -name tftp* find / -name ftp




