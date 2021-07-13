## How to build a fullstack app?

# The Problem

New developers find it hard to decide on what to use and/or learn when starting a new full-stack project.

The project might be a side-project, university assignments, final year project, business idea, or hackathon project.

Not only that, but when I was starting, I was struggling thinking about what does it takes to create a full stack app. 

- What do I need to learn?
- How does it all work together?
- Is my skills currently enough or do I need to learn more?
- Is using Bootstrap okay? Or am I cheating?

# Understading the big picture

Before you start developing or creating an app, you need to understand the big picture first, so that you know what does it take and what are things you need to learn.

There might be things that you have already understand and know how to do, but you don't know how do these skills play in the big picture.

So what does an app needs? 

Generally speaking, a full-stack app have a few components that are working together.

- Database ⇒ to store data
- Storage ⇒ to store assets
- API ⇒ to process request
- User Interface ⇒ to let users interact with your app

One thing to note is hosting won't be covered in this article. While it is an essential aspect in distributing or sharing your apps to your users, it is not something you need to worry about when you're in development. 

Most likely, you'll be developing on a local machine (i.e. your laptop) in a localhost. However, the main thing you need to know about hosting is – it's a place where all of the components live.

You probably have heard of the term frontend and backend. In this case, the database, the storage, and the API collectively is called the backend, and the user interface is called the frontend.

Most, if not all, full-stack app must have at least a database, an API, and a user interface. Storage is optional depending on the requirements of the system you're building.

So what are these components? Let's start with the easy one, the user interface. 

### User Interface (UI)

A user interface is the thing that users interact with. This might be a website, a mobile app, or a desktop app.

I'm sure many of you here have a pretty good idea of what a user interface is and what role does it play. So let's move on to the next one.

### Database

Again a pretty straightforward one.

A database is the component that stores the data of the app. It can be the user's email and password, the price of an item, user's address and so on.

This one is also pretty easy to understand. You might not know how to use and set it up, but most probably you know how it works — it stores data. Next is API.

### Application Programming Interface (API)

This is a big one. You might have heard of it but you have no idea what it is and how does it work. If that's the case, don't worry because I was in the same spot when I was starting.

In the context of building a full-stack app, an API usually is the server-side code where it handles the request made by the client (i.e. the user interface of your project). For example, if a user wants to buy an item in an e-commerce store, the transaction needs to be processed by the API or the server-side code. This process is done through HTTP protocol.

> If you have no idea what HTTP protocol is, you can watch this [HTTP Crash Course](https://www.youtube.com/watch?v=iYM2zFP3Zn0) video by Traversy Media. I highly recommend you watch the video to understand this topic.

Processes that can be handled by the API may include updating the stock count of an item, creating a new order for the purchase, send a confirmation email to the customer, notify the seller, and many more. 

In a nutshell, the API acts like the operator of the app. It does all of the work.

### Storage

You might be confused with this one because it seems like the role is the same as the database right?

Well, not exactly.

Storage is a place to store assets such as photos, files, and videos. All of these assets can't be stored in a database because it is not in a text or string format. The database usually stores the location reference of the assets in the storage.

To understand what I meant by a location reference is, try to go to this link of a [cat photo](https://www.vets4pets.com/globalassets/close-up-of-cat-looking-up.jpg), the URL of the photo is the location reference. This URL is the thing that will be stored in the database. I'll explain how you can use this link to show it in your app later.

An example of a storage is simply the folder on your Desktop right now, which is called file system. There is usually a dedicated folder in the project that is used to store user generated assets.

![storage.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1625911053209/dnV6vidOo.gif)

The GIF above shows where does the photo goes after you upload it.

Apps like Instagram and YouTube needs a place to store those files that will be fetched later. However, with big platforms like Instagram and YouTube, they usually will use an external cloud storage.  

Services like [AWS S3](https://s3.amazonaws.com/), [Firebase Cloud Storage](https://firebase.google.com/products/storage), and [Cloudinary](https://cloudinary.com/), are some of the examples of it. These services offer a dedicated server just to manage and store assets. You can explore and learn more about them later, but all of those are a part of the storage component.

The most common use case for a storage is to store user generated assets. If you app does not have a feature that allow the user to upload files, photos, or videos. You can get away with having no storage.

I hope that clear things up.

# But how does everything works together?

When I was starting, I do know some of the components needed to build an app. But I really have no clue how does it work together.

To explain this, I will use the MERN stack as an example. MERN stands for **M**ongoDB, **E**xpress, **R**eact, and **N**ode.js

This stack consists all of the components I talked about previously except for the storage.

- Database ⇒ MongoDB
- API ⇒ Express & Node.js
- User Interface ⇒ React

Imagine a to-do list app built with this stack. Features includes; users can add, delete, edit, and view a task. They can also see a list of all the tasks.

When a user opens your app for the first time, the React app will make a `GET` request to the API to fetch all of the user's tasks. The API will then fetch all of the data needed from the database, process it, and send it back to the React app.

From here, the React app will render the data provided by the API and the user will see their task on the home page.

The user can also add, delete, and edit by making a `POST`, `DELETE`, and `PUT` request respectively.

As you can see from the example, every component have its own role. 

Now imagine the to-do app that lets the user to upload a photo to a task. The React app will need to send the photo to the API via `POST` request, the API will then store it in the file system or upload it to an external file storage. The API will also store the location reference of the photo in the database.

Next, to display the photo in the UI, the React app will reference it using the location reference stored by the database and fetch the photo from the storage. It may look something like this in a React app.

```jsx
<image src="https://www.vets4pets.com/globalassets/close-up-of-cat-looking-up.jpg" />
```

I hope by now you have a clearer understanding of how everything works together. By the way, you can always replace the MERN stack with any framework combination of your choice. The important thing to note is you know which components does the framework satisfy.

# Conclusion

Learning how to create a full-stack app is a long journey, it will take time to master every aspect of it. Even then, you won't be able to catch up with all the available technologies and services provided.

Good news is, you don't need to know everything!

Just understand the core principle of how it works, then pick and choose whatever frameworks, technologies, or services that you need to make it work. 

Remember that the important thing is your ability to put things together, and solve a problem – tools are not important.

Finally, I wish you all the best in your journey of to learn building a full-stack app. If you have any questions, feel free to [dm me on Twitter](https://twitter.com/afrieirham_) or leave a comment, I will try my best to answer your questions.