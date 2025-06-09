# Linux

## Admin
`lastlog` - Shows a list of all accounts and their date of login

'last -a | grep ssh` - Shows all users logged in with ssh

`apt-cache search <string>` - With Debian systems, searches packages for pattern

`apt-get update && apt-get upgrade` - Updates package-list THEN installs new packages

`chown -[R recursive,] user:group <file>` - Changes ownership of directory/file

`chgrp` - Changes group of directory/file

`chmod [u,g,o,a] [+,-][r,w] <file>` - Changes permissions of directory/file

`mount -[l=List, a=Reload]` - Mount points from fstab file

`lsblk` - List all devices and partitions

`w` - Shows logged in users and what they are doing

`last` - History of recent account logs

`ifconfig` - Network interfaces

`ln -s <target> <destination>` - Makes a symbolic link

`ps` - Shows processes on machine

`ps -eH | less` - Shows process by all accounts into a hierarchy

`top` - Realtime process info

`a2ensite, a2dissite` - Apache enable/disable sites config

`apache2ctl -S` - Apache Service status w/ Virtual Hosts

`a2enmod <mod>, a2dismod <mod>` - Apache enable/disenable mods

`mkdir /mnt/ram && mount -t tmpfs tmpfs /mnt/ram -o size=8192M` - Creates a super fast ram disk

`mkdir -p folder/{sub1,sub2}/{sub1,sub2,sub3}` - Quickly create directory structure

`ssh -L 8000:127.0.0.1:80root@remoteserver.org -N` - Creates a tunnel from remote service on port 80 to local port 8000.

`disown -a && exit` - Disconnects all processes from current terminal and exits, leaving all processes started by that terminal to remain running.

`export ENVVAR="value"` - Defines an environment variable for current shell-env.

`sed 's/\([0-9]\{1,3\}\.\)\{3,3\}[0-9]\{1,3\}/x.x.x.x/g' in.txt > out.txt` - Remove all IPs from a file.

`source ~/.bashrc ` OR `. ~/.bashrc` OR `exec bash` - Reloads bashrc file.

`crontab -l` - List running cronjobs.

`crontab -e` - Edit current user's cronjobs.

`find / 2>/dev/null | grep -i "pattern"` - Find files & hide stderr output.

`scp -[i identityfile, ] <target> <user@host:/tmp/destination>` - Secure copy to/from remote host.

`iptables -L` - Firewall rules.

## Other

`cat` - Outputs contents of files.

`cat >> file` - Cat in append mode.

`mkdir` - Makes a directory.

`echo <variable>` - Outputs to stout.

`ssh user@host` - SSH to user on host.

`grep -[P=Regex, F=ignore_special_charatcers, r=recursive, i=ignorecase, n=line_number, c=count, v=inverse] <pattern> <path>` - Searching input for patterns.

`rm -[r=recursive, f=force]` - Removes file.

`tail -[f=realtime, n=lines, v=verbose] <path>` - Outputs last *n* lines of a file.

`tail -f <name> | grep <search_term>` - Pipes the live file to grep.

`watch tail <file>` - Another way to watch a file in real time.

`lnav <file> <file2> ...` - Better way to watch log files for extended periods. REQUIRES LNAV PACKAGE!

`locate <file>` - Searches index-db for files.

`sudo updatedb` - Updates index-db for `locate`.

`find <path> -[type f=file, d=dir] -[iname=ignore_case] -[time <days_since_accessed>]<pattern> -print` - Find Files.

`find / -size -5M -and -size +2M` - Finds files in root larger than 2MB and smaller than 5MB.

`find | grep -[i=ignorecase] <string>` - Find files *hacky*.

`find / -[name=filename, iname=filenameIGNORECASE] "*.s*"` - Finds all files in root that have an s in its extension.

`find . -path "*"` `find . -type d` - Finds all directories in pwd.

`sudo !!` - Run last used command as root.

`fc` - Opens last command ran in editor to make changes more easily, then runs once saved.

`yes | command` - Pipes yes input to command or script.

`> filename` - Empties a file without deleting it.

`export NEWENVVAR="new env variable"` - Creates a new environment variable

`curl [-I = headers,] <url>` - Curl

`history | grep <filter>` - Search bash history

`less +G /path/to/file` - Opens less at bottom of file

## Terminal/Shell

`Shift + PageUp/Down` - Scroll lines in terminal.

`Ctrl + u` - Clears current line behind cursor.

`Ctrl + w` - Clears last word.

`Ctrl + x + x` - Toggle between start and current cursor position

`Ctrl + a/e` - Moves Cursor to beginning or end of command

`Alt + f/b` - Move cursor to previous/next word

`Ctrl + x + e` - Opens an editor to type commands.

`Ctrl + r` - Bash history search

`Ctrl + d` - Kills shell

## Important Files

`/etc/passwd` - User account information.

`/etc/shadow` - Secret user account information.

`/var/log/auth.log` - Authorization Log File.

`/var/log/apache/[access.log, error.log]` - Apache Logs.

`/etc/os-release` - Operating system information.

`/etc/environment` - Ubuntu environment file; update env vars.

## Misc

Add an alias to sudoers file -
```bash
sudo visudo
...
# Creates a user alias to be referenced later
User_Alias INSTALLERS = lee, zooey

# Gives all users in INSTALLERS access to apt-get with sudo
INSTALLERS	ALL=/usr/bin/apt-get
...
```

Bash script to test environment variables/directories/symbolic links
```bash
#!/bin/bash

# Test environment variable
if [ -z "$TEST_ENVVAR" ]; then
	echo "Environment variable doesn't exist!"
fi
# Inline
if [ -z "$TEST_ENVVAR" ]; then echo "Environment variable doesn't exist!"; fi

# Test if directory exists
if [ -d /path/to/dir ]; then echo "Found directory!"; fi

# Test for symbolic link
if [ -L /path/to/link ]; then echo "Found link!"; fi

# Test for file
if [ -e /path/to/file ]; then echo "Found file!"; fi

# Make dir and change into it faster
mkdir dir_name && cd $_

```
