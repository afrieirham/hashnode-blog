## FYP-DevLog 013

### Progress Made
**Frontend**
+ Fix bugs with sidebar active state not working properly.
    + Initially it was using `defaultActiveState` instead of `activeState` for the Nav component.
    + Use `useEffect` hooks to update the `activeState` based on the route pathname

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/gj4oycr2q92sy5qov2li.gif)

**Backend**
+ Reconstruct the response data for get single admin to include email.

**Misc**
+ Created a terminal alias to start React (frontend) and Adonis (backend) server with a single command using concurrently.

### What I did well?
+ Manage to make use of `useEffect` hooks in a different way than yesterday's use case.
+ Pretty motivated and did more than an hour today.

### What I'm stuck with?
+ Always feeling like I need to change the endpoint that I've made to suit the new need from the frontend.

### How will tomorrow be?
+ Complete the user profile page and edit profile functionality.