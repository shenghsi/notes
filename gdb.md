


gdb ./executable core.123

To get the stack trace of all the threads
```
thread apply all bt
```

### ELF files (Library files, Core files, ...)
readelf -s lib64/libgcc_s.so.1 | grep Unwind_Backtrace
