#### Terminal
```bash
reset         #Truely clear terminal
In contrast to clear, or Ctrl+L, reset will actually completely re-initialise the terminal, instead of just clearing the screen. However, it won't re-instantiate the shell (bash). That means that bash's state is the same as before, just as if you were merely clearing the screen.
tput reset    #should do the same thing more quickly
```
#### Shell
```bash
du -sh */     #Show directory sizes
```
#### Network
```bash
dig             #DNS lookup
dig (domain information groper) is a flexible tool for interrogating DNS name servers. It performs DNS lookups and displays the answers that are returned from the name server(s) that were queried.

netstat         #show network status
The netstat command symbolically displays the contents of various network-related data structures.
```
