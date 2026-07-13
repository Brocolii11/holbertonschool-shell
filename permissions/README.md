This is where all the task are executed. This will follow the same styling as basics.

Current Task Completed(in repo):

**Marked tasked were completed in the sandbox holberton provided.**


| Task | File | What it does |
| --- | --- | --- |
| T0 | `0-iam_betty` | Changes user in terminal using su. |
| T1 | `1-who_am_i` | It shows the active user in the terminal. |
| T2 | `2-groups` | It shows how many groups the active user is in. |
| **T3*** | `3-new_owner` | This command let you change the ownership of the file between users. |
| T4 | `4-empty` | Creates an empty file using touch. |
| T5 | `5-execute` | Changes execute permisions for the active user over a file. |
| T6 | `6-multiple_permissions` | Adds execute for user and group, and read for others. |
| T7 | `7-everybody` | Adds execute permission for everybody. |
| T8 | `8-James_Bond` | Sets permissions to 007 so only others have full access. |
| T9 | `9-John_Doe` | Sets permissions to 753 on hello. |
| T10 | `10-mirror_permissions` | Copies permissions from olleh to hello using --reference. |
| T11 | `11-directories_permissions` | Adds execute for directories only, recursively, with a+X. |
| T12 | `12-directory_permissions` | Creates my_dir with mode 751 using mkdir -m. |
| **T13*** | `13-change_group` | Changes the group of hello to school. |
| **T14*** | `14-change_owner_and_group` | Recursively changes owner and group to vincent:staff. |
| **T15*** | `15-symbolic_link_permissions` | Changes owner and group of a symbolic link itself with -h. |
| **T16*** | `16-if_only` | Changes owner to vincent only if the current owner is guillaume. |


Man info for the shell commands

Info of the commands per task (man style):

```
SU(1)                             User Commands                            SU(1)

NAME
       su - run a command with substitute user and group ID

SYNOPSIS
       su [options] [-] [user [argument...]]

DESCRIPTION
       Change the effective user ID for a login session.

TASK NOTES (T0)
       Used in 0-iam_betty.
       Example: su betty


WHOAMI(1)                         User Commands                        WHOAMI(1)

NAME
       whoami - print effective user name

SYNOPSIS
       whoami [OPTION]...

DESCRIPTION
       Print the user name associated with the current effective user ID.

TASK NOTES (T1)
       Used in 1-who_am_i.
       Shows who you are right now in the terminal.


GROUPS(1)                         User Commands                        GROUPS(1)

NAME
       groups - print the groups a user is in

SYNOPSIS
       groups [OPTION]... [USERNAME]...

DESCRIPTION
       Print group memberships for the current user, or for USERNAME.

TASK NOTES (T2)
       Used in 2-groups.
       Lists the groups for the active user.


CHOWN(1)                          User Commands                         CHOWN(1)

NAME
       chown - change file owner and group

SYNOPSIS
       chown [OPTION]... [OWNER][:[GROUP]] FILE...

DESCRIPTION
       Change the owner and/or group of each FILE.

       -R, --recursive
              operate on files and directories recursively

       -h, --no-dereference
              affect symbolic links instead of any referenced file

       --from=CURRENT_OWNER:CURRENT_GROUP
              change only if current owner/group match

TASK NOTES
       T3  chown betty hello
           Makes betty the owner of hello.

       T14 chown -R vincent:staff .
           Changes owner to vincent and group to staff
           for . and everything inside it.

       T15 chown -h vincent:staff _hello
           -h changes the symlink itself, not the target file.
           Without -h, chown follows the link.

       T16 chown --from=guillaume vincent hello
           Only changes owner if current owner is guillaume.
           Then new owner becomes vincent.


CHGRP(1)                          User Commands                         CHGRP(1)

NAME
       chgrp - change group ownership

SYNOPSIS
       chgrp [OPTION]... GROUP FILE...

DESCRIPTION
       Change the group of each FILE to GROUP.

TASK NOTES (T13)
       Used in 13-change_group.
       Example: chgrp school hello
       Changes only the group, not the owner.


TOUCH(1)                          User Commands                         TOUCH(1)

NAME
       touch - change file timestamps

SYNOPSIS
       touch [OPTION]... FILE...

DESCRIPTION
       Update the access and modification times of each FILE.
       If FILE does not exist, create an empty one.

TASK NOTES (T4)
       Used in 4-empty.
       Example: touch hello


MKDIR(1)                          User Commands                         MKDIR(1)

NAME
       mkdir - make directories

SYNOPSIS
       mkdir [OPTION]... DIRECTORY...

DESCRIPTION
       Create the DIRECTORY(ies), if they do not already exist.

       -m, --mode=MODE
              set file mode (as in chmod), not a=rwx - umask

TASK NOTES (T12)
       Used in 12-directory_permissions.
       Example: mkdir -m 751 my_dir
       Creates my_dir already with permissions 751.
       7 = owner rwx, 5 = group r-x, 1 = others --x


CHMOD(1)                          User Commands                         CHMOD(1)

NAME
       chmod - change file mode bits

SYNOPSIS
       chmod [OPTION]... MODE[,MODE]... FILE...
       chmod [OPTION]... OCTAL-MODE FILE...
       chmod [OPTION]... --reference=RFILE FILE...

DESCRIPTION
       Change the mode of each FILE.
       u = user/owner, g = group, o = others, a = all.
       r = read, w = write, x = execute.
       X = execute only if it is a directory or already has execute.
       Octal: 4=r, 2=w, 1=x.

       -R, --recursive
              change files and directories recursively

       --reference=RFILE
              use RFILE's mode instead of MODE values

TASK NOTES
       T5  chmod u+x hello
           Add execute for the owner.

       T6  chmod ug+x,o+r hello
           Add execute for user and group.
           Add read for others.

       T7  chmod ugo+x hello
           Add execute for everybody.

       T8  chmod 007 hello
           Absolute mode. Only others get rwx.
           James Bond joke: 007.

       T9  chmod 753 hello
           Owner 7 (rwx), group 5 (r-x), others 3 (-wx).
           John Doe mode.

       T10 chmod --reference=olleh hello
           Copy the exact permissions from olleh onto hello.
           Useful when you do not want to type the mode by hand.

       T11 chmod -R a+X .
           -R  recursive
           a+X add execute for all, but only on directories
               (or files that already are executable)
           Capital X is different from lowercase x.
```
