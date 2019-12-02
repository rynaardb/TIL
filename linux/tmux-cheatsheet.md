# Tmux Cheatsheet

Tmux cheatsheet containing the most common / frequently used commands.

The main prefix is: `ctrl+b` followed by `:`

## new

`tmux` start a new session

`tmux -t NAME-OF-SESSION` start a new named session

## list

`tmux ls` list of tmux sessions

## attach

`tmux a -t NAME-OF-SESSION` attach to a named session

`tmux a  #` attached to a session by number

## kill

`tmux kill-session -t NAME-OF-SESSION` kills a named session

## sessions

`s` list of sessions

`$` name the current session

## tabs / windows

`create` create a new windows

`w` list of all windows

`n` next window

`p` previous window

`,` name the window

`&` close / kill the window

## panes / splits

`%` split vertically
`"` split horizontially
`o` swop panes
`x` kill pane

## misc

`d` detaches the session
`t` show big clock
`?` list shortcuts
`:` show the prompt
