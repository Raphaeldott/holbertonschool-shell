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

ex 24 sorted by bytes , case insesitive 
 find . -type f -name '''*.gif''' | rev | cut -d/ -f1 | cut -d . -f 2- | rev | LC_ALL=C sort -f

find . -type f -name '*.gif': This finds all files with the .gif extension.
| rev: Reverses the file paths so that the filename is at the front.
cut -d '/' -f 1: Takes the first part of the reversed string, effectively getting the filename.
cut -d '.' -f 2-: Removes the file extension (the .gif part) from the reversed filename.
| rev: Reverses the result back to normal.
| LC_ALL=C sort -f: Sorts the final output in a case-insensitive manner.

ex 25 acrostic
cut -c 1 | paste -s -d ''

cut -c 1 input.txt: This extracts the first character from each line in input.txt.
paste -s -d '': This combines all the extracted characters into a single line without any delimiter.

j'avais aussi essayé:    cut -c 1 | tr -d '\n'     mais impossible d'avoir \n a la fin 


ex 26 display host or ip wich did the most request
tail -n +2 | cut -d$'''	''' -f1 | sort --ignore-case | uniq -c | sort --ignore-case -nr | head -11 | rev  | cut -d''' ''' -f1 | rev

tail -n +2:
Skips the first line of the input, which is often a header in TSV (Tab-Separated Values) files.

cut -d$''' ''' -f1:
This command extracts the first field from each line, using a tab (\t) as the delimiter. The $''' ''' syntax is a way to specify a tab character in some shells, although using just cut -f 1 with default tab delimiter is simpler.

sort --ignore-case: 
Sorts the output from the previous step in ascending order, ignoring case differences (so "apple" and "Apple" would be treated the same).

uniq -c:  
Counts the occurrences of each unique line (in this case, unique first fields) and prefixes each line with the count.

sort --ignore-case -nr:  
Sorts the counted output in numeric order (-n) and in reverse (-r), again ignoring case. This puts the most frequently occurring items at the top.

head -11: 
Takes the top 11 lines from the sorted output, which represent the most common hosts or IPs.

rev: 
Reverses the order of characters in each line of the input. For example, edams.ksc.nasa.gov becomes vog.asa.ncs.made.

cut -d''' ''' -f1: 
Extracts the first field from the reversed lines. After reversing, the first field will be the count, but this part may need clarification because it seems there's a syntax issue with the quotes. It should look like cut -d' ' -f1 to extract the first field correctly.

rev:  Finally, it reverses the characters of the counts back to their original order.

at first ive tried cat nasa_19950801.tsv | tail -n +2 | cut -f 1 | sort | uniq -c | sort -rnk 1 | head -n 11
but i couldn't remove the request's count


