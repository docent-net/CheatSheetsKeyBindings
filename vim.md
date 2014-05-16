# VIM cheat-sheet: #

## miscellaneous
- `<leader>z` - nice edit mode (no distractions)
- `<leader>ss` - spell checking
- `<leader>o` - bufexplorer
- `<leader>f` - list of most recent used files

## Matching
- `%` - jump between matches (brackets etc)
- by matchit plugin:
    - `g%` - cycle backwards through specified groups (by |b:match_words|)
    - `a%` - in V selects all the matching group

## Indenting: ##
- `>` (single indent)
- `Vjjjjjj>` (block indent)
- `>%` (indent braced or bracketed block)
- `=%` - reindent braced or bracketed block
- `]p` - align pasted block
- `gg=G` - reindent whole buffer

- (insert mode)
    - `ctrl-t` - indent current line
    - `ctrl-d` - remove indent at current line

## windows / buffers: ##
- `:(v)split` - (vertical/horizontal) split
- `ctrl + w + w` - move between windows
- `:ls` - list buffers
- `:b2` - go to buffer 2
- resize windows:
    - `ctrl + +/-` - resize horizontally by 1 line
    - `ctrl + w + </>` - reize vertically by 1 char
    - `ctrl + w + =` - autoadjust vertically
    - `ctrl + w + _` - autoadjust horizontally

## characters ##
- `:%s/\a/&/g` - number of letters in buffer
- `:%s/\S/&/g` - number of non-whitespace characters

## folding: ##
- `F9 / space / zo / zc` - (un)fold current context
- `zO / zC` - (un)fold all

## GPG: ##
- gnupg.vim: <https://github.com/jamessan/vim-gnupg>
- `:GPGEditRecipients` - edit list of recipients
- `:GPGViewRecipients` - view thew list of recipients
- `:GPGEditOptions` - options for encryption
- `:GPGViewOptions` - list of all options
- more: <http://www.vim.org/scripts/script.php?script_id=3645>

## gundo: ##
- toggle: `F5`
- manual: <http://sjl.bitbucket.org/gundo.vim/#usage>
- `j/k/gg/G` - moving
- `enter <cr>` - apply change
- `p` - preview selected change
- `P` - replay

## surround: ##
- <https://github.com/tpope/vim-surround>
- `cs'"` - zamienia ' na " w otoczeniu
- `V + S + TAG` - wrap selected text with something
- `cs'<q>` - change ' to <q>...</q>
- `ds"` - removes delimiters
- `yssb + yss)` - wrap entire line with )
- ``ysiw` `` - wrap current word with `` ` ``

## gist: ##
- `:Gist` - pushes current buffer
    `-p` - private mode
    `-a` - anonymous mode
## evervim: ##
    - <https://github.com/kakkyz81/evervim/blob/master/doc/evervim.txt>
    - `:EvervimNotebookList`
    - `:EvervimListTags`
    - `:EvervimSearchByQuery` query

## vim-node ##
- `gf` - inside require("...") to jump to source and module files.
- `[I` - on any keyword to look for it in the current and required files.
- `:Nedit module_name` to edit the main file of a module.
- `:Nedit module_name/lib/foo` to edit its lib/foo.js file.
- `:Nedit .` to edit your Node projects main (usually index.js) file.
- `<C-w>f` - top open the file under the cursor in a new vertical split

## vim-grep ##
- `:vimgrep /Users/ **/*.js`
- `:vimgrep /Users/ **/*.js **/*.coffee`
- `:cope` - show results in quick list window
- `<leader>cc` - copy the quick list into new buffer
- `:g/models/d` - delete all lines with 'model' word
- `:g!/import/d` - delete all lines without 'import' word

## encryption ##
- all `.gpg` files will be automatically encrypted with gpg
- `:X` - will encrypt file with blowfish

## superstart ##
- when in visulmode:
    - `*` key will search forwards for selection
    - `#` key will search backwards for selection
    - `gv` will vimgrep fpr selection
    - selections will be escaped :)
