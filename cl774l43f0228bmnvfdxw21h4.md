# How to build mailchimp signup forms with React (or other JavaScript framework)

I hope I make it clear enough what this article is all about based on the title. But to add on the title a little more, this article will work with any frontend JavaScript framework.

If you ever find yourself in the same position as me, ie. you want to use mailchimp to collect email and you want to connect it to a custom frontend project, this article will be useful to you.

**Note that I will be using React in this article as an example, but this should work with any JavaScript project.**

If you want to have a look at my implementation, this is the [source code](https://github.com/afrieirham/react-mailchimp). Also, this article will assume that you've already setup your project.

With that out of the way, let's get into the article.

----

What you'll need:
- [Mailchimp](https://login.mailchimp.com/signup/) account
- [jsonp](https://www.npmjs.com/package/jsonp)


### 1. Get request URL link from Mailchimp
![Screenshot 2022-08-24 at 11.04.02 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661310476931/r6FEDOB1V.png align="left")
Go to your Mailchimp dashboard, on the sidebar, go to `Audience > Signup forms`. And then, click on `Embeded forms`.


![Screenshot 2022-08-24 at 11.02.31 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661310200618/6hGkkbB__.png align="left")
You can add more fields by clicking on the `Form Fields` and enable all the fields that you need. Then click on `Continue`.


![Screenshot 2022-08-24 at 11.10.38 AM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661310805046/nU80Kp0kI.png align="left")
Find the `form` tag in the code, and copy the `action` URL.

Also, look for `input` tag and find the fields that you've added. Take note the `name` of the `input` tag. We will be using it to submit our form later.

```html
<input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL" required>
```

In this case, the `name` is `EMAIL`.

### 2. Setup the `onSubmit` handler

**Before we proceed:** Don't forget to install [jsonp](https://www.npmjs.com/package/jsonp) package in your project.

First, we need to replace the `/post?` with `/post-json?` in our url. Then add this code in your `onSubmit` handler. I'll explain what we did later.

```js
const onSubmit = e => {
    e.preventDefault();
    const url = 'your-mailchimp-url';
    jsonp(`${url}&EMAIL=${email}`, { param: 'c' }, (_, data) => {
        const { msg, result } = data
        // do something with response
        alert(msg);
    });
};
```

We use the `jsonp` function to make the request. We then append `&EMAIL=<your-input-email>` to include the email that we want to submit.

If you have more fields, just use the `name` value you've listed out from Mailchimp code before, and append it accordingly.

Then we add the `{ param: 'c' }` as the second parameter, but I don't really know why we need this to be honest. 

Lastly, we add a callback function to handle the response. The relevant response data will be available to you in the second argument. That's why I use `_` for the first argument.

From there, I just alert the user with the response message.

And that's it, you should be able to submit the email to Mailchimp now.

---

### For more context

I write this article to share my learning when I was building "Coming Soon" page for my upcoming project [sea-techjobs.com](https://sea-techjobs.com). (shameless plug here ✊)

I want to collect emails using Mailchimp but I don't want to use their form builder. I think I can do a better job with React and ChakraUI to design the website but I wasn't sure how to exactly get this two connected.

I first stumbled upon this [video](https://youtu.be/kNiHE-FoA1c) on how to setup Mailchimp newsletter with React. And in that video, they were using this library called [react-mailchimp-subscribe](https://www.npmjs.com/package/react-mailchimp-subscribe) but I couldn't get the state working right.

I looked into the source code and figure out exactly how it works under the hood. I realized that I don't need that library for it to work. I can just copy how it works and tweak it to suit my needs.

Then I thought, why not write an article to hopefully help other people who might be facing the same issue – thus this article.

So I guess that's it from me. Thank you for reading and have a good day.

p/s - If you're curious about the project that I'm working on, you can read this [twitter thread](https://twitter.com/afrieirham_/status/1561369652067938304) to learn more. It's in Malay though, I'm sorry if you're english reader. 🤧


