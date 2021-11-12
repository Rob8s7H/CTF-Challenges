# Spooky Configs Part 2
* **Event:** SpoopyCTF (ISSS CTF 10-22-2016)
* **Problem Type:** Network

## Steps

1. From part 2 we're now on the wcoldwater account. From here our goal is to 
   get privelege escalation.

2. After some digging we can find the both the etc/shadow and etc/passwd are
   both viewable from our unpriveleged account. Oh noes!

3. We can cat it and see another user dpumpkins.

4. Let's grab their information from passwd and paste it in a file called passwd.txt on our machine

5. Let's also grab their information for shadow and paste it into a file called shadow.txt also on our machine

6. We can use the command `unshadow passwd.txt

Thinker: At this last step we have unpriveleged access. What steps 
   could we take to get an upgraded privelege (e.g. root accesss)? 

