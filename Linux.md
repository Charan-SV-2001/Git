# Linux Cheat Sheet

## File Commands

| Command                 | Description                                             |
|-------------------------|---------------------------------------------------------|
| `cat <file>`            | Print file contents                                     |
| `touch <file>`          | Create file (or update timestamp)                       |
| `cp <src> <dst>`        | Copy a file                                             |
| `mv <src> <dst>`        | Move / rename a file                                    |
| `rm <file>`             | Remove file                                             |
| `head <file>`           | Print first 10 lines of file                            |
| `tail <file>`           | Print last 10 lines of file                             |
| `tail -f <file>`        | Print last 10 lines and any new lines added to file     |

---

## Directory Commands

| Command                 | Description                                             |
|-------------------------|---------------------------------------------------------|
| `ls`                    | List files in the current directory                     |
| `ls <dir>`              | List files in `<dir>`                                   |
| `ls -l`                 | List files with details                                 |
| `ls -a`                 | List all files (including hidden)                       |
| `ls -al`                | List all files with details                             |
| `pwd`                   | Print the current/working directory                     |
| `cd <dir>`              | Change current directory to `<dir>`                     |
| `cd ..`                 | Go up one directory                                     |
| `mkdir <dir>`           | Create directory                                        |
| `mkdir -p <dir>`        | Create directory and any missing parent directories     |
| `cp -r <src> <dst>`     | Copy a directory and its contents                       |
| `mv <src> <dst>`        | Move / rename a directory                               |
| `rmdir <dir>`           | Remove an empty directory                               |
| `rm -r <dir>`           | Remove a directory and its contents                     |

---

## Directory Aliases

| Alias | Directory         |
|-------|-------------------|
| `.`   | Current directory |
| `..`  | Parent directory  |
| `~`   | Home directory    |

---

## Link Commands

| Command                      | Description                                   |
|------------------------------|-----------------------------------------------|
| `ln -s <target> <link>`      | Create symbolic link                         |
| `ln <target> <link>`         | Create hard link                             |
| `readlink -f <file>`         | Print absolute path of file                  |

---

## Search Commands

| Command                         | Description                                            |
|---------------------------------|--------------------------------------------------------|
| `grep <pattern> <file...>`      | Search for pattern in file(s)                          |
| `grep -r <pattern> <dir>`       | Search for pattern recursively in a directory          |
| `grep -i <pattern> <file>`      | Search for pattern case-insensitively                  |
| `grep -v <pattern> <file>`      | Search for lines not matching pattern                  |
| `grep -n <pattern> <file>`      | Search and print line numbers                          |
| `find <dir> -name <name>*`      | Find files in `<dir>` with name starting with `<name>` |
| `find <dir> -type <type>`       | Find files in `<dir>` of type `<type>`                 |

---

## Superuser Commands

| Command          | Description                                     |
|------------------|-------------------------------------------------|
| `sudo <cmd>`     | Run command as superuser (root)                 |
| `su`             | Switch to superuser (root)                      |
| `su <user>`      | Switch to user `<user>`                         |

---

## File Permission Commands

| Command                      | Description                                                         |
|------------------------------|---------------------------------------------------------------------|
| `chmod <mode> <file>`        | Change file permissions                                            |
| `chmod u+x <file>`           | Add execute permission for the owner                               |
| `chmod 644 <file>`           | Set file permissions to 644 (read/write for owner, read for group and everyone else) |
| `chmod -R g+w <dir>`         | Add write permission for the group recursively to a directory      |
| `chown <owner> <file>`       | Change file owner                                                  |
| `chown -R <owner> <dir>`     | Change directory owner recursively                                 |
| `chown <owner>:<group> <file>`| Change file owner and group                                        |
| `chgrp <group> <file>`       | Change file group                                                  |

---

## File Permission Bits

| Bit | Description   |
|-----|---------------|
| `4` | Read (`r`)    |
| `2` | Write (`w`)   |
| `1` | Execute (`x`) |

- The first digit represents the owner, the second digit represents the group, and the third digit represents everyone else.
- For example, `640` means:
  - Read/Write for the owner.
  - Read for the group.
  - No permissions for everyone else.

---

## File Permission User Types

| User Type | Description       |
|-----------|-------------------|
| `u`       | Owner             |
| `g`       | Group             |
| `o`       | Everyone else     |
| `a`       | All               |

## System Information Commands

| Command       | Description                              |
|---------------|------------------------------------------|
| `df`          | Show file system disk usage             |
| `df -h`       | Show disk usage in MB/GB/TB             |
| `du`          | Show disk usage per directory           |
| `du -h`       | Show disk usage in MB/GB/TB             |
| `free`        | Show memory usage                       |
| `free -h`     | Show memory usage in MB/GB/TB           |
| `uptime`      | Show uptime                             |
| `whoami`      | Show current user                       |
| `uname`       | Show system information                 |
| `uname -a`    | Show all system information             |

---

## Shutdown/Reboot Commands

| Command               | Description                                |
|-----------------------|--------------------------------------------|
| `shutdown`            | Power off the system after 1 minute       |
| `shutdown now`        | Power off the system immediately          |
| `shutdown 16:30`      | Power off the system at 16:30             |
| `shutdown -c`         | Cancel a scheduled shutdown               |
| `reboot`              | Reboot system                             |
| `poweroff`            | Power off system                          |

---

## Process Commands

| Command          | Description                            |
|------------------|----------------------------------------|
| `ps`             | List processes                        |
| `ps -ef`         | List all processes                    |
| `top`            | Display processes in real time        |
| `kill <pid>`     | Kill process                          |
| `pkill <name>`   | Kill process with name                |
| `killall <name>` | Kill all processes with name          |

---

## Secure Shell (SSH) Commands

| Command                      | Description                                |
|------------------------------|--------------------------------------------|
| `ssh-keygen`                 | Generate SSH key pair                     |
| `ssh-add <key>`              | Add SSH key to SSH agent                  |
| `ssh-add -l`                 | List SSH keys in SSH agent                |
| `ssh-copy-id <user>@<host>`  | Copy SSH key to `<host>` for `<user>`      |
| `ssh <host>`                 | Connect to `<host>` as current user       |
| `ssh <user>@<host>`          | Connect to `<host>` as `<user>`           |
| `scp <src> <host>:<dest>`    | Copy local file `<src>` to `<dest>` on `<host>` |
| `scp <host>:<src> <dest>`    | Copy file `<src>` from `<host>` to local `<dest>` |

---

## APT Commands (Debian/Ubuntu)

| Command               | Description                            |
|-----------------------|----------------------------------------|
| `apt install <pkg>`   | Install package                       |
| `apt remove <pkg>`    | Remove package                        |
| `apt purge <pkg>`     | Remove package and config files       |
| `apt update`          | Update package list                   |
| `apt upgrade`         | Upgrade packages                      |
| `apt search <term>`   | Search for package                    |

---

## Other Commands

| Command           | Description                                |
|-------------------|--------------------------------------------|
| `echo <msg>`      | Print message to stdout                   |
| `man <cmd>`       | Display manual page for `<cmd>`           |
| `history`         | Display history of given commands         |
| `which <cmd>`     | Find path to executable `<cmd>`           |
| `whereis <cmd>`   | Locate binary, source, and manual page for `<cmd>` |

---

## IO Redirection

| Command                  | Description                                |
|--------------------------|--------------------------------------------|
| `<cmd> > <file>`         | Replace contents of file with output      |
| `<cmd> >> <file>`        | Append output to file                     |
| `<cmd> < <file>`         | Redirect input from file                  |
| `<cmd> 2> <file>`        | Redirect `stderr` to file                 |
| `<cmd> &> <file>`        | Redirect `stdout` and `stderr` to file    |

---

## Pipe Commands

| Command                  | Description                                |
|--------------------------|--------------------------------------------|
| `<cmd1> | <cmd2>`        | Pipe `stdout` to next command             |
| `<cmd1> |& <cmd2>`       | Pipe `stderr` to next command             |

---

## Bash Shortcuts

| Shortcut     | Description                  |
|--------------|------------------------------|
| `Ctrl + C`   | Stop current command         |
| `Ctrl + A`   | Go to beginning of line      |
| `Ctrl + E`   | Go to end of line            |
| `Ctrl + K`   | Cut current line             |
| `Ctrl + L`   | Clear screen                 |

---

## Directory Structure

| Directory    | Description                         |
|--------------|-------------------------------------|
| `/`          | Root                                |
| `/bin`       | Binary or executable programs       |
| `/etc`       | System configuration files          |
| `/home`      | User home directories               |
| `/opt`       | Optional or third-party software    |
| `/tmp`       | Temporary files                    |
| `/usr`       | User programs                      |
| `/var`       | Variable data                      |
| `/var/log`   | Log files                          |
