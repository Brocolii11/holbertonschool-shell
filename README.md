Holberton School - Shell

This repository is for the Holberton School Shell modules.
Author: Carlos De Jesus, Holberton Puerto Rico, Cohort 30

Modules

| Module | Folder | Status |
| --- | --- | --- |
| Shell, basics | `basics/` | Completed |
| Shell, permissions | `permissions/` | Completed |
| Shell, I/O Redirections and Filters | `io_redirections_and_filters/` | Completed |
| Shell, init files, variables and expansions | `init_files_variables_and_expansions/` | Completed |

About this repo

I use this repo for the Holberton Shell track. Right now I have four modules done:

- Shell Basics (`basics/`)
- Shell Permissions (`permissions/`)
- Shell I/O Redirections and Filters (`io_redirections_and_filters/`)
- Shell init files, variables and expansions (`init_files_variables_and_expansions/`)

Each script is a small bash file that runs one shell command (or a command with flags/patterns).
Every module folder has its own README with a task table and man-style notes for the commands I used.

How to check a script

Go into the module folder, then run the script:

```
cd basics
./0-current_working_directory
```

```
cd permissions
./1-who_am_i
```

```
cd io_redirections_and_filters
./0-hello_world
```

```
cd init_files_variables_and_expansions
./1-hello_you
```

Scripts need execute permission. On Windows chmod does not always stick in git, so I use:

```
git add --chmod=+x filename
```

I also made an alias for that:

```
alias gac='git add --chmod=+x '
```

More info

For the full task list and command notes, open:

- `basics/README.md`
- `permissions/README.md`
- `io_redirections_and_filters/README.md`
- `init_files_variables_and_expansions/README.md`

This repo will be updated when I start the next shell modules.
