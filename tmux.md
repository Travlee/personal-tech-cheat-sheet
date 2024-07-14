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