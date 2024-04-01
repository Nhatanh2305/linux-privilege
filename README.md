# linux-privilege <h1></h1> <b1></b1>
<h1>1.Kernel and distribution release details</h1><br>
<h1>2.System Information:</h1>
Hostname<br>
Networking details:<br>
Current IP<br>
Default route details<br>
DNS server information<br><br>
<h1>3.User Information:</h1>
Current user details<br>
Last logged on users<br>
Shows users logged onto the host<br>
List all users including uid/gid information<br>
List root accounts<br>
Extracts password policies and hash storage method information<br>
Checks umask value<br>
Checks if password hashes are stored in /etc/passwd<br>
Extract full details for ‘default’ uid’s such as 0, 1000, 1001 etc<br>
Attempt to read restricted files i.e. /etc/shadow<br>
List current users history files (i.e .bash_history, .nano_history, .mysql_history , etc.)<br>
Basic SSH checks<br><br>
<h1>4.Privileged access</h1>
Which users have recently used sudo<br>
Determine if /etc/sudoers is accessible<br>
Determine if the current user has Sudo access without a password<br>
Are known ‘good’ breakout binaries available via Sudo (i.e. nmap, vim etc.)<br>
Is root’s home directory accessible<br>
List permissions for /home/<br><br>
<h1>5.Environmental</h1>
Display current $PATH<br>
Displays env information<br><br>
<h1>6.Jobs/Tasks:</h1>
List all cron jobs<br>
Locate all world-writable cron jobs<br>
Locate cron jobs owned by other users of the system<br>
List the active and inactive systemd timers<br>
<h1>7.Services</h1>
List network connections (TCP & UDP)<br>
List running processes<br>
Lookup and list process binaries and associated permissions<br>
List inetd.conf/xined.conf contents and associated binary file permissions<br>
List init.d binary permissions<br><br>
<h1>7.Version Information (of the following)</h1> 
Sudo<br>
MYSQL<br>
Postgres<br>
Apache<br>
      &emsp;&emsp;  Checks user config<br>
      &emsp;&emsp;  Shows enabled modules<br>
      &emsp;&emsp;  Checks for htpasswd files<br>
      &emsp;&emsp;  View www directories<br><br>

<h1>8.Default/Weak Credentials:</h1>
Checks for default/weak Postgres accounts<br>
Checks for default/weak MYSQL accounts<br><br>

<h1>9.Searches</h1>
Locate all SUID/GUID files<br>
Locate all world-writable SUID/GUID files<br>
Locate all SUID/GUID files owned by root<br>
Locate ‘interesting’ SUID/GUID files (i.e. nmap, vim etc)<br>
Locate files with POSIX capabilities<br>
List all world-writable files<br>
Find/list all accessible *.plan files and display contents<br>
Find/list all accessible *.rhosts files and display contents<br>
Show NFS server details<br>
Locate *.conf and *.log files containing keyword supplied at script runtime<br>
List all *.conf files located in /etc<br>
Locate mail<br><br>
<h1>10.Platform/software specific tests:</h1>
Checks to determine if we’re in a Docker container<br>
Checks to see if the host has Docker installed<br>
Checks to determine if we’re in an LXC container<br><br>

<h1>11.Kernel exploits</h1>
A vulnerable kernel<br>
A matching exploit<br>
The ability to transfer the exploit onto the target<br>
The ability to execute the exploit on the target<br>















<br><br><br><br><br><br><br>
office2john readme.docx > hash.txt
john -w=/usr/share/wordlists/rockyou.txt hash.txt
john –show hash.txt






