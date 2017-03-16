### Progress
- [ ] Make changes to implement cout for klee
- [ ] Find all function prototypes that need to be hidden in uclibc++. Do this by comparing klee-uclibc with uclibc.
- [ ] Change libc to klee-uclibc in Uclibc++. Debug with this. {__Still Working on this__ (_Issue_: Not linking to libc library)}.
- [x] Debugging libc using BuildRoot installation
- [x] Making Uclibc++ work (fix the library issue)
- [x] Track changes between commonly named files in UClibc++ and klee-uclibc (such as 'write')
- [x] Do simple C++ programs without stdin or stdout work out-of-the-box with KLEE? Try get-sign. 
- [x] Figuring out the stage at which cout makes the call to C functions (and which C function)
- [x] Figuring out the call heirarchy for cout by debugging uClibc++ (__Log Generated__)
- [x] Figuring out changes between uclibc and klee-uclibc for puts()



###Current Task
- [ ] Change libc to klee-uclibc in Uclibc++. Debug with this. (__Library is linking but there are some other errors. We are using a simple program with puts__)

_Command_:
```
gcc -g -static -nostdinc -nodefaultlibs -nostdlib -I/usr/x86_64-linux-uclibc/usr/include -L/usr/x86_64-linux-uclibc/usr/lib test.c -Xlinker --verbose -lc
```

_Output_:
```
/usr/bin/ld: warning: cannot find entry symbol _start; defaulting to 0000000000400144
/usr/x86_64-linux-uclibc/usr/lib/libc.a(tcgetattr.os): In function `tcgetattr':
/home/nasir/debug/klee-uclibc/libc/termios/tcgetattr.c:43: undefined reference to `ioctl'
/usr/x86_64-linux-uclibc/usr/lib/libc.a(_WRITE.os): In function `__stdio_WRITE':
/home/nasir/debug/klee-uclibc/libc/stdio/_WRITE.c:52: undefined reference to `write'
/usr/x86_64-linux-uclibc/usr/lib/libc.a(_cs_funcs.os): In function `__stdio_seek':
/home/nasir/debug/klee-uclibc/libc/stdio/_cs_funcs.c:66: undefined reference to `lseek64'
collect2: error: ld returned 1 exit status
```
