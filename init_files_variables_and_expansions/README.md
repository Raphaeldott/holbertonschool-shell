about variables and expensions

ex 0 create temprorary alias
alias ls="rm *"

ex 1 user is the current user
echo "hello ${USER:-$(whoami)}"

la solution la plus simple est :   echo $USER

ex 2 add to a path
 export PATH="$PATH:/action"

export:

The export command is used to set environment variables in the current shell session and make them available to any subprocesses (e.g., scripts, programs) started from that shell. When you export a variable, it allows child processes to inherit it.
PATH:

PATH is a special environment variable that tells the shell where to look for executable files (programs). It is a colon-separated list of directories. When you type a command in the terminal, the shell searches these directories in the order they are listed in PATH to find the executable.
"$PATH":

This refers to the current value of the PATH variable. The use of quotes ensures that any spaces or special characters in the PATH value are preserved and correctly interpreted. By including "$PATH", you are retaining all the existing directories already in the PATH.
:/action:

This adds the directory /action to the end of the PATH. The colon (:) is the separator between directories in the PATH variable. By placing /action after "$PATH", you ensure that the shell will look in /action after checking all the other directories already listed in PATH.
