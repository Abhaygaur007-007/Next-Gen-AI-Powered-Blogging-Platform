# Abhay Gaur  
  
**Email:** [abhaygaur2017@gmail.com](mailto:abhaygaur2017@gmail.com)  
  
**Profession:** Software Engineer  
  
---  
  
# Project: Next-Gen-AI-Powered-Blogging-Platform  
  
**Project Type:** Personal Project  
  
**Description:** This is my personal project named "Next-Gen-AI-Powered-Blogging-Platform". It is a platform that leverages the power of AI to enhance the blogging experience. More details to come as the project progresses.  

# Technologies Used  
  
**Backend:** FastAPI  
  
**Database:** Supabase (SQL), Firestore (NoSQL)  
  
**Frontend:** Managed by another team member 
  
---

# API Documentation  
  
## Blog Endpoints  
  
---  
  
### `POST /create-blog`  
  
This endpoint is used to create a new blog post.  
  
#### Parameters  
  
- `blog_data` (string, required): A JSON string containing the details of the blog post. This string should be a valid JSON object with the following properties:  
    - `title` (string, required): The title of the blog post.  
    - `description` (string, required): A brief description of the blog post.  
    - `tag` (string, required): The tag associated with the blog post.  
- `image_file` (file, optional): An optional image file to be associated with the blog post.  
- `token` (string, required): User's token.  
  
#### Response  
  
- `message` (string): Message indicating the status of the blog creation.  
  
---  
  
### `POST /generate_blog`  
  
This endpoint is used to generate a new blog post for a user.  
  
#### Parameters  
  
- `request_data` (object, required): An object containing the following properties:  
    - `title` (string, required): The title of the blog post.  
    - `topic` (string, required): The topic for the blog post.  
    - `tone` (string, required): The tone of the blog post.  
- `token` (string, required): User's token.  
  
#### Response  
  
- `title` (string): The generated title of the blog post.  
- `body` (string): The generated body of the blog post.  
  
---

### `GET /delete_blog/{blog_guid}`  
  
This endpoint is used to delete a specific blog post.  
  
#### Parameters  
  
- `blog_guid` (string, required): The unique identifier of the blog post.  
- `token` (string, required): User's token.  
  
#### Response  
  
- `message` (string): Message indicating the status of the blog deletion.  
  
---  
  
### `GET /blog/{blog_guid}`  
  
This endpoint is used to retrieve a specific blog post.  
  
#### Parameters  
  
- `blog_guid` (string, required): The unique identifier of the blog post.  
- `token` (string, required): User's token.  
  
#### Response  
  
- `blog` (object): The blog post that matches the provided identifier.  
- `write_access` (boolean): Indicates whether the authenticated user has write access to the blog post.  
  
---  
  
### `GET /all_blogs`  
  
This endpoint is used to retrieve all blog posts.  
  
#### Parameters  
  
- `token` (string, required): User's token.  
  
#### Response  
  
- `all_blogs` (array): An array of all blog posts. 

---

### `GET /all_user_blogs`  
  
This endpoint is used to retrieve all blog posts of a user.  
  
#### Parameters  
  
- `token` (string, required): User's token.  
  
#### Response  
  
- `user_blogs` (array): An array of all blog posts by the user.  
  
---  
  
### `POST /like/{blog_guid}`  
  
This endpoint is used to like a specific blog post.  
  
#### Parameters  
  
- `blog_guid` (string, required): The unique identifier of the blog post.  
- `token` (string, required): User's token.  
  
#### Response  
  
- `message` (string): Message indicating the status of the like action.  
  
---  
  
### `POST /comment/{blog_guid}`  
  
This endpoint is used to post a comment on a specific blog post.  
  
#### Parameters  
  
- `blog_guid` (string, required): The unique identifier of the blog post.  
- `comment` (string, required): The comment to be posted.  
- `token` (string, required): User's token.  
  
#### Response  
  
- `message` (string): Message indicating the status of the comment posting. 

---

&nbsp;

## User Endpoints  

---

### `POST /sign-up`  
  
This endpoint is used to register a new user.  
  
#### Request  
  
- `request_data` (UserSignUp, required): User registration data.  
  
#### Response  
  
- `message` (string): Message indicating the status of the registration.  
- `onboarded` (boolean): Status indicating if the user has completed onboarding.  
- `token` (string): The token to be used for authenticated requests.  
  
---  
  
### `POST /sign-in`  
  
This endpoint is used to authenticate a user.  
  
#### Request  
  
- `request_data` (UserSignUp, required): User login data.  
  
#### Response  
  
- `message` (string): Message indicating the status of the login.  
- `onboarded` (boolean): Status indicating if the user has completed onboarding.  
- `token` (string): The token to be used for authenticated requests. 

---  
  
### `POST /onboarding`  
  
This endpoint is used to complete the user onboarding process.  
  
#### Request  
  
- `request_data` (UserOnboarding, required): User onboarding data.  
- `token` (string, required): The token of the authenticated user.  
  
#### Response  
  
- `message` (string): Message indicating the status of the onboarding process.  
  
---  
  
### `POST /profile`  
  
This endpoint is used to retrieve the user's profile.  
  
#### Request  
  
- `request_data` (UserSignUp, required): User profile data.  
- `token` (string, required): The token of the authenticated user.  
  
#### Response  
  
(Document the expected response here)  

## Exception Handling  
  
All endpoints will return an error message in the format `{ "error": "Error message" }` when an error occurs.  
