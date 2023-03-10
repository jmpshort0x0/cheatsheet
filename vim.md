


## Markers

| Description				| Command								|
|---------------------------------------|-----------------------------------------------------------------------|
| Set marker point 			| `m<Capital letter (to avoid confusion with other cmds)>`								|
| Move to marker 	| `` `<Capital letter>``	|
| Go to main working file 	| `:first`	|

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
