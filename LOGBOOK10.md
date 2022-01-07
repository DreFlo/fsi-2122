# Task 1
    Since there are no security measures related to user input, anything that a user inputs will be treated as raw inner HTML code. So placing
```html
     <script>alert(’XSS’);</script>
```
 will create an alert for whoever views the page.
