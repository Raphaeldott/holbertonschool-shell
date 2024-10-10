1st script  prints the absolute path name of the current working directory.

2nd script display the content list of your current directory

3rd script change the working directory to the user's home variable


14 find . -maxdepth 1 -name '*.html' -exec cp -u {} ../

/* -maxdepth 1 tell to limit find to the current directory only
the depth 1 means it looks at the immediate children of the specified directory

-name '*.html'  filter the results to only include the pattern .html

-exec   to execute a command on each file that find matches

-u copy only when the source file is newer than the destination file or when the destination file does not exist.

{} is a place holder that gets replaced by each file found by find

../ is the target directory where the files should be copied, which is the parent directory of the current directory. */                                                                                    ~                       
