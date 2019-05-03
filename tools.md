### doxygen
generate documents from source code

### cscope and ctags
[Tag Jumping in a Codebase Using ctags and cscope in Vim](https://www.embeddedarm.com/blog/tag-jumping-in-a-codebase-using-ctags-and-cscope-in-vim/)
```bash
ctags
ctags -R
Once the index is built, open Vim, find a function call or variable name, hover over it, and hit Ctrl+] . 
Simply select the number you wish to explore more about and it’ll take you there. 
Hit Ctrl+t  to jump back.
While still in insert mode, hit Ctrl+x Ctrl+] . You should get a list like shown in the screenshot below.

cscope -R
To include symlinks
find `pwd` -name "*.[ch]" -o -name "*.cpp" -o -name "*.hxx" -exec realpath {} \; > cscope.files
In the directory with 'cscope.files'
cscope -b -q -k
```
