# Vimium Chrome Plugin
Modifier keys are specified as <c-x>, <m-x>, <a-x> for ctrl+x, meta+x, and alt+x respectively.

## Navigating the current page
- `?` - Show the help dialog for a list of all available keys
- `h` - Scroll left
- `j` - Scroll down
- `k` - Scroll up
- `l` - Scroll right
- `gg` - Scroll to top of the page
- `G` - Scroll to bottom of the page
- `d` - Scroll down half a page
- `u` - Scroll up half a page
- `f` - Open a link in the current tab
- `F` - Open a link in a new tab
- `r` - Reload
- `gs` - View source
- `i` - Enter insert mode -- all commands will be ignored until you hit esc to exit
- `yy` - Copy the current url to the clipboard
- `yf` - Copy a link url to the clipboard
- `gf` - Cycle forward to the next frame

## Navigating to new pages
- `o` - Open URL, bookmark, or history entry
- `O` - Open URL, bookmark, history entry in a new tab
- `b` - Open bookmark
- `B` - Open bookmark in a new tab

## Using find
- `/` - Enter find mode -- type your search query and hit enter to search or esc to cancel
- `n` - Cycle forward to the next find match
- `N` - Cycle backward to the previous find match

## Navigating your history
- `H` - Go back in history
- `L` - Go forward in history

## Manipulating tabs
- `J, gT` - Go one tab left
- `K, gt` - Go one tab right
- `g0` - Go to the first tab
- `g$` - Go to the last tab
- `t` - Create tab
- `x` - Close current tab
- `X` - Restore closed tab (i.e. unwind the 'x' command)
- `T` - Search through your open tabs

## Additional advanced browsing commands
- `]]` - Follow the link labeled 'next' or '>'. Helpful for browsing paginated sites.
- `[[` - Follow the link labeled 'previous' or '<'. Helpful for browsing paginated sites.
- `<a-f>` - Open multiple links in a new tab
- `gi` - Focus the first (or n-th) text input box on the page
- `gu` - Go up one level in the URL hierarchy