


gdb ./executable core.123

To get the stack trace of all the threads
```
thread apply all bt

gdb /u01/crshome/0929/bin/orarootagent.bin core.16949 -ex 'thread apply all bt' -ex quit > test.txt
```

### ELF files (Library files, Core files, ...)
readelf -s lib64/libgcc_s.so.1 | grep Unwind_Backtrace
