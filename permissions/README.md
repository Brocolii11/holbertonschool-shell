This is where all the tasks are executed. This follows the same styling as basics.

Current tasks completed (in repo):

**Marked tasks were completed in the sandbox Holberton provided.**


| Task    | File                     | What it does                                                  |
| ------- | ------------------------ | ------------------------------------------------------------- |
| T0      | `0-iam_betty`            | Switches user in the terminal using `su betty`.               |
| T1      | `1-who_am_i`             | Prints the active username with `whoami`.                     |
| T2      | `2-groups`               | Lists groups for the active user with `groups`.               |
| **T3*** | `3-new_owner`            | Changes file ownership with `chown betty hello`.              |
| T4      | `4-empty`                | Creates an empty file with `touch hello`.                     |
| T5      | `5-execute`              | Adds execute permission for the owner with `chmod u+x hello`. |
| T6      | `6-multiple_permissions` | Sets mixed permissions with `chmod ug+x,o+r hello`.           |
| T7      | `7-everybody`            | Adds execute for everyone with `chmod ugo+x hello`.           |
| T8      | `8-James_Bond`           | Sets octal mode `007` with `chmod 007 hello` (others only).   |
| T9      | `9-John_Dow`             | Pending                                                       |
| T10     | `10-mirror_permissions`  | Pending                                                       |


Man info for the shell commands

Info of the commands per task (man style):

```
SU(1)                             User Commands                            SU(1)

NAME
       su - run a command with substitute user and group ID

SYNOPSIS
       su [options] [-] [user [argument...]]

DESCRIPTION
       Change the effective user ID (and possibly group) for a login session.

TASK NOTES (T0)
       Used in 0-iam_betty as: su betty
       Switches the terminal session to user betty.


WHOAMI(1)                         User Commands                        WHOAMI(1)

NAME
       whoami - print effective user name

SYNOPSIS
       whoami [OPTION]...

DESCRIPTION
       Print the user name associated with the current effective user ID.

TASK NOTES (T1)
       Used in 1-who_am_i.
       Shows who you are in the current shell session.


GROUPS(1)                         User Commands                        GROUPS(1)

NAME
       groups - print the groups a user is in

SYNOPSIS
       groups [OPTION]... [USERNAME]...

DESCRIPTION
       Print group memberships for each USERNAME (current user if none given).

TASK NOTES (T2)
       Used in 2-groups.
       Lists all groups for the active user.


CHOWN(1)                          User Commands                         CHOWN(1)

NAME
       chown - change file owner and group

SYNOPSIS
       chown [OPTION]... [OWNER][:[GROUP]] FILE...

DESCRIPTION
       Change the owner and/or group of each FILE.

TASK NOTES (T3)
       Used in 3-new_owner as: chown betty hello
       Makes betty the owner of file hello.
       Often requires elevated privileges.


TOUCH(1)                          User Commands                         TOUCH(1)

NAME
       touch - change file timestamps / create empty files

SYNOPSIS
       touch [OPTION]... FILE...

DESCRIPTION
       Update access and modification times.
       If FILE does not exist, create it empty (unless options say otherwise).

TASK NOTES (T4)
       Used in 4-empty as: touch hello
       Creates empty file hello if missing.


CHMOD(1)                          User Commands                         CHMOD(1)

NAME
       chmod - change file mode bits

SYNOPSIS
       chmod [OPTION]... MODE[,MODE]... FILE...
       chmod [OPTION]... OCTAL-MODE FILE...

DESCRIPTION
       Change permissions for user (u), group (g), and others (o).
       Letters: r read, w write, x execute.
       Octal digits: 4=r, 2=w, 1=x (sum per class).

TASK NOTES
       T5  chmod u+x hello
           Add execute for the owner only.

       T6  chmod ug+x,o+r hello
           Add execute for user and group; add read for others.

       T7  chmod ugo+x hello
           Add execute for user, group, and others.

       T8  chmod 007 hello
           Absolute mode: user=0, group=0, others=7 (rwx).
           Only "others" have full access (007 / James Bond joke).
```

