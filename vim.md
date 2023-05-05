
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
|mx|Toggle mark 'x' and display it in the leftmost column|
|dmx|Remove mark 'x' where x is a-zA-Z|
|m,|Place the next available mark|
|m.|If no mark on line, place the next available mark. Otherwise, remove (first) existing mark.|
|m-|Delete all marks from the current line|
|m\<Space\> |Delete all marks from the current buffer|
|]`|Jump to next mark|
|[`|Jump to prev mark|
|]'|Jump to start of next line containing a mark|
|['|Jump to start of prev line containing a mark|
|`]|Jump by alphabetical order to next mark|
|`[|Jump by alphabetical order to prev mark|
|']|Jump by alphabetical order to start of next line having a mark|
|'[|Jump by alphabetical order to start of prev line having a mark|
|m/|Open location list and display marks from current buffer|
|m[0-9] | Toggle the corresponding marker !@#$%^&*()|
|m<S-[0-9]> | Remove all markers of the same type|
|]-|Jump to next line having a marker of the same type|
|[-|Jump to prev line having a marker of the same type|
|]=|Jump to next line having a marker of any type|
|[=|Jump to prev line having a marker of any type|
|m?|Open location list and display markers from current buffer|
|m\<BS\>|Remove all markers|


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
| Re-align line to the top 			| `zt`								|
| Re-align line to the middle 			| `zz`								|
| Re-align line to the bottom 			| `zb`								|
| Re-align line to the bottom 			| `zb`								|
| Move to top of current/visible scren | `H` |
| Move to middle of current/visible scren | `M` |
| Move to bottom of current/visible scren | `L` |
| Go to the first line 			| `gg`								|
| Go to the last line 			| `G`								|
| Go to the beginning of the line			| `^`								|
| Go to the end of the line			| `$`								|
 
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

## Registers
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| View registers 			| `:reg`								|
| Access register | `"<register>` |
| Expression register | `"=` |
| Search register | `"/` |
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
| Search for word | `/<word\>` |
| Search forward for next instance of the hit | `n` |
| Search backward for next instance of the hit | `N` |


## Other
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Select all 			| `ggVG`								|


