This is where all the task are executed. I also figured out some .md styling for the readme. 

Holberton Checker fixed

Current Task Completed(In repo):


| Task                                      | File                          | What it does                                                                          |
| ----------------------------------------- | ----------------------------- | ------------------------------------------------------------------------------------- |
| T0 - Where am I?                          | `0-current_working_directory` | Prints the current working directory using pwd.                                       |
| T1 - What's in there?                     | `1-listit`                    | Lists the contents of the current directory.                                          |
| T2 - There is no place like home          | `2-bring_me_home`             | Changes the working directory to the home directory.                                  |
| T3 - The long format                      | `3-listfiles`                 | Lists files in long format with ls -l.                                                |
| T4 - Hidden files                         | `4-listmorefiles`             | Lists all files including hidden ones with ls -la.                                    |
| T5 - I love numbers                       | `5-listfilesdigitonly`        | Lists all files in long format with numeric user and group ids.                       |
| T6 - Welcome                              | `6-firstdirectory`            | Creates the directory /tmp/my_first_directory.                                        |
| T7 - Betty in my first directory          | `7-movethatfile`              | Moves /tmp/betty into /tmp/my_first_directory.                                        |
| T8 - Bye bye Betty                        | `8-firstdelete`               | Deletes the file betty from /tmp/my_first_directory.                                  |
| T9 - Bye bye My first directory           | `9-firstdirdeletion`          | Deletes the directory /tmp/my_first_directory.                                        |
| T10 - Back to the future                  | `10-back`                     | Changes the working directory to the previous one with cd -.                          |
| T11 - Lists                               | `11-lists`                    | Lists files in the current directory, the parent directory, and /boot.                |
| T12 - File type                           | `12-file_type`                | Prints the type of the file /tmp/iamafile.                                            |
| T13 - We are symbols, and inhabit symbols | `13-symbolic_link`            | Creates a symbolic link to /bin/ls named `__ls__`.                                   |
| T14 - Copy HTML files                     | `14-copy_html`                | Copies all .html files to the parent directory, but only if they are new or newer.    |
| T15 - Let's move                          | `15-lets_move`                | Moves all files that start with an uppercase letter to /tmp/u.                        |
| T16 - Clean Emcas                         | `16-clean_emacs`              | Deletes all files in the current directory that end with ~.                           |
| T17 - Tree                                | `17-tree`                     | Creates the directories welcome/, welcome/to/, and welcome/to/school/ using mkdir -p. |


Man info for the shell commands

Info of the commands per task (man style):

```
PWD(1)                            User Commands                           PWD(1)

NAME
       pwd - print name of current/working directory

SYNOPSIS
       pwd [OPTION]...

DESCRIPTION
       Print the full filename of the current working directory.

TASK NOTES (T0)
       Used in 0-current_working_directory.
       Example output: /home/user/holbertonschool-shell/basics


LS(1)                             User Commands                            LS(1)

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List information about the FILEs (the current directory by default).

       -l     use a long listing format
       -a     do not ignore entries starting with .
       -n     like -l, but list numeric user and group IDs

TASK NOTES
       T1  ls
           Basic list of names only.

       T3  ls -l
           Long format: permissions, owner, size, date, name.
           First char of permissions: - file, d directory, l link.

       T4  ls -la
           Long format + hidden files.
           Also shows . (current) and .. (parent).

       T5  ls -lna
           Same as -la, but owner/group as numbers (UID/GID).
           Example: 1001 0 instead of student_jail root.

       T11 ls -la . .. /boot
           ls can take multiple paths at once.
           . = current directory
           .. = parent directory
           /boot = absolute path to system boot directory
           Do not confuse /boot with ../boot


CD(1)                             User Commands                          BUILTIN

NAME
       cd - change the shell working directory

SYNOPSIS
       cd [-L|[-P [-e]] [-@]] [dir]
       cd -

DESCRIPTION
       Change the current directory to dir.
       If dir is not given, the value of HOME is used.
       A single hyphen (-) is treated specially.

TASK NOTES
       T2  cd
           No argument -> go to home directory.

       T10 cd -
           Go back to the previous working directory (OLDPWD).
           Also prints the path you moved to.
           Example: /var then /tmp, then cd - returns to /var.
           This script should be run with source so the cd stays
           in your current shell.


MKDIR(1)                          User Commands                         MKDIR(1)

NAME
       mkdir - make directories

SYNOPSIS
       mkdir [OPTION]... DIRECTORY...

DESCRIPTION
       Create the DIRECTORY(ies), if they do not already exist.

       -p, --parents
              no error if existing, make parent directories as needed

TASK NOTES
       T6  mkdir /tmp/my_first_directory/
           Creates one directory.

       T17 mkdir -p welcome/to/school
           Creates the full tree in one command:
           welcome/
           welcome/to/
           welcome/to/school/
           Without -p, mkdir fails if parents are missing.


MV(1)                             User Commands                            MV(1)

NAME
       mv - move (rename) files

SYNOPSIS
       mv [OPTION]... SOURCE... DIRECTORY
       mv [OPTION]... SOURCE DEST

DESCRIPTION
       Rename SOURCE to DEST, or move SOURCE(s) to DIRECTORY.

TASK NOTES
       T7  mv /tmp/betty /tmp/my_first_directory/
           Moves betty into my_first_directory.
           Use full paths when the file is not in the cwd.

       T15 mv [A-Z]* /tmp/u
           [A-Z]  one uppercase letter A-Z
           *      any characters after that
           Matches: Hello, README, Test.txt
           Does not match: hello, 1file
           Moves matching files into /tmp/u


RM(1)                             User Commands                            RM(1)

NAME
       rm - remove files or directories

SYNOPSIS
       rm [OPTION]... [FILE]...

DESCRIPTION
       Remove (unlink) the FILE(s).
       Deleted files are not sent to a recycle bin.

TASK NOTES
       T8  rm /tmp/my_first_directory/betty
           Deletes one file by full path.

       T16 rm *~
           *~ means any filename ending with ~
           Used to clean emacs backup files (example: notes.txt~)
           Be careful with wildcards and rm.


RMDIR(1)                          User Commands                         RMDIR(1)

NAME
       rmdir - remove empty directories

SYNOPSIS
       rmdir [OPTION]... DIRECTORY...

DESCRIPTION
       Remove the DIRECTORY(ies), if they are empty.

TASK NOTES
       T9  rmdir /tmp/my_first_directory
           Works only if the directory is empty.
           If files are still inside, remove them first.


FILE(1)                           User Commands                          FILE(1)

NAME
       file - determine file type

SYNOPSIS
       file [OPTION...] [FILE...]

DESCRIPTION
       Determine type of FILEs and print a description.
       Looks at file content/signature, not only the extension.

TASK NOTES
       T12 file /tmp/iamafile
           Prints the type of /tmp/iamafile.
           The checker creates that file before running the script.


LN(1)                             User Commands                            LN(1)

NAME
       ln - make links between files

SYNOPSIS
       ln [OPTION]... [-T] TARGET LINK_NAME

DESCRIPTION
       Create a link named LINK_NAME to TARGET.

       -s, --symbolic
              make symbolic links instead of hard links

TASK NOTES
       T13 ln -s /bin/ls __ls__
           TARGET     = /bin/ls
           LINK_NAME  = __ls__
           Creates a symlink (shortcut) in the current directory.
           Remember: ln = link, ls = list.


CP(1)                             User Commands                            CP(1)

NAME
       cp - copy files and directories

SYNOPSIS
       cp [OPTION]... SOURCE... DIRECTORY

DESCRIPTION
       Copy SOURCE to DIRECTORY, or SOURCE to DEST.

       -u, --update
              copy only when the SOURCE file is newer than the
              destination file or when the destination file is
              missing

TASK NOTES
       T14 cp -u *.html ..
           -u      update only (new or newer files)
           *.html  all files ending in .html
           ..      parent directory
           Skips overwrite if parent already has same/newer file.
```

