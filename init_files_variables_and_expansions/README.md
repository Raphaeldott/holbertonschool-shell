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

ex 3 count directories in the path
echo $PATH | tr : $'\n' | grep / | wc -l

echo $PATH
Purpose: Outputs the value of the PATH environment variable.

tr : $'\n'
Purpose: Translates (or replaces) colons (:) in the output with newline characters (\n).

grep /
Purpose: Filters the output to include only lines that contain a forward slash (/).

wc -l
Purpose: Counts the number of lines in the input it receives

ex 4 list global variables
printenv

ex 5 list local variables
set

ex 6 create local variable
BEST="School"
like declaring a variable in C

ex 7 create global variable
export BEST="School"

ex 8 addition with variables
echo $((128 + TRUEKNOWLEDGE))

ex 9 division
$((5/2))

ex 10 puissances
$((5**2))

ex 11 base 2  to base 10
echo $((2#$BINARY))

$((...))
What it is: This is a form of arithmetic expansion in Bash.
Purpose: It evaluates the arithmetic expression inside the parentheses and returns the result.
 2#$BINARY
2#: This prefix indicates that the number following it is in base 2 (binary). In Bash, you can specify the base of a number using this syntax: base#number.
$BINARY: This is a variable that is expected to contain a binary number (a string of 0s and 1s).

ex 12 combination aa zz without oo
echo {a..z}{a..z} | tr ' ' '\n' | grep -v oo

tr ' ' '\n':
tr is a command that translates or deletes characters.
In this case, it replaces spaces (' ') in the output from the previous command with newline characters ('\n').
grep -v: This command filters the input.
The -v option inverts the match, meaning it will exclude lines that match the specified pattern.
oo: This is the pattern to exclude

ex 13 write with two decimal places
printf "%.2f\n" "$NUM"

%: A placeholder that indicates where to insert a value.
.2: This specifies that you want to display the number with two decimal places.
f: Stands for "floating point", indicating that the value being formatted is a decimal number.
\n: This is a newline character, ensuring that the output ends with a new line.
"$NUM": This is a variable that holds the value you want to format. The double quotes around $NUM ensure that it is treated as a single argument, even if it contains spaces or special characters.

ex 14 decimal to hexadecimal
printf "%x\n" "$DECIMAL"

This line uses printf to format the output. %x converts the number from decimal to hexadecimal, and \n adds a newline at the end.


