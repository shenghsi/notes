### Vim notes
``` vim
" Search down into subfolders
" Provides tab-completion for all file-related tasks
set path+=**

" Display all matching files when we tab complete
set wildmenu

" NOW WE CAN:
" - Hit tab to :find by partial match
" - Use * to make it fuzzy
```

### vim examples in normal mode
```
.       # repeat last command
diw     # delete in word
caw     # change all word
yi)     # yank all inside parentheses
dt)     # delete until )
df)     # delete until ), including )
va"     # visual select all inside " including "
:earlier 2m     # goto 2min ago

m{a-zA-Z}       # set mark at cursor position, use `{maker} to go to this mark

```

### Macros
```
Recode a macro
q{register}
(do something)
q

Play a macro
@{register}

Aplly macro in visual mode
:normal @{register}
```
