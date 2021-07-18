## FYP-DevLog 010

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/la2racw6kcs08eh5zfye.png)

Today I decided to refactor my react app that uses axios. From the beginning of my development up until today, every time I need to make a request to my backend, I need to manually fetch the auth token in localstorage, construct it, and included it in the request header. 

The problem with it is because I am repeating the same codes over and over and if you're a programmer yourself you know that something is wrong with it. 

And to be honest I realized it early enough, it's just that only today I want to do something about it. So now all I did was to set the header after a successful login attempt in the login page.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/orn88av6prmoy04y0orp.png)

The other thing that I did today was trying to implement React Context API to display the logged in user's information on the page to make it more relevant. For example in the top-right corner of the dashboard, up until now it's hardcoded with `username`. That is why I'm implementing React Context API. 

That is all for today, thank you for reading, have a nice day.