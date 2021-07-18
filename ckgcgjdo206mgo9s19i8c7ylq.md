## FYP-DevLog 030

### Progress Made
**Frontend**
+ Implement logout redux flow which reset all of the redux state.
+ Connect admin list page with the backend ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1602864150804/Yu0l5H4SO.png)
+ Add profile page (with edit and delete account functionality)
    + My profile page ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1602864065327/M3FxX0ZFV.png)
    + Other admin profile page ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1602864208610/VERV8g7M4.png)
+ Implement forgot password page ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1602864357195/xppfv4g0q.png)

**Backend**
+ Add `gender` and `phone_no` attribute to admin table
+ Refactor some error response message
+ Refactor `forgotPassword` and `updatePasswordByToken` handler (using the same workflow as send admin invitation)
+ Add permission checking for account deletion
+ Include id with invite list deletion

### What I did well?
+ Feeling great with my progress because of Trello, I feel more focused on what to do.
+ Learn how to reset redux state when the user tries to logout.

### What I'm stuck with?
+ Not feeling stuck, but I know that sometimes I always do something different from what I've planned in the previous log. 

### How will tomorrow be?
+ Planning to complete this authentication module ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1602864917810/6b0AwHU9f.png)
+ For the next phase, I'm planning to do the students-related modules such as the student invite list and student management, then only I can start doing more transactional module when the core user module (Admin and Student) has been completed.
