# Usage Examples
prereq: `fd` (fd-find) and `ag` (The Silver Searcher) and `rg` (ripgrep)

## searching syntax

| Description | Command |
|----|----|
| signify end | `$` |
| signify beginning | `^` |
| not operator  | `!` |
| or operator  | `|` |
| exact match | `'` |
| and operator (implicit) | ` `|

example `.txt$ python project | prj !git`


## default command
sets the default searching parameters when using `fzf` when there is * **no additional input** * \
`export FZF_DEFAULT_COMMAND='find -L . -type f ! -path "*git*"'` or  \
`export FZF_DEFAULT_COMMAND='fd . --hidden --exclude ".git"'` or \
`export FZF_DEFAULT_COMMAND='rg --files --hidden --glob "!.git"'`

## commands


| Description | Command |
|----|----|
|fzf mode and paste contents on <enter>|`ctrl t`|
|cd via fzf| `cd **<tab>` or `cd $(find . -type d |fzf)` or `cd $(fd . --hidden | fzf)`|
|vi via fzf| `vi **<tab>` or `` vi -o `fzf` `` or `vi $(fzf)`|

  
## VIM
  
Prereqs: `ag` (The Silver Searcher) and `rg` (ripgrep)
  
| Description | Command |
|----|----|
| Files (runs `$FZF_DEFAULT_COMMAND` if defined)                                        | `:Files [PATH]`        |
| Git files (`git ls-files`)                                                            | `:GFiles [OPTS]`       |
| Git files (`git status`)                                                              | `:GFiles?`             |
| Open buffers                                                                          | `:Buffers`             |
| Color schemes                                                                         | `:Colors`              |
| [ag][ag] search result (`ALT-A` to select all, `ALT-D` to deselect all)               | `:Ag [PATTERN]`        |
| [rg][rg] search result (`ALT-A` to select all, `ALT-D` to deselect all)               | `:Rg [PATTERN]`        |
| Lines in loaded buffers                                                               | `:Lines [QUERY]`       |
| Lines in the current buffer                                                           | `:BLines [QUERY]`      |
| Tags in the project (`ctags -R`)                                                      | `:Tags [QUERY]`        |
| Tags in the current buffer                                                            | `:BTags [QUERY]`       |
| Marks                                                                                 | `:Marks`               |
| Windows                                                                               | `:Windows`            |
| `locate` command output                                                               | `:Locate PATTERN`      |
| `v:oldfiles` and open buffers                                                         | `:History`             |
| Command history                                                                       | `:History:`            |
| Search history                                                                        | `:History/`            |
| Snippets ([UltiSnips][us])                                                            | `:Snippets`            |
| Git commits (requires [fugitive.vim][f])                                              | `:Commits [LOG_OPTS]`  |
| Git commits for the current buffer; visual-select lines to track changes in the range | `:BCommits [LOG_OPTS]` |
| Commands                                                                              | `:Commands`            |
| Normal mode mappings                                                                  | `:Maps`                |
| Help tags \<sup id="a1"\>\[1\](#helptags)\</sup\>                                           | `:Helptags`            |
| File types |`:Filetypes`           |


## flags

| Description | Command |
|----|----|
| exact matches | `-e` or `--exact` |
| multi line matches | `-m` or `--multi`|
| case insensitive | `-i`|
| case sensitive | `+i` |
| toggle section and move up | `<TAB>`|
| toggle selection and move down | `<SHIFT><TAB>`|
| search on the nth fields | `--nth=<num>` |
| change delimter from <space> to <delim> | `--delimiter=<delim>` |
  
### nth usage

| Description | Command |
|----|----|
| match 2nd field | `2` |
| match last field | `-1` |
| match second last field | `-2` |
| match 3rd to 5th field | `3..5` |
| match 2nd to last field | `2..` |
| match 1st to 3rd last field | `..-3` |
| match all fields | `..` |

### display settings

#### height
| Description | Command |
|----|----|
| height by row or percentage | `--height=` |
| minimum height when `--height` is used with % | `--min-height=` |
  
#### margin
| Description | Command |
|----|----|
| margin by row or percentage | `--margin=` |
| padding by row or percentage | `--padding=` |

#### layout
| Description | Command |
|----|----|
| layout from bottom to top. prompt at the bottom | `--layout=default` |
| layout from top to bottom. prompt at the top | `--layout=reverse` |
| layout from top to bottom. prompt at the bottom | `--layout=reverse-list` |

#### border
| Description | Command |
|----|----|
| display boarder | `--border=<type>` |
| display border with label | `--border-label=<txt>` |
| display border with label at position | `--border-label-position` |

##### border types
| Description | Command |
|----|----|
| rounded corners | `rounded` |
| sharp corners | `sharp` |
| bold lines | `bold` |
| double lines | `double` |
| horizontal lines above and below | `horizontal` |
| vertical lines on the left and right | `vertical` |
| top border only | `top` |
| bottom bortder only | `bottom` |
| left obrder only | `left` |
| right border only | `right` |
| no border | `none` |
  

Top border and centered label \
`fzf --border=top --border-label="| My Cool Label |"` \

Bold border and label 5 columns from the left \
`fzf --border=bold --border-label="| My Cool Label |" --border-label-pos=5`\

Horizontal border and label 5 columns from the right \
`fzf --border=horizontal --border-label="| My Cool Label |" --border-label-pos=-5`

#### info lines
between entry and prompt
| Description | Command |
|----|----|
| just above prompt | `--info=default` |
| at the same level of prompt | `--info=inline` |
| no info line | `--info=hidden` |

Inline the info line with the prompt \
`fzf --info=inline`

Hide the info line \
`fzf --info=hidden`

#### prompt pointer and multimarker
| Description | Command |
|----|----|
| change the prompts character | `--prompt='<char>'` |
| change pointer character | `--pointer='<char>'` |
| change marker character | `--marker='<char>'` |
  
`fzf -m --prompt='▶' --pointer='→' --marker='♡'`  

#### header
appear near prompt
| Description | Command |
|----|----|
| header's content | `--header` |
| display <num> lines from input as header | `--header-lines=<num>` |
| display the header before the prompt | `--header-first` |

The header is above the prompt \
`fzf --header="Use CTRL-C to cancel" --header-first --reverse`

Display the first line of output from the command "lsblk" as header. \
It won't be possible to fuzzy search for this line anymore. \
`lsblk | fzf --header-lines=1`
  
#### colors
| Description | Command |
|----|----|
| processing of ansi color | `--ansi` |
| change color of TUI | `--color` |
| no color | `--no-color` |

##### base scheme
| Description | Command |
|----|----|
| dark scheme | `dark` |
| light scheme | `light` |
| 16 color | `16` |
| black and white | `bw` |

##### colors
| Description | Command |
|----|----|
| text of entries | `fg` |
| text of current line | `fg+` |
| bg color | `bg` |
| bg of current line | `bg+` |
| preview text | `preview-fg` |
| preview background | `preview-bg` |
| highlighted substring | `hl` |
| highlighted substring of current line | `hl+` |
| gutter on the left (get the value of bg+ if not specified) | `gutter` |
| query string | `query` |
| query string when search is disabled | `disabled` |
| info line | `info` |
| horizontal separator of the info line | `separator` |
| border aroudn the window (used by --border and --preview) | `border` |
| border's label (used by --border-label and --preview-label) | `label` |
| prompt | `prompt` |
| pointer | `pointer` |
| multiselect markers | `marker` |
| loading input indicator | `spinner` |
| header | `header` |

schema : `--color=[BASE_SCHEME][,COLOR_NAME[:ANSI_COLOR][:ANSI_ATTRIBUTES]]...`

Use ANSI color code (bright red) \
The first '^[' is an ESC character - you can spit it with 'CTRL-v ESC' \
`echo "^[[1;31mHello" | fzf --ansi`

The text of the current entry is red on a "dark" base scheme (ANSI 256 colors). \
`fzf --color='dark,fg+:red'`

The text of the current entry is red, and the other entries are blue (ANSI 256 colors). \
`fzf --color='fg+:red,fg:117'`

The text of the current line is red, and the other entries are blue (24 bits colors). \
`fzf --color='fg+:#ff0000,fg:#0000ff'`
  
```
fzf --color="bg+:-1,\
fg:gray,\
fg+:white,\
border:black,\
spinner:0,\
hl:yellow,\
header:blue,\
info:green,\
pointer:red,\
marker:blue,\
prompt:gray,\
hl+:red"
```
#### preview

| Description | Command |
|----|----|
| exec current command show in preview window | `--preview='<cmd> {}'` |
| preview window settings | `--preview-window=` |
| preview label | `--preview-label='<txt>'` |
| preview label position | `--preview-label-pos=` |

Display the stats of each directory using the CLI "stat" \
For example, if the current entry is "./home", the preview command will be "stat './home'" \
`find . -type d | fzf --preview='stat {}'`

Display the preview window with a label centered on top. \
`find . -type d | fzf --preview='stat {}' --preview-label='[ Directory stats ]'`

Display the preview window with a label at the bottom, 3 rows from the left. \
`find . -type d | fzf --preview='stat {}' --preview-label='[ Directory stats ]' --preview-label-pos='3:bottom'`

##### preview scrolling

| Description | Command |
|----|----|
| preview one line up | `<shift><up>` |
| preview one line down | `<shift><down>` |
  
##### preview placeholder
default placeholder is `{}` but it can display the second field of an entry `{2}`

| Description | Command |
|----|----|
| display the preview of all entries | `{+}` |
| keep the leading and trailing white space | `{s}` |
| replace the palceholder with the query string | `{q}` |
| replace the placeholder by the line number | `{n}` |
  
`find . -type d | nl | fzf --preview='stat {2}' --preview-label='[ Directory stats ]'`
`find . -type d | fzf --preview='echo "File(s) with index(es) {+n} and query {q} \n" && ls -l {-1}' --preview-label='[ Directory stats ]'`

##### preview window

| Description | Command |
|----|----|
| position of the window `left`,`right`,`top`, or `bottom`| `POSITION` |
| height of the window in rows or percentage | `SIZE`|
| add a border | `border-<BORDDER_OPT>` |
| wrap the lines | `wrap` or `nowrap` |
| automatically scroll to the bottom of the window | `follow` or `nofollow` |
| enable cycling (back to the top) | `cycle` or `nocycle` | `hidden` or `nohidden`
| hide the preview window. can only be shown wthen the binding `toggle-preview` action | 
`--preview-window=[POSITION][,SIZE[%]][,border-BORDER_OPT][,[no]wrap][,[no]follow][,[no]cycle][,[no]hidden][,+SCROLL[OFFSETS][/DENOM]][,~HEADER_LINES][,default]`  

#### binding keystroks or events to actions

| Description | Command |
|----|----|
| comma separated liset of keybindings | `--bind='<binding key>:<action>'`

`find . -type d | fzf --bind='ctrl-r:reload(find -type d)' --header='CTRL-r to refresh the list'`
`find . -type d | fzf --bind='ctrl-r:reload(find -type d)' --bind='del:execute(rm -ri {})' --bind='del:+reload(find -type d)' --header='CTRL-R to refresh the list | CTRL-P to toggle the preview | DEL to delete the current directory'`  

##### events
| Description | Command |
|----|----|
| triggered when fzf starts | `start`|
| triggered when the query is changed | `change` |
| triggered when query is empty and stil <bksp> | `backward-eof` |  

`FZF_DEFAULT_COMMAND="find . -type d" fzf --bind='change:reload(eval $FZF_DEFAULT_COMMAND)' --bind='del:execute(rm -ri {})' --bind='del:+reload(eval $FZF_DEFAULT_COMMAND)' --header='CTRL-R to refresh the list | CTRL-P to toggle the preview | DEL to delete the current directory'`

##### actions
You can use `{}` to signify current entry
| Description | Command |
|----|----|
| switch to alternate screen and execute command | `execute(<cmd>)` |
| execute a command without leaving fzf | `execute-silent(<cmd>)` |
| specify additional preview command | `preview(<cmd>)` |
| refresh the preview | `change-preview` |
| change the value of --preview-window. use the delimiter | to create (and cycle through) different groups of options| `change-preview-window(<cmd1>|<cmd2>)`|
| chagen the prompt to the given characters | `change-prompt(<cmd>)`|
| reload the list of entries with the given command | `reload(<cmd>)` |
| select all matches | `select-all`|
| clear selection | `deselect-all`|
|toggle all matches | `toggle-all`|
| toggle the sorting | `toggle-sort`|
| replace the query with the current selection | `replace_query`|
| delete the query | `clear-query` |
| unbind a binding keystroke | `unbind(<bind>)`|
| rebind a keystroke after unbinding it | `rebind(<bind>)`|
| close fzf | `abort`|

Close fzf with CTRL-D \
`fzf --bind='ctrl-d:abort'`

Display the preview with CTRL-P \
`fzf --preview-window=hidden --bind='ctrl-p:preview(stat {})'`

Change the preview with CTRL-P \
`fzf --preview='file {}' --bind='ctrl-p:change-preview(stat {})'`

Change the position and size of the preview window with CTRL-P \
`fzf --preview='file {}' --bind='ctrl-p:change-preview-window(20%,top|50%,right)'`

Change the prompt with CTRL-P \
`fzf --preview='file {}' --bind='ctrl-p:change-prompt(→ )'`

Delete the file or directory with DEL \
`fzf --preview='file {}' --bind='del:execute(rm -ri {})'`

Reload the list of files\
`find . -type f | fzf --bind='ctrl-r:reload(find . -type f)'`

Bind CTRL-A to select all entries \
Unbind CTRL-A and rebind it with, respectively, CTRL-U and CTRL-R \
`find . -type f | fzf --multi --bind='ctrl-a:select-all' --bind='ctrl-u:unbind(ctrl-a)' --bind='ctrl-r:rebind(ctrl-a)'`
  

### bindings
  
| Description | Command |
|----|----|
| map `\r` to `:Rg` |`nnoremap <Leader>r :Rg`|
| map `\a` to `:Ag` | `nnoremap <Leader>a :Ag`|
| map `\f` to `:Files` |`nnoremap <Leader>f :Files`|

## combining into bashrc

adjust for `fd`/`find` usage accordingly
  
replace `tree -C` with `lsd --tree` accordingly
```
# fzf 
# fzf ctrl-r and alt-c behavior
export FZF_DEFAULT_COMMAND='fd --hidden --exclude ".git"' #requires fd to be installed
#export FZF_DEFAULT_COMMAND='rg --files --hidden --glob "!.git"'
#export FZF_DEFAULT_COMMAND='find -L ! -path "*git*"'
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
export FZF_ALT_C_COMMAND="$FZF_DEFAULT_COMMAND --type d"
#export FZF_ALT_C_COMMAND="$FZF_DEFAULT_COMMAND -type d"
export FZF_DEFAULT_OPTS="
--layout=reverse
--info=inline
--height=80%
--multi
--preview-window=:hidden
--preview '([[ -f {} ]] && (bat --style=numbers --color=always {} || cat {})) || ([[ -d {} ]] && (lsd --tree {} | less)) || echo {} 2> /dev/null | head -200'
--color='hl:148,hl+:154,pointer:032,marker:010,bg+:237,gutter:008'
--prompt='∼ ' --pointer='▶' --marker='✓'
--bind '?:toggle-preview'
--bind 'ctrl-a:select-all'
--bind 'ctrl-y:execute-silent(echo {+} | pbcopy)'
--bind 'ctrl-e:execute(echo {+} | xargs -o vim)'
--bind 'ctrl-v:execute(code {+})'"
```

or
  
```
fzf --multi \
--height=50% \
--margin=5%,2%,2%,5% \
--layout=reverse-list \
--border=double \
--info=inline \
--prompt='$>' \
--pointer='→' \
--marker='♡' \
--header='CTRL-c or ESC to quit' \
--color='dark,fg:magenta'
```

## combining for clink
the following do not persist, set in local user's env var (or via setx) for persistence 
```
set FZF_CTRL_T_OPTS=--layout=reverse --info=inline --height=80% --multi --preview-window=:hidden --preview "cat {} | head -200" --color="hl:148,hl+:154,pointer:032,marker:010,bg+:237,gutter:008" --prompt="∼ " --pointer="▶" --marker="✓" --bind "?:toggle-preview" --bind "ctrl-a:select-all" --bind "ctrl-y:execute-silent(echo {+} | pbcopy)" --bind "ctrl-e:execute(echo {+} | xargs -o vim)" --bind "ctrl-v:execute(code {+})"
set FZF_CTRL_R_OPTS=--layout=reverse --info=inline --height=80% --multi --preview-window=:hidden --preview "echo {} | head -200" --color="hl:148,hl+:154,pointer:032,marker:010,bg+:237,gutter:008" --prompt="∼ " --pointer="▶" --marker="✓" --bind "?:toggle-preview" --bind "ctrl-a:select-all" --bind "ctrl-y:execute-silent(echo {+} | pbcopy)" --bind "ctrl-e:execute(echo {+} | xargs -o vim)" --bind "ctrl-v:execute(code {+})"
set FZF_ALT_C_OPTS=--layout=reverse --info=inline --height=80% --multi --preview-window=:hidden --preview "lsd --tree {} | head -200" --color="hl:148,hl+:154,pointer:032,marker:010,bg+:237,gutter:008" --prompt="∼ " --pointer="▶" --marker="✓" --bind "?:toggle-preview" --bind "ctrl-a:select-all" --bind "ctrl-y:execute-silent(echo {+} | pbcopy)" --bind "ctrl-e:execute(echo {+} | xargs -o vim)" --bind "ctrl-v:execute(code {+})"
set FZF_BINDINGS_OPTS=--layout=reverse --info=inline --height=80% --multi --preview-window=:hidden --preview "cat {} | head -200" --color="hl:148,hl+:154,pointer:032,marker:010,bg+:237,gutter:008" --prompt="∼ " --pointer="▶" --marker="✓" --bind "?:toggle-preview" --bind "ctrl-a:select-all" --bind "ctrl-y:execute-silent(echo {+} | pbcopy)" --bind "ctrl-e:execute(echo {+} | xargs -o vim)" --bind "ctrl-v:execute(code {+})"
set FZF_COMPLETE_OPTS=--layout=reverse --info=inline --height=80% --multi --preview-window=:hidden --preview "cat {} | head -200" --color="hl:148,hl+:154,pointer:032,marker:010,bg+:237,gutter:008" --prompt="∼ " --pointer="▶" --marker="✓" --bind "?:toggle-preview" --bind "ctrl-a:select-all" --bind "ctrl-y:execute-silent(echo {+} | pbcopy)" --bind "ctrl-e:execute(echo {+} | xargs -o vim)" --bind "ctrl-v:execute(code {+})"
set FZF_CTRL_T_COMMAND=fd --hidden --exclude ".git"
set FZF_ALT_C_COMMAND=fd --hidden --type d 
```

