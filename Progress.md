### Progress
- [ ] Make changes to implement cout for klee
- [ ] Find all function prototypes that need to be hidden in uclibc++. Do this by comparing klee-uclibc with uclibc.
- [ ] Change libc to klee-uclibc in Uclibc++. Debug with this. (__Not working__ : Even gcc++ has also stopped working)
- [x] Track changes between commonly named files in UClibc++ and klee-uclibc (such as 'write')
- [x] Do simple C++ programs without stdin or stdout work out-of-the-box with KLEE? Try get-sign. 
- [x] Figuring out the stage at which cout makes the call to C functions (and which C function)
- [x] Figuring out the call heirarchy for cout by debugging uClibc++ (__Log Generated__)
- [x] Figuring out changes between uclibc and klee-uclibc for puts()
