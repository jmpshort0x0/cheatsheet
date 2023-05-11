# Usage Examples
prereq: `fd` (fd-find) and `ag` (The Silver Searcher) and `rg` (ripgrep)

## flags

| Description | Command |
|----|----|
| exact matches | `-e` or `--exact` |
| multi line matches | `-m` or `--multi`|
| case insensitive | `-i`|
| case sensitive | `+i` |
| toggle section and move up | `<TAB>`|
| toggle selection and move down | `<SHIFT><TAB>`|

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
sets the default searching parameters when using `fzf` when there is **no additional input**
`export FZF_DEFAULT_COMMAND='find -L . -type f ! -path "*git*"'` or
`export FZF_DEFAULT_COMMAND='fd . --hidden --exclude ".git"'` or
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



### bindings
  
| Description | Command |
|----|----|
| map `\r` to `:Rg` |`nnoremap <Leader>r :Rg`|
| map `\a` to `:Ag` | `nnoremap <Leader>a :Ag`|
| map `\f` to `:Files` |`nnoremap <Leader>f :Files`|



## combining into bashrc
```
# fzf 
# fzf ctrl-r and alt-c behavior
export FZF_DEFAULT_COMMAND='fd --hidden --exclude ".git"' #requires fd to be installed
#export FZF_DEFAULT_COMMAND='rg --files --hidden --glob "!.git"'
#export FZF_DEFAULT_COMMAND='find . -type f ! -path "*git*"'
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
export FZF_ALT_C_COMMAND="$FZF_DEFAULT_COMMAND --type d"
export FZF_DEFAULT_OPTS="
--layout=reverse
--info=inline
--height=80%
--multi
--preview-window=:hidden
--preview '([[ -f {} ]] && (bat --style=numbers --color=always {} || cat {})) || ([[ -d {} ]] && (tree -C {} | less)) || echo {} 2> /dev/null | head -200'
--color='hl:148,hl+:154,pointer:032,marker:010,bg+:237,gutter:008'
--prompt='∼ ' --pointer='▶' --marker='✓'
--bind '?:toggle-preview'
--bind 'ctrl-a:select-all'
--bind 'ctrl-y:execute-silent(echo {+} | pbcopy)'
--bind 'ctrl-e:execute(echo {+} | xargs -o vim)'
--bind 'ctrl-v:execute(code {+})'
```

