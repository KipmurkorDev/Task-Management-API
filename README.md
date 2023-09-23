# Express.js API with Multer and Sharp Middleware

This is a powerful Express.js API that offers user and task management features, along with image uploading and processing capabilities using Multer and Sharp middleware.

## Table of Contents

1. [Authentication](#authentication)
2. [User Routes](#user-routes)
3. [Task Routes](#task-routes)
4. [Image Upload and Processing](#image-upload-and-processing)

---

## Authentication

All routes in this API demand authentication, which is implemented using JSON Web Tokens (JWTs). Users can acquire a token by registering or logging in.

### User Registration

- **Route:** `POST /users`
- **Description:** Register a new user.
- **Request Body:** A JSON object containing user details (name, email, password).
- **Response:** A JSON object with user details and an authentication token.

### User Login

- **Route:** `POST /users/login`
- **Description:** Log in an existing user.
- **Request Body:** A JSON object containing user email and password.
- **Response:** A JSON object with user details and an authentication token.

### User Logout

- **Route:** `POST /users/logout`
- **Description:** Log out the current user.
- **Authentication:** Requires a valid JWT token.
- **Response:** Successful logout if the token is valid.

### User Logout from All Devices

- **Route:** `POST /users/logoutAll`
- **Description:** Log out the user from all devices.
- **Authentication:** Requires a valid JWT token.
- **Response:** Successful logout from all devices if the token is valid.

---

## User Routes

### Get User Profile

- **Route:** `GET /users/me`
- **Description:** Retrieve the profile of the authenticated user.
- **Authentication:** Requires a valid JWT token.
- **Response:** A JSON object with user details.

### Update User Profile

- **Route:** `PATCH /users/me`
- **Description:** Update user profile information.
- **Authentication:** Requires a valid JWT token.
- **Request Body:** A JSON object with user details to be updated (name, email, password, age).
- **Response:** A JSON object with updated user details.

### Delete User Account

- **Route:** `DELETE /users/me`
- **Description:** Delete the authenticated user's account.
- **Authentication:** Requires a valid JWT token.
- **Response:** A JSON object with deleted user details.

---

## Task Routes

### Create a New Task

- **Route:** `POST /tasks`
- **Description:** Create a new task.
- **Authentication:** Requires a valid JWT token.
- **Request Body:** A JSON object containing task details (description).
- **Response:** A JSON object with created task details.

### Get User's Tasks

- **Route:** `GET /tasks`
- **Description:** Retrieve tasks owned by the authenticated user.
- **Authentication:** Requires a valid JWT token.
- **Query Parameters:** `completed` (boolean), `limit` (number), `skip` (number), `sortBy` (field:asc/desc).
- **Response:** A JSON array of tasks.

### Get Task by ID

- **Route:** `GET /tasks/:id`
- **Description:** Retrieve a task by its ID.
- **Authentication:** Requires a valid JWT token.
- **Response:** A JSON object with task details.

### Update Task

- **Route:** `PATCH /tasks/:id`
- **Description:** Update a task by its ID.
- **Authentication:** Requires a valid JWT token.
- **Request Body:** A JSON object with task details to be updated (description, completed).
- **Response:** A JSON object with updated task details.

### Delete Task

- **Route:** `DELETE /tasks/:id`
- **Description:** Delete a task by its ID.
- **Authentication:** Requires a valid JWT token.
- **Response:** A JSON object with deleted task details.

---

## Image Upload and Processing

### Upload User Avatar

- **Route:** `POST /users/me/avatar`
- **Description:** Upload a user's avatar image.
- **Authentication:** Requires a valid JWT token.
- **Request:** Form data with an image file named "avatar."
- **Response:** Status 200 on successful upload.

### Delete User Avatar

- **Route:** `DELETE /users/me/avatar`
- **Description:** Delete a user's avatar image.
- **Authentication:** Requires a valid JWT token.
- **Response:** Status 200 on successful deletion.

### Get User Avatar

- **Route:** `GET /users/:id/avatar`
- **Description:** Retrieve a user's avatar image by their ID.
- **Response:** The user's avatar image in PNG format if available, or a 404 error if not found.

---
