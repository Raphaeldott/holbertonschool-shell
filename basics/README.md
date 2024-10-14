1st script  prints the absolute path name of the current working directory.

2nd script display the content list of your current directory

3rd script change the working directory to the user's home variable

4th Display current directory contents, including hidden files (starting with .). Use the long format.

5th Display current directory contents.

Long format
with user and group IDs displayed numerically
And hidden files (starting with .)

6th Create a script that creates a directory named my_first_directory in the /tmp/ directory.

7th Move the file betty from /tmp/ to /tmp/my_first_directory.

8th Delete the file betty.

The file betty is in /tmp/my_first_directory

9th Delete the directory my_first_directory that is in the /tmp directory.

10th Write a script that changes the working directory to the previous one.

11th Write a script that lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the /boot directory (in this order), in long forma

12 Write a script that prints the type of the file named iamafile. The file iamafile will be in the /tmp directory when we will run your script.

13th Create a symbolic link to /bin/ls, named __ls__. The symbolic link should be created in the current working directory.

14th find . -maxdepth 1 -name '*.html' -exec cp -u {} ../

/* -maxdepth 1 tell to limit find to the current directory only
the depth 1 means it looks at the immediate children of the specified directory

-name '*.html'  filter the results to only include the pattern .html

-exec   to execute a command on each file that find matches

-u copy only when the source file is newer than the destination file or when the destination file does not exist.

{} is a place holder that gets replaced by each file found by find

../ is the target directory where the files should be copied, which is the parent directory of the current directory.

15th Create a script that moves all files beginning with an uppercase letter to the directory /tmp/u.

16th Create a script that deletes all files in the current working directory that end with the character ~.

17th Create a script that creates the directories welcome/, welcome/to/ and welcome/to/school in the current directory.

You are only allowed to use two spaces (and lines) in your script, not more.                   
