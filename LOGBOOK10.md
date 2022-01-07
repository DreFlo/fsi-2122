# Task 1
Since there are no security measures related to user input, anything that a user inputs will be treated as raw inner HTML code. So placing
```html
     <script>alert('XSS');</script>
```
 will create an alert for whoever views the page.
# Task 2
Through the same process we are able to discover the cookie of the user viewing the webpage.
# Task 3
By sending a GET request to our own machine with the cookie in the URL and listening for it we were able to steal the user's information.
# Task 4
We used HTTP Header Live to see how a friend request was being sent. After that we realized we had to create a valid request to send to the server in order to add anyone who view Samy's profile as a friend. The request in the URL was formatted like **"http://www.seed-server.com/action/friends/add?friend=" + [ID of user to add as friend] + "&__elgg_ts=" + elgg.security.token.__elgg_ts + "&__elgg_token=" + elgg.security.token.__elgg_token + "&__elgg_ts=" + elgg.security.token.__elgg_ts + "&__elgg_token=" + elgg.security.token.__elgg_token** so we placed that in the _sendurl_ variable in the script provided to us. 
Lines 1 and 2 were necessary to retrieve the ts and token of the user viewing Samy's profile so the request would be valid, if Text mode was not available the attack would not be possible because there would be extra security measures in place that would prevent the input text from being treated as raw HTML code like substituting '<' for '&lt[no space];' and injecting tags like the paragraph tag and others in the middle of the text. 
