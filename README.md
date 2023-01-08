<h1>Linux-Bash-Scripting</h1>

<h2>Description</h2>
In this Project I'll be showing how to create User and groups as well as meaneuver through the CLI "command Line" using linux. I'm going to provide you a very in depth  step by step example how to create user and groups, as well as assign permission to specific user , groups and folders. Also heads up i am using AWS ec2 instance to run as an ec2 user, rather than using my local host name and information.


<h3>Enviroment Used</h3>

AWS ec2 instance
<br></br>
Linux CLI



<h4>Step 1</h4>

So the first step is to identify who are you, or who you are signed in as and the location you are in by running these commands "pwd" , "whoami" and follow with the date you started this assignment. This gives a basic understanding of the user you are logged in as and the users location


<br>
<img src=https://imgur.com/UPQKecM.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>


<h5>Step 2</h5>

We will create a user named "ec2-user" and create a password for the ec2-user and name it "anything". After creating this user and adding its credentials i will show you where to verify the creation of the user remoteuser. During this process I have granted my ec2-user sudo privileges, which i can explain later creating another repository. Next I will creating three directories called "dir1" , "dir2" , "dir3" and list to show the directories have been created.


<br>
<img src=https://imgur.com/EQq9VBK.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>

this command "cat /etc/passwd" will display all of the user created in the system.

<br>
<img src=https://imgur.com/maWnZfX.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>



the command "mkdir" create a directory which can also be called a folder. after creating all 3 directories use the command "ls la" which lists all hidden files and directories.

<br>
<img src=https://imgur.com/QHpia8Q.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>

<h6>Step 3</h6>

This next step is very easy,I'll be creating files inside "dir1" called file1.txt, file2.txt , file3.txt, then create files inside "dir3" called file4.txt , file5.txt , file6.txt then list all the files I have create for both dir1 and dir3. 

files created for "dir1" using the "touch" command which allows you to create files only. You can also use "vi or vim" command to create files which allows you to edit the file adding content or objects in it.

<br>
<img src=https://imgur.com/4HBPSMe.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>


files created for "dir3"

<br>
<img src=https://imgur.com/xnsFEJs.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>



<h7>Step 4</h7>

Now its time to create users and groups :)!!! Each user will have a specific group they'll be assigned to. " User1: Michael Group1: Finance, Security" "User2: Adam Group2:  Security,HR" "User3: Abby Group3: Admin , security" "User4: Shon Group4: Manager, Database" "User5: Emma Group5: network, admin"
The command we user to create user is "adduser" . for example: adduser shon, and creating a group i'll use the command "groupadd groupname". 


<br></br>

As you can see these are the new users i have created, now i will create their groups and assign the users, individually to the appropraite group. In order to find the groups you have created you'll use this command "cat /etc/group", this prints out all the groups created and the groups that are already part of the system. One of the most imporant things to remember is when you create a user the user comes with a default group, which will be the user username.

<br>
<img src=https://imgur.com/nywQ653.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>

<br>
<img src=https://imgur.com/2qn2rY5.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>

Users added to their corrective group

<br>
<img src=https://imgur.com/MraWeXW.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>



<h8>Step 5</h8>
This last step we will discuss permission and ownership using these two commands "chmod" which allows you to change permission for a file or folder and "chown" which allows you to change user or group ownership of a file or folder. First we will switch to the root user, and we shall create a folder in the home directory called "linux101".

<br></br>

quick steps you should follow to speed up the process.  sudo -i -->  whoami (to confirm you are in root user) --> cd /home (change to the home directory) --> mkdir linux101 (create the directory linux101). --> ls -lart (list all the files and folders to confirm the directory has been created).
As you can see the "linux101" directory has root:root thats the userowner:groupowner. The root also has full permission to drwxr-xr-x read(4) , write(2) and execute(1). To break permission watch this video to get a better explanation https://www.youtube.com/watch?v=LFNwRp-rwMs

<br>
<img src=https://imgur.com/vgUmiX4.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>

I shall remove all the permissions for "others" on linux101 folder using the command "chmod 750 linux101" and i'll display the content of the home directory to show "others" permissions has been fully evoked. 

<br>
<img src=https://imgur.com/fDRGstL.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>

<br></br>
I will then add the "security" group to the linux101 folder. Whoever is following this repository should know this:What is the consequence of adding the security group as group ownership of the directory? What regular user/s now has access and with what permission?

<br> </br>
Change the linux101 group owner using this command: "chown root: security linux101" As can be seen, the ownership of the group has changed, which means that, despite the fact that the root user created the file, members of the "security" group now have permission to read, write, and execute it. The "sudo" rights for this folder, "linux101," are granted to the member of the security group.


<br>
<img src=https://imgur.com/2nDqjyb.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>

Lastly i will switch to the user adam in the security group and verify if i can access the folder and file. 

<br>
<img src=https://imgur.com/TGvxHcY.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</br>

<br></br>
Now you have the basic understanding of Linux. Please leave a suggestion of what I can improve on. Most importantly thank you for stopping by.
