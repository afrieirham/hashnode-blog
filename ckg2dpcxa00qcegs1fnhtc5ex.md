## FYP-DevLog 025

### Progress Made
**Frontend**
+ No progress made

**Backend**
+ Refining invite-only workflow, quite chaotic due to indecisiveness.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1602255082586/WFpDAomJN.png)
+ Invite-only admin registration flow:
    1. Existing admin invite new admin via email.
    2. Before sending link to the invited user, the backend will check if email already exist.
        + If email exist, it will check if the account has been activated (meaning invited email has created the account). If active then error.
        + If the account is not active, it will check for link validity, whether it has expired or not. If not expired then error.
        + If expired then continue no 3
    3. Email will be sent to the invited user with link to complete their profile.

### What I did well?
+ Satisfied with the current flow, can't wait to implement it in the frontend.

### What I'm stuck with?
+ Not feeling stuck.

### How will tomorrow be?
+ Implement this feature on the frontend.