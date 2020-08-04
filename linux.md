### Shell
#### Prompts
csh/zsh: <http://www.nparikh.org/unix/prompt.php>

#### execute multiple commands in one line  
```bash
A; B    # Run A and then B, regardless of success of A
A && B  # Run B if and only if A succeeded
A || B  # Run B if and only if A failed
A &     # Run A in background.
```
#### some commands
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
#### csh
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

### Symbolic link
ln -s source_file myfile    #Replace source_file with the name of the existing file for which you want to create the symbolic link (this file can be any existing file or directory across the file systems). Replace myfile with the name of the symbolic link.

### SSH
ssh using public and private keys <https://missing.csail.mit.edu/2020/command-line/>  
To generate a pair you can run ssh-keygen
```
ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519
```   
ssh will look into .ssh/authorized_keys to determine which clients it should let in. To copy a public key over you can use:
```
cat .ssh/id_ed25519.pub | ssh foobar@remote 'cat >> ~/.ssh/authorized_keys'
```
A simpler solution can be achieved with ssh-copy-id where available:
```
ssh-copy-id -i .ssh/id_ed25519.pub foobar@remote
```
lists all currently held keys
```
ssh-add -l 
```
forces ssh-agent to forget all currently held keys
```
ssh-add -D 
```  
adds the private key ~/.ssh/newkey_rsa to ssh-agent.
```
ssh-add ~/.ssh/newkey_rsa 
```
adds a new private key with an expiry time, so ssh-agent will only remember newkey_rsa for (say) 3600 seconds.
```
ssh-add -t 3600 ~/.ssh/newkey_rsa 
```
show ciphers, connect using ciphers
```
ssh -Q cipher localhost | paste -d , -s -
ssh -YC -c aes128-gcm@openssh.com shxi@slc11cbg
```

### Network
```bash
dig             #DNS lookup. dig (domain information groper) is a flexible tool for interrogating DNS name servers. It performs DNS lookups and displays the answers that are returned from the name server(s) that were queried.

netstat         #show network status. The netstat command symbolically displays the contents of various network-related data structures.
```
### VNC
```
Problem: unable to copy to vnc server
Solution:
kill the klipper process. May need run vncconfig&
enable copy and paste to and from local machine by add to .profile
vncconfig -nowin&

uncheck pass special keys directly to VNC server to use CMD+Tab to switch between local windows
```

### Meta key
<https://www.emacswiki.org/emacs/MetaKeyProblems>

Esc = Meta on Mac


### Database
connect to database
```
mysql -u root -p
```
back up
```
mysqldump -u root -p --all-databases > stock.sql
```
permissions
```
show grants;
show grants for 'test'@'localhost';
grant select, create, insert on stock.test to 'test'@'localhost';
revoke drop on stock.test from 'test'@'localhost';
```

### Mac launchctl
```
launchctl load ~/Library/LaunchAgents/com.devdaily.scripts.plist
launchctl unload ~/Library/LaunchAgents/com.devdaily.scripts.plist
```
To start right away for debug
```
launchctl start ~/Library/LaunchAgents/com.devdaily.scripts.plist
launchctl stop ~/Library/LaunchAgents/com.devdaily.scripts.plist
```
You typically want to use launchctl load -w and launchctl unload -w.
start and stop are usually reserved for testing or debugging a job.

launchctl start <label>: Starts the job. This is usually reserved just for testing or debugging a particular job.
launchctl stop <label>: Stops the job. Opposite of start, and it's possible that the job will immediately restart if the job is configured to stay running.

launchctl remove <label>: Removes the job from launchd, but asynchronously. It will not wait for the job to actually stop before returning, so no error handling on this one.

launchctl load <path>: Loads and starts the job as long as the job is not "disabled."
launchctl unload <path>: Stops and unloads the job. The job will still restart on the next login/reboot.

launchctl load -w <path>: Loads and starts the job while also marking the job as "not disabled." The job will restart on the next login/reboot.
launchctl unload -w <path>: Stops and unloads and disables the job. The job will NOT restart on the next login/restart.



