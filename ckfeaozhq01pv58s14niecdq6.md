## FYP-DevLog 007

I don't really have anything in mind about what to do today so it started off with me trying to figure out what I can do today.

After taking a look at the list of API endpoints that I have, I decided to continue the implementation of the forgot password feature.

Before I proceed, I think it's better for me to tell you what do I use for my backend code. Introducing `AdonisJs`, a Laravel-like Nodejs framework.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/a930a1px59ajeycos1al.png)

The main reason why I choose this framework is because I am quite familiar with how Laravel works but I want to use JavaScript as the language. I just 'prefers' it. And I also like the npm packages available with Nodejs.

With that said, there is a way on how to handle authentication with AdonisJs, which brought us to Adonis Persona.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/2m45s0wgrqjemf1sf8js.png)

The way Adonis Persona handles forgotPassword is they first require user's email to create a token, which then will be used to change the password. Simple enough.

But the challenge for me today is I can't get Adonis to send the email for of link with the token to the user. The issue was me not reading the documentation really. I was wrong about formatting the email template with edge.

And then I also realized that I was on the wrong path for the flow of resetting password. I was trying to create a form for the password reset in the email itself.

What I should do is to email them to a page for the password reset and insert the token to that page so that I can use the token and take the new password to send it to the updatePassword endpoint.

It was not a smooth day today but I'm glad because now I know what I want to do tomorrow.

Until then, thank you for reading.
