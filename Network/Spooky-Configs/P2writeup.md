# Spooky Configs Part 2
* **Event:** SpoopyCTF (ISSS CTF 10-22-2016)
* **Problem Type:** Network

## Steps

1. There are some interesting files on the ftp server from part 1,
   namely newusers.txt and welcome.msg

2. The newusers.txt is a list of newer users on the network and 
   the welcome message is reminding us to change our password 
   from the default CHANGEME!

3. From the nmap we preformed in part 1, you might have noticed an 
   ssh server occupying port 22. Let's test it with the users we
   found and the CHANGEME! password.

4. If we connect to ssh with wcoldwater@<IP> and enter the CHANGEME!
   password we'll get access to his home directory.

5. Perform an `ls` and we'll see the flag2.txt!

Thinker: At this last step we have unpriveleged access. What steps 
   could we take to get an upgraded privelege (e.g. root accesss)? 

