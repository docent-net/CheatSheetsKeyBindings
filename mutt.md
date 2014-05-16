# Mutt cheat-sheet #
  Sending (composing) message:
    a - attach files
    b - edit BCC
    c - edit CC
    p - edit PGP options
    ALT-k - attach PGP pubkey
    ^f - forget PGP pass
    r - edit Reply-To
    s - change the subject
    t - edit recipients
    y - send msg
    CTRL-X - insert canned response (via vim/mutt-canned)
    CTRL-v - create new canned response from selected text (via vim/mutt-canned)
    TAB - show address book (when to, cc or bcc field is active)

  Main menu, reading message
    a - create new addressbook entry (only when using abook integration)
    c - change to a different mailfolder
      d - delete mailfolder
      shift + c - create mailbox
    C - copy selected msg to another inbox
    d -mark msg for deletion
    f - forward msg
    F - mark as important
    i - return from reading msg to main menu
    I - show msgs matching pattern
    j,k - change selected msg in main menu to next/prev
    m - compose a new msg
    o - change current sort method
    r - reply
    s - save cur msg to a file
    t - toggle a tag on msg or entire thread
    T - tag msgs matching a pattern
      ;WN - mark all messages as read
    u - unmark deletion
    v - view attachments
    ? - HELP
    ^| - clear and redraw the screen
    ALT-k - send public GPG key to someone
    - - move to prv page while reading msg
    <space> - move to next page while reading msg (or first page of next
    undeleted msg)
    / - pattern search in the headers of msgs
    l - search and limits view (filter)
    = - select first msg
    $ - sync mbox (deletes marked for deletion, checks for new mail)
    @ - display full address of sender
    * - marks last msg
    <number> - selects msg number...
    TAB - selects the next new msg

  Threads:
    - - collapse thread
    shift + - - collapse all threads
    # - break thread in 2
    & - link threads

  Useful for macros:
    t + ; + s + ? - tag choosen msgs and move to choosen directory
    c + ? + shift-C - create mailbox
    t + ; + W + n - mark as read (clear unread flag)
    T (same as above but marking multiple messages)
