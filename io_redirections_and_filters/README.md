about redirections ><

ex 8 current state of directories
ls -la > ls_cwd_content

ls -la lists all files in the current directory, showing detailed information.
The > operator redirects the output to ls_cwd_content. If the file exists, it will be overwritten. If it doesn’t, it will be created.

ex 9 duplicate last line
tail -n 1 iacta >> iacta

tail -n 1 iacta extracts the last line.
>> iacta appends that line to the file.

ex 10 deletes js
find . -type f -name "*.js" -delete

find . starts searching from the current directory.
-type f specifies that you want to find regular files.
-name "*.js" filters the results to only include files with a .js extension.
-delete removes the found files.

ex 11 count directories
find . -mindepth 1 -type d | wc -l

find . starts the search from the current directory.
-mindepth 1 ensures that the current directory (.) is not included in the results.
-type d specifies that you want to find directories only.
| wc -l counts the number of lines outputted by the find command, which corresponds to the number of directories found

ex 12 newest
# List files, filter for regular files, and get the 10 newest
ls -1t | head -n 10

ls -1t: This lists files in a single column sorted by modification time, newest first.
head -n 10: This extracts the first 10 files from the output

ex 13 uniques
# Read words from standard input, sort them, and filter for unique occurrences
sort | uniq -u

sort: This command sorts the input words alphabetically.
uniq -u: The uniq command filters out repeated lines. The -u option specifically outputs only the lines that are unique

ex 14 find a pattern
grep "root" /etc/passwd

grep: This command searches for patterns in files.
"root": This is the pattern you're searching for. In this case, it looks for the string "root".
/etc/passwd: This is the file in which you're searching for the pattern.

ex 15 count that word
grep -c "bin" /etc/passwd

grep: This command searches for patterns in files.
-c: This option tells grep to count the number of matching lines instead of displaying them.
"bin": This is the pattern you're searching for.
/etc/passwd: This is the file being searched

ex 16 add trailing
grep -A 3 "root" /etc/passwd

-A 3: This option tells grep to display 3 lines of trailing context after each

ex 17 do not contain
grep -v "bin" /etc/passwd

-v: This option tells grep to invert the match, meaning it will display all lines that do not match the specified pattern.

ex 18 letters only
grep '^[a-zA-Z]' /etc/ssh/sshd_config

'^[a-zA-Z]': This is the regular expression used to match lines starting with a letter.

ex 19 replace letters
tr 'Ac' 'Ze'
replace 'Ac' to 'Ze'

ex 20 remove letters
tr -d 'cC'

-d delete occurence

ex 21 reverse input
rev

ex 22 delimiters
cat /etc/passwd | cut -d: -f1,6 | sort

cat /etc/passwd: This command reads the contents of the /etc/passwd file.
cut -d: -f1,6: This command:
-d:: Specifies : as the delimiter.
-f1,6: Selects the first and sixth fields (username and home directory).

ex 23 empty casks
find . -empty | rev | cut -d '/' -f 1 | rev

find . -empty: This part searches the current directory (.) and its subdirectories for empty files and directories.

| rev: This takes the output of the find command and reverses each line of text.

| cut -d '/' -f 1: This takes the reversed lines and cuts them at the / delimiter, selecting the first field (which is now the last part of the original path due to the reversal).

| rev: Finally, this reverses the result again, restoring the original file or directory names but now only displaying the last part of the path.





