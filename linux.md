#### Shell
```bash
du -sh */     # Show directory sizes

!!            # Execute last command
!co           # Execute last command begin with co

reset         #Truely clear terminal. In contrast to clear, or Ctrl+L, reset will actually completely re-initialise the terminal, instead of just clearing the screen. However, it won't re-instantiate the shell (bash). That means that bash's state is the same as before, just as if you were merely clearing the screen.
tput reset    #should do the same thing more quickly.

Single quote vs double quote
The single quotes will literally echo what you have between them, while the double quotes will evaluate variables between them and output the value of the variable. For example, this
#!/bin/sh
MYVAR=sometext
echo "double quotes gives you $MYVAR"
echo 'single quotes gives you $MYVAR'
will give this:
double quotes gives you sometext
single quotes gives you $MYVAR
But in alias:
Single quotes are evaluated dynamically:
alias QS='echo $PWD'
Double quotes are evaluated at time of creation and, thereafter, never changes:
alias QD="echo $PWD"

```
#### Network
```bash
dig             #DNS lookup. dig (domain information groper) is a flexible tool for interrogating DNS name servers. It performs DNS lookups and displays the answers that are returned from the name server(s) that were queried.

netstat         #show network status. The netstat command symbolically displays the contents of various network-related data structures.
```
