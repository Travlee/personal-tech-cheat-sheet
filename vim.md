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