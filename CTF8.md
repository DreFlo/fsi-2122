# Challenge 1

From the end-user's perspective, we can only login or logout. To bypass the login, we can use sql injection, to which the code is vulnerable to since it doesn't treat the user inputs and creates sql queries dynamically as strings. The vulnerability is present in line 40, where the sql query is created:
```php
$query = "SELECT username FROM user WHERE username = '".$username."' AND password = '".$password."'";
```

To explore it, we supplied the name 'admin' through input, with the addition of the necessary characters to end the string and the character ';' to end the query, followed by an '#' to comment the rest of the code, thus creating the following query:
$query = "SELECT username FROM user WHERE username = '".$username."' AND password = '".$password."'";
```php
$query = "SELECT username FROM user WHERE username = 'admin';#' AND password = '".$password."'";
```

# Challenge 2

An unauthenticated user can login, check their internet speed, or ping a host of their choice.
Using the feedback we got from trying the features available, we realized that the ping functionality is implemented through the use of the PHP:exec() function and the 'ping' program.
By using this function, there's a possbility for us to manipulate the arguments received in order to do what we require, including the use of other programs such as 'cat'.
Thus, we explore this vulnerability by using '||' in order to be able to call another program when the first, 'ping', returned an error, which we could be assured by passing either no arguments or invalid ones, and using the 'cat' program in the right side to open the required file, 'flag.txt'.
```
|| cat /flag.txt
```
