## FYP-DevLog 012

>Quicknote: Trying out this new format to update my progress here moving forward. Credit to [Ran Segall](https://youtu.be/8dvk9LgB5Xo) for the documentation template.

### Progress Made
**Frontend**
+ Find a workaround with display name bug when refresh.
    + New request is made to `/auth/me` every time the route is updated
+ Explicitly re-setting the default headers for axios after each token refresh.
+ Add a change password page for the logged in user.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/00uduep1aqyhudzlmdla.png)

**Backend**
+ Create a new endpoint `/auth/change-password` for authenticated user (or logged in user) to change their password. 
+ Fix minor bug with `/auth/me`
    + Add middleware to make sure only authorized user are allowed to make this request
    + Send a badRequest with code 400 instead of just a plain text

### What I did well?
+ Manage to better understand useEffect hooks that I use to fix the display name bug.

### What I'm stuck with?
+ The workaround with display name is not something I'm satisfied with but I can let it go for now.

### How will tomorrow be?
+ Complete the user profile display page, and add edit info page where they can change their name and maybe email.

---

That's all for today, thank you for reading and have a nice day.