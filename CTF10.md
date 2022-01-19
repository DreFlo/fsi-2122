# Challenge 1

We realized the input was vulnerable to the insertion of HTML code. Upon reading the challenge in Moodle we realized the administrator was clicking in the input with id "markAsRead", as we could not change where de admin clicked we had to change the URL the post request was being sent to. This would "fool" the admin into thinking they had denied us. The post would have to be sent to the same url as the current page (as shown in the  form with the Give Flag button), to achive this we just had to set the action attribute of the form tag to "".

To change the value of the action attribute in the form we used the following code: 

```html
<script>document.getElementsByTagName("form")[1].action = "";</script>
```
