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

### normal mode vim examples
```
.       # repeat last command
`.      # jump to last change
``      # bring you back to where the cursor was before you made your last jump
`^      # jump to the position where the cursor was the last time when insert mode was stopped
diw     # delete in word
caw     # change all word
yi)     # yank all inside parentheses
dt)     # delete until )
df)     # delete until ), including )
(       # [count] sentences backward.  exclusive motion. eg: 2(, (
)       # [count] sentences forward.  exclusive motion.
{       # [count] paragraphs backward.  exclusive motion.
}       # [count] paragraphs forward.  exclusive motion.
]]      # [count] sections forward or to the next '{' in the first column.  When used after an operator, then also stops below a '}' in the first column.  exclusive Note that exclusive-linewise often applies.
][      # [count] sections forward or to the next '}' in the first column.  exclusive Note that exclusive-linewise often applies.
[[      # [count] sections backward or to the previous '{' in the first column.  exclusive Note that exclusive-linewise often applies.
[]      # [count] sections backward or to the previous '}' in the first column.  exclusive Note that exclusive-linewise often applies.

:earlier 2m     # goto 2min ago

m{a-zA-Z}       # set mark at cursor position, use `{maker} to go to this mark

```

### visual mode examples
``` vim
va"     # visual select all inside " including "
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
