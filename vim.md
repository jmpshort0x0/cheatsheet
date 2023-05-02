


## Markers

| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Set marker point 			| `m<Capital letter (to avoid confusion with other cmds)>`								|
| Move to marker 	| `` `<Capital letter>``	|
| Go to main working file 	| `:first`	|

### Marking with signature plugin
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
|mx|Toggle mark 'x' and display it in the leftmost column|
|dmxRemove mark 'x' where x is a-zA-Z|
|m,|Place the next available mark|
|m.|If no mark on line, place the next available mark. Otherwise, remove (first) existing mark.|
|m-|Delete all marks from the current line|
|m<Space> Delete all marks from the current buffer|
|]`|Jump to next mark|
|[`|Jump to prev mark|
|]'|Jump to start of next line containing a mark|
|['|Jump to start of prev line containing a mark|
|`]|Jump by alphabetical order to next mark|
|`[|Jump by alphabetical order to prev mark|
|']|Jump by alphabetical order to start of next line having a mark|
|'[|Jump by alphabetical order to start of prev line having a mark|
|m/|Open location list and display marks from current buffer|
|m[0-9] Toggle the corresponding marker !@#$%^&*()|
|m<S-[0-9]> Remove all markers of the same type|
|]-|Jump to next line having a marker of the same type|
|[-|Jump to prev line having a marker of the same type|
|]=|Jump to next line having a marker of any type|
|[=|Jump to prev line having a marker of any type|
|m?|Open location list and display markers from current buffer|
|m<BS>|Remove all markers|


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
| Re-align line to the top 			| `zt`								|
| Re-align line to the middle 			| `zz`								|
| Re-align line to the bottom 			| `zb`								|
| Re-align line to the bottom 			| `zb`								|
| Go to the first line 			| `gg`								|
| Go to the last line 			| `G`								|
| Go to the beginning of the line			| `^`								|
| Go to the end of the line			| `$`								|
  
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


## Other
| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Select all 			| `ggVG`								|

