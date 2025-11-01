Student: Minh-Huy Mai Duc
StudentID: 23122008
Institution: VNUHCM University of Science

To add a new syscall to the current xv6 setup; you need to modify at least these files:

Kernel space:
+-- [syscall.h](kernel/syscall.h): define a new system call number (usually increased by 1 from the last one).
|
+-- [syscall.c](kernel/syscall.c): define the prototype for the function that handles the system call and map the 
previous defined system call number to that function. 
|
+-- [sysproc.c](kernel/sysproc.c): implement for the system call function. 
|
+-- dependencies files

User space:
+-- [user.h](user/user.h): define the function that the user can use to invoke the new implemented system call. 
|
+-- [usys.pl](user/usys.pl): add an interface for the user function to access the system call. (e.g entry('newfunc'))
|
+-- mainprogram.c - e.g: [helloworld.c](user/testhello.c) or [trace.c](user/trace.c): typically handle logic at input level, invoking the function implemented from [...]
|
+-- dependencies files