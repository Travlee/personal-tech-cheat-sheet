# Useful Shortcuts & Tips

*Shortcuts for applications: VS Code, Bash shell, Git, and Vim*. Also some tips!

*By Travis Lee Presnell*



## Visual Studio Code

`Ctrl + W` - Closes active file

`Ctrl + B` - Toggle File Explorer

`Ctrl + PageUp/Down` - Cycle editors

`Ctrl + P` - Navigate to File

`Ctrl + Shift + O` - Navigate to Symbol

`F2` - Get Definition

`Shift + F2` - Get all References

`Ctrl + Tab` - File History

`Ctrl + I` - Select Line

`Ctrl + Shift + M` - Open Problems

`Ctrl + Shift + L` - Select All Occurrences

`Ctrl + G` - Go to Line

`Ctrl + Page Down/Up` - Focus Next Editor Group

`Ctrl + tilde` - Terminal

`Ctrl + Shift + F` - Search all Files in Project

`Ctrl + K, F` - Closes working dir.

`Ctrl + K, Ctrl + O` - Open working dir.



## Linux Commands

### Admin

`lastlog` - Shows a list of all accounts and their date of login.

`apt-cache search <string>` - With Debian systems, searches packages for pattern.

`apt-get update && apt-get upgrade` - Updates package-list THEN installs new packages.

`chown user:group <target>` - Changes ownership of directory/file.

`chgrp` - Changes group of directory/file.

`chmod [u,g,o,a] [+,-][r,w] <file>` - Changes permissions of directory/file.

`mount -[l=List, a=Reload]` - Mount points from fstab file.

`w` - Shows logged in users and what they are doing.

`last` - History of recent account logs.

`ifconfig` - Network interfaces.

`ln -s <target> <destination>` - Makes a symbolic link.

`ps` - Shows processes on machine.

`top` - Realtime process info.

`a2ensite, a2dissite` - Apache enable/disable sites config.

`apache2ctl -S` - Apache Service status w/ Virtual Hosts.

`a2enmod <mod>, a2dismod <mod>` - Apache enable/disenable mods.

`mkdir /mnt/ram && mount -t tmpfs tmpfs /mnt/ram -o size=8192M` - Creates a super fast ram disk.

`mkdir -p folder/{sub1,sub2}/{sub1,sub2,sub3}` - Quickly create directory structure.

`ssh -L 8000:127.0.0.1:80root@remoteserver.org -N` - Creates a tunnel from remote service on port 80 to local port 8000.

`disown -a && exit` - Disconnects all processes from current terminal and exits, leaving all processes started by that terminal to remain running.

`export ENVVAR="value"` - Defines an environment variable for current shell-env. 

### Other

`cat` - Outputs contents of files.

`mkdir` - Makes a directory.

`echo <variable>` - Outputs to stout.

`ssh user@host` - SSH to user on host.

`grep -[v=NOT] <pattern> <dir>` - Regex to search input.

`grep -[P=Regex][r=recursive][i=ignorecase] <pattern> <dir>` - Finds pattern in files.

`rm -[r=recursive, f=force]` - Removes file.

`tail -[f=realtime, n=lines, v=verbose] <path>` - Outputs last *n* lines of a file.

`tail -f <name> | grep <search_term>` - Pipes the live file to grep.

`watch tail <file>` - Another way to watch a file in real time.

`locate <file>` - Searches index-db for files.

`sudo updatedb` - Updates index-db for `locate`.

`find <path> -type [f=file, d=dir] -[iname=ignorecasename] <string> -print` - Find Files.

`find | grep -[i=ignorecase] <string>` - Find files *hacky*.

`find / -[name=filename, iname=filenameIGNORECASE]iname "*.s*"` - Finds all files in root that have an s in its extension.

`find . -path "*"` `find . -type d` - Finds all directories in pwd.

`sudo !!` - Run last used command as root.

`fc` - Opens last command ran in editor to make changes more easily, then runs once saved.

`yes | command` - Pipes yes input to command or script.

`> filename` - Empties a file without deleting it.

`export NEWENVVAR="new env variable"` - Creates a new environment variable

`curl [-I = headers,] <url>` - Curl 

`history | grep <filter>` - Search bash history 

### Terminal

`Shift + PageUp/Down` - Scroll lines in terminal.

`Ctrl + U` - Clears current line behind cursor.

`Ctrl + A` - Moves Cursor to Beginning of Line.

`Ctrl + E` - Moves to end of line.

`Ctrl + K`  - Clears Current Line in Front of Cursor.

`Ctrl + W` - Clears last word.

`Ctrl + X + E` - Opens an editor to type commands.

### Important Files

`/etc/passwd` - All user accounts and information.

`/var/log/auth.log` - Authorization Log File.

`/var/log/apache/[access.log, error.log]` - Apache Logs.

`/etc/os-release` - Operating system information.



## Git

`git init` - Initializes git for the pwd; adds git files.

`git add [<file>, <file>, ...]` - Tracks new file(s).

`git rm --cached <file>` - Stops tracking file, doesn't delete from filesystem.

`git status` - Shows state of current branch.

`git ls-files` - Show tracked files.

`git commit -[a=AllTracked, m=Message] <msg?>` - Makes a commit.

`git diff <file?>` - Shows changes.

`git log [--graph?]` - Shows log of commits.

`git branch -[d=Delete, m=Rename] <branch> <newname>` - Shows branches.

`git checkout -[b=NewBranch] <branch>` - Changes current branch.

`git merge <branch>` - Merge branch into current.

`git remote add origin <url>.git` - Adds remote origin to repo.

`git remote -v` - Shows your current remote origin/fetch urls.

`git push -u origin <branch>` - Sets the origin as the default for push calls, then pushes branch.

`git commit --amend --reuse-message HEAD` - Commits current changes with last commit message.

`git stash list` - Lists all stash objects.

`git stash pop` - Pops the top-most stash entry to working dir and removes entry from stash list.

`git stash apply` - Pops the top-most 


## VIM

### Insert Mode

`:e file` - Opens file inside Vi.

`:q!` - Quits without saving.

`:q` - Quits.

`:wq` - Writes and quits.

### Command Mode

`dd` - Deletes a whole line.

`v` - Starts copy.

`y` - Copies character under cursor.

`yy` - "Yanks" the whole line.

`12yy` - "Yanks" 12 lines.

`x` - Cuts character under cursor.

`p` - Pastes "yanked."

`i` - Insert mode.

`a` - Insert at end of current line.

`Esc` - Return to command mode.

`u` - Undo last change.

`Ctrl + R` - Redo

`/text` - Search for 'text' after the cursor.

`:noh` - Clear last search highlight.

`n` - Find next occurrence after searching.

`gg` - Takes you to the top of the code.

`=` - Fixes indents.

`G` - Fixes indents throughout the whole file.

`G$` - End of file.

### Buffer



## Windows 10

### File Explorer

`F2` - Renames directory/file.

`Ctrl + X` - Cuts to clipboard.

`Ctrl + C` - Copies to clipboard.

`Ctrl + V` - Paste clipboard.

`Ctrl + Shift + V` - Format paste.

`Ctrl + Z` - Undo.

`Ctrl + Y` - Redo.

`Alt + ArrowKeys` - Backwards & Forwards through history.

### Desktop

`Win + ArrowKeys` - Moves window to different monitor.

`Win + DownKey` - Minimizes everything.

`Win + D` - Hides everything and brings you to Desktop.

`Win + P` - Changes multi-display layout.

`Win + L` - Locks computer.

`Win + Shift + S` - Snipping Screenshot.

`Win + X` - Admin Panel.

`Ctrl + Shift + Esc` - Task Manager.

`Alt + Tab` - I mean... come on.

`Win + Tab` - More fancy alt-tab.

`Shift + F3` - Changes case in Word...

`Win + A` - Opens Action Center.

`Win + I` - Opens Settings.

`Win + M` - Minimizes all Windows.

`Win + Home` - Minimizes all but Current Window.

`Win + ,` - Quick Desktop Peak.

### Virtual Desktops

`Win + Ctrl + D` - New Desktop.

`Win + Ctrl + ArrowKeys` - Switch Between Desktops.

`Win + Ctrl + F4` - Closes Current Virtual Desktop.



## Chrome

`Ctrl + W` - Closes Tab.

`Ctrl + T` - New Tab.

`Ctrl + Shift + T` - Reopens last tab.

`Ctrl + Tab` - Cycles tabs.

`Ctrl + Page Up/Down` - Cycles tab.

`Ctrl + L` - Focuses search box.

`Alt + ArrowKeys` - History: back & forward.


## MySQL

`DROP TABLE [IF EXISTS] <name>;`

`DROP VIEW [IF EXISTS] <name>;`

`mysql -u username -p database_name < database_name.sql`

`CREATE VIEW <v_name> AS ...`

`SHOW FULL TABLES;`

`SHOW CREATE VIEW <view>;`

`... WHERE <field> LIKE 'string%';`


## Docker
`docker info`

`docker ps -a`

`docker-machine start`

`docker-machine env default`

`docker container ls`

`docker container`

`docker container stop`

`docker container prune`

`docker system prune`

`docker create -v /var/lib/mysql --name mysqldata mysql:5.7` - Creates a data volume with the mysql image

`docker run --name dev-container -volumes-from mysqldata -e MYSQL_ROOT_PASSWORD=root -p 3307:3306 base-image:latest`

`docker run -it --rm --name container-name --volumes-from mysqldatadb -e MYSQL_ROOT_PASSWORD=root -p 3306:3306 -p 80:80 base-image:latest`

`docker run --rm -it -p 80:80 -p 3306:3306 dev-image:latest`

`docker run -it --rm -v $(pwd):/var/www/html base-image:latest`

`docker build -t base-image:latest .` - Finds a dockerfile in the localdir and builds the image and tags it with base-image:latest

`docker images`

`docker volume ls`

`docker run -e "env_var_name=value" <image>` - Runs a container with supplied environment variable


## PHP

`php -S localhost:8080` - Built-in PHP dev web-server

`php -S localhost:8080 -c /etc/php/7.2/apache2/php.ini ` - Built-in PHP web-server with specific ini file.

```php
// PHP Class Auto-loader
spl_autoload_register(function ($class) {
	include "path" . $class . ".class.php";
});
```

```php
// PHP Convert Errors to Exceptions
set_error_handler(function($errorNumber, $errorMessage, $errorFile, $errorLine) {
    throw new \ErrorException($errorMessage, 0, $errorNumber, $errorFile, $errorLine);
});
```

```php
// PHP Register Shut-down Function - Handle Errors
register_shutdown_function(function() {
    $errorData = error_get_last();
    if (is_array($errorData)) {
        ob_end_clean();
        echo 'Error occured! - ' . $errorData['message'];
    }
});
```

