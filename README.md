# Tech Cheat Sheet
Various software keybinds and other helpful references

# Visual Studio Code
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

`Ctrl + Shift + U` - Open Output

`Ctrl + Shift + L` - Select All Occurrences

`Ctrl + G` - Go to Line

`Ctrl + Page Down/Up` - Focus Next Editor Group

`Ctrl + tilde` - Terminal

`Ctrl + Shift + F` - Search all Files in Project

`Ctrl + K, F` - Closes working dir.

`Ctrl + K, Ctrl + O` - Open working dir.

`Alt + F12` - Peak definition.

`Ctrl + K , Ctrl + I` - DEFAULT Show hover.

`Ctrl + E` - Show hover.

# Windows Terminal

`Ctrl + Shift + W` - Close Tab/Pane

`Ctrl + T` - New Tab

`Shift + Alt + [-, +]` - New *pane* split horizontal and vertical, respectively

`Alt + [Left, Right, Up, Down]` - Shift pane focus

# Linux

## Admin
`lastlog` - Shows a list of all accounts and their date of login

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

```

# Git

`git init` - Initializes git for the pwd; adds git files.

`git add [<file>, <file>, ...]` - Tracks new file(s).

`git rm --cached <file>` - Stops tracking file in repo, doesn't delete from filesystem.

`git status` - Shows state of current branch.

`git ls-files` - Show tracked files.

`git commit -[a=AllTracked, m=Message, ] --[ammend=Ammends previous commit, no-edit=Keeps commit message, reuse-message HEAD=Keeps commit msg from HEAD, ] <msg?>` - Makes a commit.

`git diff <file?>` - Shows changes.

`git log [--graph?]` - Shows log of commits.

`git log --all -- <filename>` - Searches through git history for file.

`git branch -[d=Delete, m=Rename] <branch> <newname>` - Shows branches.

`git checkout -[b=NewBranch] <branch>` - Changes current branch.

`git checkout -- <file>` - Resets a file to HEAD, ignoring local changes.

`git merge [--squash="Collaspe all commit in merging branch to single."] <branch>` - Merge branch into current.

`git mergetool` - See merge conflicts.

`git remote add origin <url>.git` - Adds remote origin to repo.

`git remote -v` - Shows your current remote origin/fetch urls.

`git reset [--hard="Ignores local changes", --soft="Keeps local changes"]` - Resets all files to last commit.

`git reset --soft HEAD~1` - Undo last commit and drop changes into working dir.

`git push -u origin <branch>` - Sets the origin as the default for push calls, then pushes branch.

`git push origin --delete <branch>` - Deletes remote branch.

`git stash -[u=Untracked Files, ]` - Stash working dir.

`git stash list` - Lists all stash objects.

`git stash pop` - Pops the top-most stash entry to working dir and removes entry from stash list.

`git stash apply` - Pops the top-most, keep changes in stash.

`git stash save "desc."` - Saves working dir with name/desc.

`git stash drop stash@{0}` - Drops stash at index 0.

`git stash push -[u untracked] -[m message] path/to/file` - Stash a single untracked file

`git show --pretty="" --name-only <commit hash>` - Shows new files in commit.

## Examples

### Merge Conflicts

```bash
# Checkout ours/theirs to solve merge conflicts
git checkout [--ours, --theirs] filename.c
git add filename.c
git pull origin master
```

### Rebase Git-flow

```bash
# update master first
git checkout master && git pull

# get on feature branch to rebase
git checkout feature-branch

# Add a tag to go back to, should something go wrong
git tag BACKUP

# rebase feature to master
git rebase master

# solve merge issues, if any
git mergetool

# continue rebase after fixing merge issues
git rebase --continue

# discard rebase if needed
# git rebase --abort
# git reset --hard BACKUP

# force-push to remote feature branch
git push -f
```

### Git Add Patch-mode

```bash
# enter patch-mode to select hunks of a file to be commited
git add -p

# HELP
# y - stage this hunk
# n - do not stage this hunk
# q - quit; do not stage this hunk nor any of the remaining ones
# a - stage this hunk and all that follow
# d - do not this hunk or any that follow
# s - split current hunk into more
# ? - help
```

### Replace local changes with Remote

```bash
# fetch changes from remote
git fetch

# reset your local to remote
git reset --hard origin/remote
```

# Tmux

`tux new` `tmux new-session` - Starts a new session

`tmux list-session` - Lists sessions

`tmux attach [-t session_name]` - Attaches to running session

`tmux kill-session -a [-t session_name]` - Kills all sessions; optional save supplied session

`prefix + [` - Enter scrollmode?

## Sessions

`:new` - Creates new session while inside Tmux

`prefix + d` - Detach

`prefix + $` - Rename session

`prefix + w` - Session list

`prefix + (` - Switch to the previous session

`prefix + )` - Switch to the next session

`prefix + L` - Switch to the last active session

## Windows

`prefix + c` - Creates new window

`prefix + ,` - Renames current window

`prefix + &` - Close current window

`prefix + 0..9` - Select window by number

`prefix + l` - Switches to the last active window

`prefix + p` - Switches to the previous window

`prefix + n` - Switches to the next window

`:move-window -r` - Refreshes window numbering

`:snap-window -t -1` - Moves current window to the left by 1

## Panes

`prefix + z` - Toggle panel zoom

`prefix + %` - Split window horizontal

`prefix + "` - Split window vertical

`prefix + x` - Kill pane

`prefix + o` - Switch to next pane

`prefix + ;` - Switch to last pane

`prefix + !` - Convert pane into window

`prefix + q` - Show pane numbers

`prefix + q 0..9` - Select pane by number

`:join-pane -s 2 -t 1` - Join Window2 with Window1 as panes

## Copy Mode

`prefix + [` - Enter copy mode

`\pattern` - Search down

# VIM

## Tips

`%` - Means across all lines

`/g` - Means global, otherwise only execute once per line

## Commands

`:e file` - Opens file inside Vi.

`:q!` - Quits without saving.

`:q` - Quits.

`:wq` - Writes and quits.

`:noh` - Clear last search highlight.

`:set number` - Enables line numbers

`:f` - Show file info?

`q/` - Search history; `:q` to close

`q:` - Command history; `:q` to close

`:help <topic>` - Shows help; `:q` to close

## Insert Mode

`i` - Insert at cursor.

`I` - Insert at beginning of line.

`a` - Insert after cursor.

`A` - Insert at end of current line.

`o` - Append a newline after current.

`O` - Append a newline above current.

`Ctrl + w` - Delete word backwards.

`Ctrl + h` - Delete character backwards.

`Ctrl + t` - Indent one.

`Ctrl + d` - De-indent one.

`Ctrl + n` - (Auto-Complete) Next match.

`Ctrl + p` - (Auto-Complete) Previous match.

`Ctrl + o` - Temporarily enter Normal Mode to enter a single command.

## Cursor Movement

`h,j,k,l` - Move cursor left,down,up,right

`H` - Move cursor to top of screen

`M` - Move cursor to middle of screen

`L` - Move cursor to bottom of screen

`w` - Jump forwards to the start of a word

`W` - Jump forwards to the start of a word (with punctuation)

`e` - Jump forwards to the end of a word

`E` - Jump forwards to the end of a word (with punctuation)

`b` - Jump backwards to the start of a word

`B` - Jump backwards to the start of a word (with punctuation)

`%` - Jump cursor to matching pair: '()', '[]', '{}'

`0` - Jump cursor to start of the line

`^` - Jump cursor to the first non-blank character of the line

`$` - Jump cursor to the end of the line

`g_` - Jump cursor to the last non-blank character of the line

`gg` - Goes to first position of buffer

`G` - Goes to last position of buffer

`5gg` `5G` - Go to line 5

`}` - Jump to next paragraph (or code block)

`{` - Jump to previous paragraph (or code block)

`[[` `]]` - Jump to next/previous symbol?

`zz` - Center screen on cursor

`zt` - Moves screen so cursor is on top

`zb` - Moves screen so cursor is on bottom

`Ctrl + e` - Moves screen down one line

`Ctrl + y` - Moves screen up one line

`Ctrl + f` - Moves screen up down page

`Ctrl + b` - Moves screen up one page

`Ctrl + d` - Move cursor and screen down half a page

`Ctrl + u` - Move cursor and screen up half a page

*Prefix a cursor move with a number to repeat. Ex. `50j` moves down 50 lines.*

## Editing

`r` - Replace character under cursor

`R` - Replace characters until ESC is pressed

`J` - Join line below with current, with a space between

`cc` `S` - Replace entire line

`c$` `Ctrl + c` - Replace line from cursor to end

`ciw` - Replace entire word

`cw` `ce` - Replace entire word from cursor

`u` - Undo

`U` - restore (undo) last changed line

`Ctrl + r` - redo

`s` - Delete character and substitute text

`.` - Repeat last command

## Macros

`qa` - Record macro named a

`q` - Stop recording

`@a` - Run macro named a

`@@` - Rerun last run macro

## Copy, Cut & Paste

`yy` - Yank (copy) a line

`2yy` - Yank (copy) two lines

`yw` - Yank the characters of the word from the cursor to the start of the next word

`yiw` - Yank the word under the cursor

`y$` - Yank from the cursor to the end of the line

`p` - Put (paste) after cursor

`P` - Put (paste) before cursor

`dd` - Delete line

`2dd` - Delete two lines

`dw` - Delete word from cursor to next word

`db` - Deletes from cursor to beginning of word

`dw` - Deletes word

`d[h,j,k,l]` - Deletes in the direction

`d[^,$]` - Deletes from the cursor to the beginning or end of the line, respectively.

`:3,5d` - Delete line 3 to 5

`diw` - Delete word under cursor

`gg dG` - Deletes all lines in buffer

`x` - Delete character

`:g/{pattern}/d` - Delete all lines containing pattern

`:g!/{pattern}/d` - Delete all lines NOT containing pattern

## Indent text

`>>` - Indent line one shift-width

`>>` - De-indent line one shift-width

`gg=G` - Re-indents entire buffer

`>%` - Indent block (cursor on brace)

`<%` - De-indent block (cursor on brace)

## Folding

`zR` - Unfold all

`zM` - Fold all

## Visual Mode

`v` - Enter visual mode, mark lines, then do a command

`V` - Enter visual mode with line selected

`o` - Move cursor to other end of marked area

`O` - Move cursor to other corner of marked block

`aw` - Mark a word

`ab` `a(` - Mark a block with ()

`aB` `a{` - Mark a block with {}

`at` - Mark a block with <> tags

`ib` `i(` - Mark an inner block with ()

`iB` `i{` - Mark an inner block with {}

`it` - Mark an inner block with <> tags

## Visual mode commands

`y` - Yank marked

`d` - Delete marked

`>` - Shift right

`<` - Shift left

`~` - Switch case

`u` - Changed marked to lowercase

`U` - Changed marked to uppercase

## Marks

`:marks` - Lists marks

`ma` - Sets current position for mark 'a'

``a` - Jumps to position for mark 'a'

``0` - Jumps to position where vim was previously exited

`:ju[mps]` - Lists of jumps

`:changes` - Lists of changes

## Search & Replace

`/pattern` - Search ahead for pattern

`?pattern` - Search backwards for pattern

`n` - Repeat search in same direction

`N` - Repeat search in opposite direction

`:noh` - Remove search highlight

`:%s/old/new/g` - Replace all old with new throughout buffer

`:%s/old/new/gc` - Replace all old with new throughout buffer with confirmations

`/orig/new` - Replace text

# Windows

## File Explorer

`F2` - Renames directory/file.

`Ctrl + x` - Cuts to clipboard.

`Ctrl + c` - Copies to clipboard.

`Ctrl + v` - Paste clipboard.

`Ctrl + Shift + v` - Format paste.

`Ctrl + z` - Undo.

`Ctrl + y` - Redo.

`Alt + ArrowKeys` - Backwards & Forwards through history.

## Desktop

`Win + ArrowKeys` - Moves window to different monitor, or min/max.

`Win + DownKey` - Minimizes everything.

`Win + d` - Shows desktop.

`Win + p` - Changes multi-display layout.

`Win + l` - Locks computer.

`Win + Shift + s` - Snipping Screenshot.

`Win + x` - Admin Panel.

`Ctrl + Shift + Esc` - Task Manager.

`Alt + Tab` - I mean... come on.

`Win + Tab` - More fancy alt-tab.

`Shift + F3` - Changes case in Word...

`Win + a` - Opens Action Center.

`Win + i` - Opens Settings.

`Win + m` - Minimizes all Windows.

`Win + Home` - Minimizes all but Current Window.

`Win + ,` - Quick Desktop Peak.

`Win + .` - Emoji & Gifs.

## Virtual Desktops

`Win + Ctrl + D` - New Desktop.

`Win + Ctrl + ArrowKeys` - Switch Between Desktops.

`Win + Ctrl + F4` - Closes Current Virtual Desktop.



# Blender

## Camera

`MB3` - Orbiting the view; rotating the view.

`Shift + MB3` - Pan view.

`NumPad .` - Snap view to selected object.

`NumPad 1` - Side-on view of selected object.

`NumPad 7` - Top-down view of selected object.

`~ + View Selected` - Snap view to selected object.

`Alt + MB3 Click Drag` - Snap to nearest view angle.

## General Keys

`G` - Grab

`S` - Scale

`R` - Rotate

`G/S/R + Z` - Locks to Z axis only.

`G/S/R + Y` - Locks to Y axis only.

`G/S/R + X` - Locks to X axis only.

`G/S/R + MB3` : Snaps to axis currently near.

`~` - Cursor menu

`X` - Delete selected object.

`Shift + A` - Add Menu at cursor.

`F3` - Search for things; shortcuts, info, etc...

`Tab` - Switch from edit/model mode.

`O` - Toggle Proportional Editing

`Alt + Z` - X-Ray mode; see through object...

`Shift + D` - Duplicate Selection.

`P` - Selection to separate object.

`Ctrl + L` - Select all of connected vertices.

`N` - Bring up another property window.

`A` - Select entire mesh.

`Alt + A` - Deselect.

`Alt + LeftClick` - Select row of vertices.

`Ctrl + I` - Invert selection.

`H` - Hide selection.

`Alt + H` - Reveal Hidden.

`E` - Extrude; pulls a new face out of the mesh.

`J` - Join vertices.

## Tips

- To make a donut less perfect, goto **Edit Mode**, turn on proportional edit, click a point and then hit G. Now scroll down to narrow the area affected.

- To see smooth objects: in **Object Mode** right click object, with it selected, and click **shade smooth**.

- To smooth mesh: in **Property Window** goto wrench, click **Add Modifier**, then **Subdivision Surface**.

- Select part of an object, hit **Shift + D** to duplicate it, hit **ESC** or **right-click** to cancel movement. Then hit **P** and **Selection** to make it a separate object.

- Add a **Solidify** modifier to icing, increased outset to 1.0 and decreased thickness. Move this modifier above Sub Surface for smooth thickness.

- Add vertices to mesh: Select mesh, **right click** then **Subdivide**. Doubles vertices in mesh.

- Turn on snapping to face when moving things: top of the window click **Snap**, then **Face** and **Project Individual Elements**.

# Gimp2

`[ ]` - Increase/decrease size of brush.

## Paths Tool

`Ctrl + Click` - Adds a new node.

`Ctrl + Drag` - Realign node?

`Shift + Ctrl + Click` - Delete node.

# Slack

`Ctrl + k` - Change chat channel

`Ctrl + z` - Unsend last message

`Ctrl + f` - Search in conversation

`Ctrl + g` - Search in everything

`Ctrl + Shift + m` - Goto mentions

`Ctrl + Shift + e` - Goto people

`Ctrl + n` - New message

# Chrome

`Ctrl + W` - Closes Tab.

`Ctrl + T` - New Tab.

`Ctrl + Shift + T` - Reopens last tab.

`Ctrl + Tab` - Cycles tabs.

`Ctrl + Page Up/Down` - Cycles tab.

`Ctrl + L` - Focuses search box.

`Alt + ArrowKeys` - History: back & forward.


# MySQL

`DROP TABLE [IF EXISTS] <name>;`

`DROP VIEW [IF EXISTS] <name>;`

`mysql -u username -p database_name < database_name.sql`

`CREATE VIEW <v_name> AS ...`

`SHOW FULL TABLES;`

`SHOW CREATE VIEW <view>;`

`... WHERE <field> LIKE 'string%';`

`DELETE FROM <table> WHERE <condition...>;`

`INSERT INTO <table> (<column>...) VALUES (<value>...);`

`SELECT * FROM <table> WHERE <condition>;`

`EXPLAIN ...query` - Shows query execution plan.

# Docker

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

`docker build -t image_name:tag --build-arg arg_name=arg_value .` - Builds an image with build-time environment variables

`docker images`

`docker volume ls`

`docker run -e "env_var_name=value" <image>` - Runs a container with supplied environment variable

`docker exec -it <container-name> /bin/bash` - Attack to running container; run bash

`docker stats` - Container resource usage information


# PHP

## CLI

`php -S localhost:8080 [-c ./php.ini]` - Built-in PHP dev web-server, with option specific ini file.

## Examples

### Class Auto-Loader
```php
// PHP Class Auto-loader
spl_autoload_register(function ($class) {
	include "path" . $class . ".class.php";
});
```

### Convert errors to exceptions
```php
// PHP Convert Errors to Exceptions
set_error_handler(function($errorNumber, $errorMessage, $errorFile, $errorLine) {
    throw new \ErrorException($errorMessage, 0, $errorNumber, $errorFile, $errorLine);
});
```

### Register shutdown function
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

# Godot
## Shortcuts
### General
 - `Ctrl + F1/F2/F3` - Switch to 2D/3D/Script view, respectively.
 - `Ctrl + Tab` - Switch tab forwards.
 - `Ctrl + Shift + Tab` - Switch tab backwards.
 - `F` - Center viewport onto the selected node?
 - `W` - Move Mode
 - `Q` - Select Mode
 - `E` - Rotate Mode
 - `S` - Scale Mode
 - `R` - Ruler Mode
 - `Shift + S` - Smart snap
 - `Shift + G` - Grid snap
 - `Ctrl + '` - Show grid
 - `Y` - Show guides
 - `Alt + Drag` - Move nodes
 - `Alt + Shift + Drag` - Move node on axis.
 - `Ctrl + Drag` - Rotate node.
 - `Ctrl + Alt + Drag` - Scale node.
 - `Ctrl + Alt + Shift + Drag` - Scale uniform node.
 - `Alt + 1` - <CUSTOM> Switch to 2D editor.
 - `Alt + 2` - <CUSTOM> Switch to script editor.
### Scene Tree
 - `Ctrl + A` - Add new node.
 - `Ctrl + Shift + A` - Add new child node.
 - `Ctrl + N` - Create new scene.
 - `Ctrl + D` - Duplicate node.
 - `Ctrl + Up/Down` - Move node up/down tree, respectively.
### Script Editor
 - `Ctrl + Shift + F` - Search through all scripts.
 - `Ctrl + \` - Toggle script panel visibility.
 - `Ctrl + Shift + F11 - Focus mode.
 - `Ctrl + R` - Replace modal.
 - `Ctrl + Shift + ,/.` - Go to next/previous script file, respectively.
 - `Ctrl + Alt + O` - Quick open script.
 - `Ctrl + Shift + O` - Quick open scene.
## Tips
 - Collion layers define which layer the object is in, while mark defines which layers it can interact with.
 - Use print_debug() to show where it is being printed from.
 - To click on a specific node that is stacked on others, use `Select Mode` and alt right-click to select.


# GIMP

## Shortcuts
 - `O` - Color picker
 - `N` - Pencil tool
 - `E` - Eraser
 - `X` - Swap colors
