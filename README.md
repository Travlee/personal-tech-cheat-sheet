# Useful Shortcuts & Tips

---

*Shortcuts for applications: VS Code, Bash shell, Git, and Vim*. Also some tips!

*By Travis Lee Presnell*



## Visual Studio Code

- Close file - `Ctrl + W`
- Toggle File Explorer `Ctrl + B`
- Switch Editors - `Ctrl + PageUp/Down`
- Navigate to File - `Ctrl + P`
- Navigate to Symbol - `Ctrl + Shift + O`
- Get Definition - `F2`
- Get all References - `Shift + F2`
- File History  - `Ctrl + Tab`
- Select Line - `Ctrl + I`
- Open Problems - `Ctrl + Shift + M`
- Select All Occurrences - `Ctrl + Shift + L`
- Go to Line - `Ctrl + G`
- Focus Next Editor Group - `Ctrl + Page Down/Up`
- Terminal	- `Ctrl + tilde` 
- Search all Files in Project - `Ctrl + Shift + F`

---

## Bash

### Admin

`lastlog` - Shows a list of all accounts and their date of login.

`apt-cache search <string>` - With Debian systems, searches packages for pattern.

`apt-get update && apt-get upgrade` - Updates package-list THEN installs new packages.

`chown` - Changes ownership of directory/file.

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

### Other

`cat` - Outputs contents of files.

`mkdir` - Makes a directory.

`echo <variable>` - Outputs to stout. 

`ssh user@host` - SSH to user on host.

`grep -[v=NOT] <pattern> <file>` - Regex to search input. 

`rm -[r=recursive, f=force]` - Removes file.

`tails -[f=realtime, n=lines, v=verbose] <path>` - Outputs last 10 lines of files.

`watch tail <file>` - Another way to watch a file in real time.

`find -type [f=file] -[iname=ignorecasename] <string> -print` - Find Files.

`find | grep -[i=ignorecase] <string>` - Find files "hack."

### Window

`Shift + PageUp/Down` - Scroll lines in terminal.

`Ctrl + U` - Clears current line behind cursor.

`Ctrl + A` - Moves Cursor to Beginning of Line.

`Ctrl + K`  - Clears Current Line in Front of Cursor.

`Ctrl + U` - Clears last word.

### Important Files

`/etc/passwd` - All user accounts and information.

`/var/log/auth.log` - Authorization Log File.

`/var/log/apache/[access.log, error.log]` - Apache Logs.

---

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

---

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



---

## Windows

### File Explorer

`F2` - Renames directory/file.

`Ctrl + X` - Cuts to clipboard.

`Ctrl + C` - Copies to clipboard.

`Ctrl + V` - Paste clipboard.

`Ctrl + Shift + V` - Format paste.

`Ctrl + Z` - Undo.

`Ctrl + Y` - Redo.

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

---

## Chrome

`Ctrl + W` - Closes Tab.

`Ctrl + T` - New Tab.

`Ctrl + Shift + T` - Reopens last tab.

`Ctrl + Tab` - Cycles tabs.

`Ctrl + Page Up/Down` - Cycles tab.

`Ctrl + L` - Focuses search box.

`Alt + ArrowKeys` - History: back & forward.