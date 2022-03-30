 # Black Beans
 * **Event:** legumeCTF
 * **Problem Type:** Networking
 * **Point Value / Difficulty:** Easy(ish)
 * **(Optional) Tools Required / Used:** John The Ripper
 
 ## Steps

 #### Step 1
 using the command 'nmap -sC -sV -v -p 8822 ctf.isss.io' should reveal that ssh is open. looks like a good target

 #### Step 2
 You can now get on the machine with 'ssh scotty@ctf.isss.io -p 8822' with the password given

 #### Step 3
 Once you are on the machine, you can navigate to the etc folder and run 'ls -al' and see that we have read access on botht the shadow and passwd files. cat these and save the text on your local machine to files of the same name.
 
 #### Step 4 
you can now use unshadow with 'unshadow passwd shadow > unshadow' to save a file neccessary for john to crack
 
 #### Step 5
run 'john unshadow' and it will should find the password for admin. you might need to run 'john --show unshadow' if it doesn't show after completing.

 #### Step 6
 use 'ssh admin@ctf.isss.io -p 8822' with the password you found and the flag should be visible in the folder with an ls.
