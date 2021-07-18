## FYP-DevLog 034

### Progress Made
**Frontend**
+ Implement user profile view in the dashboard
+ Completed course management module implementation
    + Course list page ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1603391588719/DzGIfcQHp.png)
    + Add course modal ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1603391622692/EweVSOczh.png)
    + Course details page (with registered students) ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1603391655537/l66FUsrYS.png)
    + Course details page (without registered students) ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1603391756073/TQVd6IqvA.png)
    + Edit course page ![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1603391679281/dz7za9msq.png)

**Backend**
+ Complete student-uploads module
+ Standardize API response
    + Success response `{ "message": "success", "data": {} }`
    + Error response `{ "message": "error", "error": {} }`
+ Implement course attachment with student-uploads endpoint

### What I did well?
+ Learned how to handle file uploads with Adonis and AWS S3
+ Decided to standardize the API response for a better development experience

### What I'm stuck with?
+ Coming up with a design will coding is not a great idea, should use Figma to create a mockup but that takes too much time

### How will tomorrow be?
+ Continue with student invite list and student management module for the frontend