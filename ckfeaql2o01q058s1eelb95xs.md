## FYP-DevLog 008


[![Thumbnail](https://img.youtube.com/vi/w8mok_2O_40/hqdefault.jpg)](https://youtu.be/w8mok_2O_40)

Today I completed the forgot password reset flow. I also recorded a video for demonstration purposes. (Click the photo above)

Basically how it works is, the first step is the user need to request for a password reset at the login page. 

The app will then generate a token and send an email to a link to the reset password page.

The user then will need to enter their new password and the app will validate the token and the new password to make sure the password is matched.

The app will also alert the user that their password is updated on the reset password page. The user is now able to login with their new password.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/7f3x6di0mob4oxmb79et.png)

If the token is either invalid or expired however, the app will alert the user the make a new password reset request to generate a new token and give them a new link.


![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/8y8ydnngnk279w0wd2l4.png)

One thing that I haven't develop is when the user enter a password that doesn't match. Right now the app will alert the user to make a new password reset request if that happens which is not a good user experience. 

That's all for today and for the next day. I would like to redo the first time login flow after I had a discussion with my supervisor today.

I will update about that as I go later. Thank you for reading and have a nice day.