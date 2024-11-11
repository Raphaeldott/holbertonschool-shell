about permission: 
usually we use the "chmod" command and select a target from (U- user/ G-group/ O-others) and either add or minus a permission (R-read/ W-write/ X-execute)
for exemple: chmod u+x file
this command add the execute permission for the user to this files
             chmod o-w file
this command take axay the permission to write inside this file for the others.

But there is a second way with the chmod command. Its to talk in binary to the command.
In here we have three group of 3bits each so in binary we can go from 0 to 7
if we take that ---  rwx is a 3bits binary system then
the x = 1    w = 2    r = 4
                  - - -
                  4 2 1
so this config for example r-- equals 4
   this config for example r-x equals 5
   this config for example rwx equals 7

then writing this:
user: rwx
group: r-x
other: r--

is the same than:
user: 7
group:5
other:4

so chmod 754 file gives the files this rwxr-xr-- permission

777
Explanation: This permission value allows read, write, and execute for the owner, group, and others.

040
Explanation: This value gives read permission to the group owner only.

rwx------ permission?
700
Explanation: This value gives read, write, and execute permissions to the owner only.

r-xr--r-- permission?
544
Explanation: This value gives read and execute permissions to the owner and read permission to the group and others.

 ----w---x permission?
021
Explanation: This value gives write permission to the group and execute permission to others.

chown user:group myfile changes the owner of myfile to user and its group to group.

chgrp group myfile changes the group owner of myfile to group

su - switches to the root user and provides a new shell with root's environment.

sudo command
Function: Executes a command with superuser (root) privileges
