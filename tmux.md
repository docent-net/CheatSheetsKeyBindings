Tmux cheat-sheet:
  tmux new -s session_name
  tmux attach -t session_name

    or:

    tmux new -d -s session-host-name
    tmux new -s session-client-name -t session-host-name

  tmux switch -t session_name
  tmux list-sessions
  tmux detach (prefix + d)

  prefix c - Create new window
  prefix d Detach current client
  prefix n Move to the next window
  prefix & Kill the current window
  prefix , Rename the current window
  prefix q Show pane numbers (used to switch between panes)
  prefix z - zoom in/out current pane
  prefix x - kill pane
  prefix ? List all keybindings
  prefix -/| - split hori/vert (customized via config)
  prefix arrows - move between panes (customized via config)

  prefix n - next window
  prefix p - previous windows
  prefix w - list all windows

  prefix ESC - vi mode
    v - selects from buffer
    y - copy
  prefix p - paste (previously copied in vim mode)
