# Challenge 1

We analysed the code in *main.c* and found the program would try to open a file with the path stored in *meme_file*. To change the file that is opened we would have to change the value in *mem_file*. To do this we made use of a buffer overflow attack since up to 28 bytes were being read from the *stdin* into a buffer with only 20 bytes. We used the string "12345678901234567890flag.txt\0" to change the value in *meme_file* thus unlocking the flag (flag{722c674469e8b50fafa091337613b41e}).

# Challenge 2

The changes made consist of adding a new 4 byte array whose value will be interpreted as a *long* and compared to another hard-coded value. If these two are equal, then the program will open the file with the path specified in *meme_file*. We made use of the same buffer overflow vulnerability to change both the value of the *val* and *meme_file* arrays. To input the correct value in *val* we used the \x escape sequence in python to input the value of the bytes from the least significant to the most. The string used in the attack was "12345678901234567890\x22\x21\xfc\xfeflag.txt\0". We unlocked the flag (flag{80bd47c0622cd99def4f744866ad32b7}). 
