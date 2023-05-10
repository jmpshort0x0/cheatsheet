## Quitting
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Quit and save | `ZZ` or `:wq` |
| Quit without saving | `ZQ` or `:q!` |
| Write current buffer | `w` |


## Insertions
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Insert before cursor | `i` |
| Insert at the first nonblank on current line | `I` |
| Append after cursor | `a` |
| Append at the end of line | `A` |
| Open a new line below current line | `o` |
| Open a new line above current | `O` |


## Markers
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Set marker point 			| `m<Capital letter (to avoid confusion with other cmds)>`								|
| Move to marker 	| `` `<Capital letter>``	|
| Go to main working file 	| `:first`	|
| show marks | `:marks` |



### Marking with signature plugin
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
|Toggle mark 'x' and display it in the leftmost column| `mx` |
|Remove mark 'x' where x is a-zA-Z| `dmx` |
|Place the next available mark| `m,` |
|If no mark on line, place the next available mark. Otherwise, remove (first) existing mark.| `m.` |
|Delete all marks from the current line|`m-`|
|Delete all marks from the current buffer|`m<Space>`|
|Jump to next mark| `` ]` ``|
|Jump to prev mark| `` [` `` |
|Jump to start of next line containing a mark|` ]'`|
|Jump to start of prev line containing a mark| `['`|
|Jump by alphabetical order to next mark|`` `] ``|
|Jump by alphabetical order to prev mark|`` `[ ``|
|Jump by alphabetical order to start of next line having a mark|`']`|
|Jump by alphabetical order to start of prev line having a mark|`'[`|
|Open location list and display marks from current buffer|`m/`|
| Toggle the corresponding marker !@#$%^&*()|`m[0-9] `|
| Remove all markers of the same type|`m<S-[0-9]> `|
|Jump to next line having a marker of the same type|`]-`|
|Jump to prev line having a marker of the same type|`[-`|
|Jump to next line having a marker of any type|`]=`|
|Jump to prev line having a marker of any type|`[=`|
|Open location list and display markers from current buffer|`m?`|
|Remove all markers|`m<BS>`|


## File Management (netrw)

| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Make directory 			| `:!mkdir <foldername>`								|
| Change directory 	| `:cd <path>`	|
| Show working directory | `:pwd` |
| Check runtimepaths | `:set runtimepath?` |
| Check paths | `:set path?` |
| Check include library paths | `checkpath!` |
| source file for configs | `:so <path\>` |
| Open path with netrw 	| `:e <path\>`	|
| Create dir with netrw 	| `d`	|
| Create file with netrw 	| `%`	|


## Movement
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Up 			| `k`								|
| Down 			| `j`								|
| Left 			| `h`								|
| Right 			| `l`								|
| Move to beginning of next word | `w` |
| Move to back to the beginning of a word | `b` |
| Move to end of next word | `e` |
| Move to back to the end of a word | `ge` |
| Move to beginning of next WORD | `W` |
| Move to back to the beginning of a WORD | `B` |
| Move to end of next WORD | `E` |
| Move to back to the end of a WORD | `gE` |
| Re-align line to the top 			| `zt`								|
| Re-align line to the middle 			| `zz`								|
| Re-align line to the bottom 			| `zb`								|
| Re-align line to the bottom 			| `zb`								|
| Move to top of current/visible scren | `H` |
| Move to middle of current/visible scren | `M` |
| Move to bottom of current/visible scren | `L` |
| Go to the first line 			| `gg`								|
| Go to the last line 			| `G`								|
| Go to the beginning of first nonblank of the line		| `^`								|
| Go to the beginning of the line		| `0`								|
| Go to the end of the line			| `$`								|
 
## Yank/Put to/from register ("" or "0) - Copy/Paste
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Yank line | `yy` |
| Yank word | `yw` |
| Yank to end of word | `ye` |
| Yank to <char> | `yt<char>` |
| Yank to space | `yt ` |
| Search for yanked string | `/ CTRL+R 0` |
| Put register content at the end of cursor | `p` |
| Put register content before the cursor | `P` |
| Yank up to <keyword> | `y/<keyword>/e` |
 
Note: for `y/<keyword>/e`, the yank will get copied everything up to and including cursor to <keyword> but the search buffer will only contain <keyword>
 
 
## Manipulation
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Delete char at cursor 			| `x` or `dl`	|
| Delete char left of cursor 			| `X` or `dh`	|
| Delete delete to end of line from cursor 			| `D` or `d$`	|
| Delete word 			| `dw`	|
| Delete line 			| `dd`	|
| Change to end of line 			| `C` or `c$`	|
| Change char at cursor 			| `s` or `cl`	|
| Change whole line 			| `S` or `cc`	|
| Change word 			| `cw`	|
| Change WORD 			| `cW`	|
| Join line / delete line break | `J` |

### word / sentence / paragraphs
below uses a **prefix** as the command, for example `aw` would need a prefix of `d` to make `daw`

| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Around word 			| `aw`	|
| Within word | `iw` |
| A sentence | `as` |
| Inner sentence | `is` |
| A paragraph | `ap` |
| Inner paragraph | `ip` |

### programming language context
below uses a **prefix** as the command, for example `i"` would need a prefix of `c` to make `ci"`


| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Around "\\'\\`\\)\\]\\}\\> 			| `` a"\'\`\)\]\}\> ``	|
| Within "\\'\\`\\)\\]\\}\\>			| `` i"\'\`\)\]\}\> ``	|


| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Around tag block 			| `at`	|
| Within tag block 			| `it`	|

example : `<title>Hello Earthlings</title>`. `cit` will remove `Hello Earthlings` and change to edit mode

## Registers
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| View registers 			| `:reg`								|
| Access register | `"<register>` |
| Expression register | `"=` |
| Search register or last search command | `"/` |
| Most recent command | `":` |
| Current file path | `"%` |
| Copy file path to clipboard | `:let @+=@%` + is the clipboard register, let is used to write to a register |
| clipboard register | `"*` |
| copy to clipboard | `"*yy` |
| paste from clipboard | `"*p` |


## Searching
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Search forward of current word 			| `*`								|
| Search backward of current word 			| `#`								|
| Search for word | `/<word>` |
| Search forward for next instance of the hit | `n` |
| Search backward for next instance of the hit | `N` |
| Search forward for next instance of <char> | `f<char>` |
| Search backward for next instance of <char> | `F<char>` |
| Search forward until (one char before) the next instance of <char> | `t<char>` |
| Search backward until (one char after) the next instance of <char> | `T<char>` |
 
 

## Visual
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Visual mode by character | `v` |
| Visual mode by line | `V` |
| Visual mode by block | `ctrl V` |
| Move to the end of the selection | `o` |
| Move to the beginning of selection | `O` |
 
 
## Split Screen
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| New horizontal split | `:new` or `CTRL w n` |
| New vertical split | `:vnew` or `CTRL w N` |
| Split horizontally | `:split` or `CTRL w s` |
| Split vertically | `:vsplit` or `CTRL w v` |
| Close a window | `:close` or `CTRL w c` |
| Close all except current window | `:only` or `CTRL w o`|
| Move between splits | `CTRL w w` |
| Move around based on current (up/down/left/right) | `CTRL w k/j/h/l` |
| Move to top left / bottom right | `CTRL w t/b` |
| Move to last accessed | `CTRL w p` |
| Rotate windows clockwise | `CTRL w r` |
| Rotate windows counter clockwise | `CTRL w R` |
| Move current window top/bottom/left/right | `CTRL w K/J/H/L` |
| Reset all window sizes | `CTRL w =` |
| Decrease window height | `CTRL w -` |
| Increase window height | `CTRL w +` |
| Decrease window width | `CTRL w <` |
| Increase window width | `CTRL w >` |
| Move current window to new tab | `CTRL w T` |
 
## Tabs
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Move forward a tab | `gt` |
| Move backward a tab | `gT` |
| List tabs | `:tabs` |

 
 ## fzf
| Description				| Command								|
|---|---|
| Search through files | `:Files` |
| Search via ag | `:Ag` |
| Search via rg | `:Rg` |

 
## Other
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Select all 			| `ggVG`								|
| Match parenthesis | `%` |
 


