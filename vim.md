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

[m      # cursor N times back to start of member function
]]      # [count] sections forward or to the next '{' in the first column.  When used after an operator, then also stops below a '}' in the first column.  exclusive Note that exclusive-linewise often applies.
][      # [count] sections forward or to the next '}' in the first column.  exclusive Note that exclusive-linewise often applies.
[[      # [count] sections backward or to the previous '{' in the first column.  exclusive Note that exclusive-linewise often applies.
[]      # [count] sections backward or to the previous '}' in the first column.  exclusive Note that exclusive-linewise often applies.
[(      # go to [count] previous unmatched '('. exclusive motion. {not in Vi} 
[{      # go to [count] previous unmatched '{'. exclusive motion. {not in Vi} 
])      # go to [count] next unmatched ')'. exclusive motion. {not in Vi} 
]}      # go to [count] next unmatched '}'. exclusive motion. {not in Vi} 

:earlier 2m     # goto 2min ago

m{a-zA-Z}       # set mark at cursor position, use `{maker} to go to this mark
ma	            # set mark a at current cursor location
'a              # jump to line of mark a (first non-blank character in line)
`a	            # jump to position (line and column) of mark a
d'a	            # delete from current line to line of mark a
d`a	            # delete from current cursor position to position of mark a
c'a	            # change text from current line to line of mark a
y`a	            # yank text to unnamed buffer from cursor to position of mark a
:marks	        # list all the current marks
:marks aB	      # list marks a, B
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

### When searching:
```
., *, \, [, ^, and $ are metacharacters.
+, ?, |, &, {, (, and ) must be escaped to use their special function.
\/ is / (use backslash + forward slash to search for forward slash)
\t is tab, \s is whitespace (space or tab)
\n is newline, \r is CR (carriage return = Ctrl-M = ^M)
After an opening [, everything until the next closing ] specifies a /collection. Character ranges can be represented with a -; for example a letter a, b, c, or the number 1 can be matched with [1a-c]. Negate the collection with [^ instead of [; for example [^1a-c] matches any character except a, b, c, or 1.
\{#\} is used for repetition. /foo.\{2\} will match foo and the two following characters. The \ is not required on the closing } so /foo.\{2} will do the same thing.
\(foo\) makes a backreference to foo. Parenthesis without escapes are literally matched. Here the \ is required for the closing \).
```

### When replacing:
```
\r is newline, \n is a null byte (0x00).
\& is ampersand (& is the text that matches the search pattern).
\0 inserts the text matched by the entire pattern
\1 inserts the text of the first backreference. \2 inserts the second backreference, and so on.
```
