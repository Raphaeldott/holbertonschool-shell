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
