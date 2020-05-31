### fzf
C-r (search command history)
C-t (search file)
cd \*\*\<tab\> (find dir to cd)

### doxygen
generate documents from source code

###  and ctags
[Tag Jumping in a Codebase Using ctags and cscope in Vim](https://www.embeddedarm.com/blog/tag-jumping-in-a-codebase-using-ctags-and-cscope-in-vim/)
```bash
ctags
ctags -R
Include another ctags file generated separately in another path
:set tags+=/path/to/other/dir/tags

Once the index is built, open Vim, find a function call or variable name, hover over it, and hit Ctrl+] . 
Simply select the number you wish to explore more about and it’ll take you there. 
Hit Ctrl+t  to jump back.

Auto-complete:
While still in insert mode, hit 
Ctrl+x Ctrl+]   # You should get a list like shown in the screenshot below.
```
### cscope
```
cscope -R
To include symlinks
find `pwd` -name "*.[ch]" -o -name "*.cpp" -o -name "*.hxx" -exec realpath {} \; > cscope.files
In the directory with 'cscope.files'
cscope -b -q -k

error:
cs_read_prompt EOF: No such file or directory
E609: Cscope error: cscope: invlib.c:570: invopen: Assertion `invcntl-aram.sizeblk == sizeof(t_logicalblk)' failed.

solution:

Use the correct version 32 bit vs 64 bit
file /usr/bin/cscope
/usr/bin/cscope: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.6.32, BuildID[sha1]=401ebb04096233e591deed0162255b9b50efb017, stripped

file /usr/local/packages/cscope/bin/cscope
/usr/local/packages/cscope/bin/cscope: ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.2.5, not stripped

```
