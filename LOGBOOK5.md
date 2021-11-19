# TASK 1: Getting Familiar with Shellcod

We realised we had to inject the shellcode somewhere in the program and force it to run.

# TASK 2: Understanding the Vulnerable Program

We found a vulnerability in the program in the _strcpy_ function because the buffer string array have different sizes which means we could write to unallocated memory changing the return pointer.

# TASK 3: Launching Attack on 32-bit Program

We discovered the memory position of the base pointer and buffer start and calculated the return pointer memory address. We change the return pointer to the buffer pointer where we had injented the shellcode thus forcing it to run.


