# Challenge 1

With checksev's use we verified that PIE isn't used, which allowed us to discover the memory position of where the flag's address is stored which won't be random across different executions.

The vulnerability is found at line 25, with scanf(), which will allow us to take advantage of printf(), letting us access arbitrary memory positions and their content.

By using %s in printf(), we were able to see the inserted memory value, found with gdb, with the flag pointer.
flag{35d8b9e61a93c6ee97ef0e0a8db5864c}.

# Challenge 2

The vulnerability is found in line 12, with scanf(), allowing us to take advantage of printf(), in which we were able to interpret a value as a memory position and write something in it, using %n.

The flag is stored in stored in the file flag.txt, not loaded into memory, being accessed by using the system command giving us access to the bash.

In order to use this, we had to change a certain memory position, found with gdb, to a specific value in order to enter the if statement, after which we simply used 'cat flag.txt' to get the value from the file.
flag{c12871068a2ef0874cc72d0e9eff2499}
