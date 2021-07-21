# Utilize The Force
* **Event:** GalaxyBattle
* **Problem Type:** Network
* **Point Value / Difficulty:** Medium
* **(Optional) Tools Required / Used:**

## Steps
#### Step 1
First step is to preform an nmap scan on the provided IP. nmap -sC -sV should work fine. Once done nmap should reveal that port 22 is open and that you can access ssh.

#### Step 2
Use can use a tool like hydra and the provided user and password lists to brute force a username and password.
the command `hydra -L users.txt -P pass.txt -t 10 <ip> ssh -s 22` should work well.

#### Step 3
Once on the server `ls` shows the plans.txt is in the current directory. `cat` it and get the flag!

