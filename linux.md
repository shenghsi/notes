#### Shell
execute multiple commands in one line  
```bash
A; B    # Run A and then B, regardless of success of A
A && B  # Run B if and only if A succeeded
A || B  # Run B if and only if A failed
A &     # Run A in background.
```

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

--            # double dash "--" means "end of command line flags" i.e. it tells the preceding command not to try to parse what comes after command line options.
```
##### csh
```
!! Repeats the previous command
!10 Repeat the 10th command from the history
!-2 Repeat the 2nd command (from the last) from the history
!string Repeat the command that starts with “string” from the history
!?string Repeat the command that contains the word “string” from the history
^str1^str2^ Substitute str1 in the previous command with str2 and execute it
!!:$ Gets the last argument from the previous command.
!string:n Gets the nth argument from the command that starts with “string” from the history.

!^ first argument of the previous command

!$ last argument of the previous command
!\* all arguments of the previous command
!:2 second argument of the previous command
!:2-3 second to third arguments of the previous command
!:2-$ second to last arguments of the previous command
!:2\* second to last arguments of the previous command
!:2- second to next to last arguments of the previous command
!:0 the command itself
```

#### Symbolic link
ln -s source_file myfile    #Replace source_file with the name of the existing file for which you want to create the symbolic link (this file can be any existing file or directory across the file systems). Replace myfile with the name of the symbolic link.

#### SSH
ssh using public and private keys
<https://missing.csail.mit.edu/2020/command-line/>
```bash
ssh-add -l lists all currently held keys
ssh-add -D forces ssh-agent to forget all currently held keys
ssh-add ~/.ssh/newkey_rsa adds the private key ~/.ssh/newkey_rsa to ssh-agent.
ssh-add -t 3600 ~/.ssh/newkey_rsa adds a new private key with an expiry time, so ssh-agent will only remember newkey_rsa for (say) 3600 seconds.

show ciphers
ssh -Q cipher localhost | paste -d , -s -
ssh -YC -c aes128-gcm@openssh.com shxi@slc11cbg
```

#### Network
```bash
dig             #DNS lookup. dig (domain information groper) is a flexible tool for interrogating DNS name servers. It performs DNS lookups and displays the answers that are returned from the name server(s) that were queried.

netstat         #show network status. The netstat command symbolically displays the contents of various network-related data structures.
```
#### VNC
```
Problem: unable to copy to vnc server
Solution: kill the klipper process. May need run vncconfig&

uncheck pass special keys directly to VNC server to use CMD+Tab to switch between local windows
```

#### Meta key
<https://www.emacswiki.org/emacs/MetaKeyProblems>

Esc = Meta on Mac
