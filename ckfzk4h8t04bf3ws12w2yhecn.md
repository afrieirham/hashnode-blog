## FYP-DevLog 023

### Progress Made
**Frontend**
+ Setup axios to use my api URL as the base url  and attach a `user_type` data into every request I made from frontend. 

**Backend**
+ Refactor my whole backend structure including the database structure, resources relationships, route endpoints, and general logic.
     + I feel like the previous backend was a bit too complicated and over-engineered with excessive validation and middleware. So I decided to refactor most of the logic to make it more simple.
     + After using my own API with my previous react app, there are a lot of things I have in mind that needs to change. Thus today's 8 hours of code. 
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1602084582037/fWNtKqDAj.png)

### What I did well?
+ Manage to made a lot of progress rethinking and refactoring my backend code.

### What I'm stuck with?
+ Authentication, particularly the JWT part with refresh token and access token. As of now, I store both token in the localStorage of the browser but I have read a lot of articles saying it is vulnerable to many attacks.

### How will tomorrow be?
+ Continue with implementing some other endpoints to be used in a new workflow that I have in mind which is an exclusive invite only account registration.