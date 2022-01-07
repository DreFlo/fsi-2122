# Task 1
Since there are no security measures related to user input, anything that a user inputs will be treated as raw inner HTML code. So placing
```html
     <script>alert(’XSS’);</script>
```
 will create an alert for whoever views the page.
#Task 2
Through the same process we are able to discover the cookie of the user viewing the webpage.
