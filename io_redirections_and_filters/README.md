This is where all the task are executed. This will follow the same styling as basics.

Current Task Completed(in repo):

| Task | File | What it does |
| --- | --- | --- |
| T0 - Hello World | `0-hello_world` | Prints Hello, World using echo. |
| T1 - Confused smiley | `1-confused_smiley` | Displays the confused smiley "(Ôo)' using echo and escaping. |
| T2 - Hello file | `2-hellofile` | Displays the content of /etc/passwd with cat. |
| T3 - Two files | `3-twofiles` | Displays /etc/passwd and /etc/hosts with cat. |
| T4 - Last lines | `4-lastlines` | Displays the last 10 lines of /etc/passwd with tail. |
| T5 - First lines | `5-firstlines` | Displays the first 10 lines of /etc/passwd with head. |
| T6 - Third line | `6-third_line` | Displays the third line of iacta using head and tail. |
| T7 - File | `7-file` | Creates a file with a weird name containing Best School. |
| T8 - CWD state | `8-cwd_state` | Writes ls -la output into ls_cwd_content (overwrite/create). |
| T9 - Duplicate last line | `9-duplicate_last_line` | Appends the last line of iacta to iacta again. |
| T10 - No more js | `10-no_more_js` | Deletes all .js regular files in the current directory and subfolders. |
| T11 - Directories | `11-directories` | Counts directories and sub-directories (not . or ..). |
| T12 - Newest files | `12-newest_files` | Displays the 10 newest files in the current directory. |
| T13 - Unique | `13-unique` | Prints words from input that appear exactly once. |
| T14 - Find that word | `14-findthatword` | Displays lines containing root from /etc/passwd. |
| T15 - Count that word | `15-countthatword` | Counts lines containing bin in /etc/passwd. |
| T16 - Whats next | `16-whatsnext` | Displays lines with root and 3 lines after them. |
| T17 - Hide this word | `17-hidethisword` | Displays lines in /etc/passwd that do not contain bin. |
| T18 - Letter only | `18-letteronly` | Displays lines in sshd_config that start with a letter. |
| T19 - AZ | `19-AZ` | Replaces A with Z and c with e from input. |
| T20 - Hiago | `20-hiago` | Removes all c and C letters from input. |
| T21 - Reverse | `21-reverse` | Reverses its input. |
| T22 - Users and homes | `22-users_and_homes` | Displays users and home directories from /etc/passwd, sorted. |


Man info for the shell commands

Info of the commands per task (man style):

```
ECHO(1)                           User Commands                          ECHO(1)

NAME
       echo - display a line of text

SYNOPSIS
       echo [STRING]...

DESCRIPTION
       Output the STRINGs to standard output.

TASK NOTES
       T0  echo "Hello, World"
       T1  echo "\"(Ôo)'"
           \" prints a literal double quote.


CAT(1)                            User Commands                           CAT(1)

NAME
       cat - concatenate files and print on the standard output

SYNOPSIS
       cat [FILE]...

DESCRIPTION
       Read FILE(s) and write them to standard output.

TASK NOTES
       T2  cat /etc/passwd
       T3  cat /etc/passwd /etc/hosts


HEAD(1)                           User Commands                          HEAD(1)

NAME
       head - output the first part of files

SYNOPSIS
       head [OPTION]... [FILE]...

DESCRIPTION
       Print the first 10 lines of each FILE by default.

       -n, --lines=NUM
              print the first NUM lines

TASK NOTES
       T5  head /etc/passwd
       T6  head -n 3 iacta | tail -n 1
           first 3 lines, then keep only the last of those.


TAIL(1)                           User Commands                          TAIL(1)

NAME
       tail - output the last part of files

SYNOPSIS
       tail [OPTION]... [FILE]...

DESCRIPTION
       Print the last 10 lines of each FILE by default.

       -n, --lines=NUM
              output the last NUM lines

TASK NOTES
       T4  tail /etc/passwd
       T9  tail -n 1 iacta >> iacta
           >> appends instead of overwriting.


REDIRECTION

NAME
       >  >>  - shell output redirection

DESCRIPTION
       >   send output to a file (create or overwrite)
       >>  append output to a file

TASK NOTES
       T7  echo "Best School" > 'weird_filename'
       T8  ls -la > ls_cwd_content


FIND(1)                           User Commands                          FIND(1)

NAME
       find - search for files in a directory hierarchy

SYNOPSIS
       find [PATH] [EXPRESSION]

DESCRIPTION
       Search for files matching tests like -type and -name.

TASK NOTES
       T10 find . -type f -name "*.js" -delete
       T11 find . -mindepth 1 -type d | wc -l
           -mindepth 1 skips the current directory .


LS(1) / WC(1)

TASK NOTES
       T12 ls -t | head -n 10
           -t sorts by modification time (newest first).


SORT(1) / UNIQ(1)

NAME
       sort - sort lines of text files
       uniq - report or omit repeated lines

TASK NOTES
       T13 sort | uniq -u
           -u prints only unique lines (appear once).


GREP(1)                           User Commands                          GREP(1)

NAME
       grep - print lines that match patterns

SYNOPSIS
       grep [OPTION]... PATTERN [FILE]...

DESCRIPTION
       Search for PATTERN in FILE(s).

       -c     count matching lines
       -A NUM print NUM lines after a match
       -v     invert match (print non-matching lines)

TASK NOTES
       T14 grep root /etc/passwd
       T15 grep -c bin /etc/passwd
       T16 grep -A 3 root /etc/passwd
       T17 grep -v bin /etc/passwd
       T18 grep '^[a-zA-Z]' /etc/ssh/sshd_config
           ^ means start of line.


TR(1)                             User Commands                            TR(1)

NAME
       tr - translate or delete characters

SYNOPSIS
       tr [OPTION]... SET1 [SET2]

DESCRIPTION
       Translate characters from SET1 to SET2, or delete with -d.

TASK NOTES
       T19 tr Ac Ze
           A->Z and c->e
       T20 tr -d cC
           delete all c and C characters.


REV(1)                            User Commands                           REV(1)

NAME
       rev - reverse lines characterwise

TASK NOTES
       T21 rev


CUT(1)                            User Commands                           CUT(1)

NAME
       cut - remove sections from each line of files

SYNOPSIS
       cut OPTION... [FILE]...

DESCRIPTION
       -d DELIM   use DELIM instead of TAB as field delimiter
       -f LIST    select only these fields

TASK NOTES
       T22 cut -d: -f 1,6 /etc/passwd | sort
           field 1 = username, field 6 = home directory.
```
