Holberton School - Shell

This repository is for the Holberton School Shell modules.
Author: Carlos De Jesus, Holberton Puerto Rico, Cohort 30

Modules


| Module             | Folder         | Status                   |
| ------------------ | -------------- | ------------------------ |
| Shell, basics      | `basics/`      | Completed                |
| Shell, permissions | `permissions/` | In progress (T0–T8 done) |


About this repo

I started this repo for the Shell Basics module. That first module is done.
All scripts from that module are inside the basics folder.

The permissions module is in progress. Scripts for completed tasks are in the permissions folder.

Each script is a small bash file that runs one shell command (or a command with flags/patterns).
Each module README has a task table. Basics also has man-style notes for the commands used.

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

Scripts need execute permission. On Windows I used:

```
git add --chmod=+x filename
```

More info

For task lists and command notes, open:

- `basics/README.md`
- `permissions/README.md`

This repo will be updated as more shell modules and tasks are completed.