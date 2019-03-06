***Truely clear terminal***
reset
In contrast to clear, or Ctrl+L, reset will actually completely re-initialise the terminal, instead of just clearing the screen. However, it won't re-instantiate the shell (bash). That means that bash's state is the same as before, just as if you were merely clearing the screen.
tput reset
should do the same thing more quickly

**Show directory sizes**
du -sh */

### Network
**DNS lookup**
dig
