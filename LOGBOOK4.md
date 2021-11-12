
Task 1: We tried the commands given to explore how we can see environmental variables.

Task 2: 
    Step 1: The program printed the environmental variables of the child process.
    Step 2: We changes it, and now it printed the environmental variables of the parent process.
    Step 3: By studying the manual for the fork function, we realized that it creates an exact copy of the parent process, including the environmental variables, so after comparing the two outputs, just as expected, the environmental variables were the same, having been inherited by the child process.

Task 3:
    Step 1: After running, we concluded that there were no environmental variables to print.
    Step 2: By changing one of the parameters of the execve() function, there now were environmental variables to print.
    Step 3: The third argument of the execve() function asks for an array of strings which contains the environmental variables and, thus, it needs to be specificed in order for a process to inherit the environmental variables via that function.

Task 4: After running the file, we concluded that, even though there were a few changes in values of a few of the environmental variables that were most likely due to other circumstances, by using system() the new program inherits the environmental variables.

Task 5: We used export to set the three different environmental variables, however after running the Set-UID program, we found that the PATH variable and the new variable we created had remained with their values, but the LD_LIBRARY_PATH was nonexistant in the child  process. We, honestly, don't know why that happened.

Task 6: Yes, we were able to run our malicious code by creating another ls and placing it on the /home/seed path. Since we had changed its owner to root, using the chown command, we can conclude that it was running with root privileges.
