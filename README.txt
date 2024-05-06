This application provides user authentication and management functionalities using a
 React frontend and a Node.js backend. It includes APIs for user registration, login, 
 password management, user data retrieval, and image uploading. The backend is built with Express.js
and MongoDB for database storage, while the frontend is developed using React and Bootstrap for styling.

Backend APIs

User Authentication API
1* Register
Endpoint: /register
Method: POST
Request Body: { "fname": "John", "lname": "Doe", "email": "john@example.com", "password": "password123", "userType": "regular" }
Response: { "status": "ok" }
2* Login
Endpoint: /login-user
Method: POST
Request Body: { "email": "john@example.com", "password": "password123" }
Response: { "status": "ok", "data": "<JWT Token>" }
User Data Retrieval
3* Endpoint: /userData
Method: POST
Request Body: { "token": "<JWT Token>" }
Response: { "status": "ok", "data": { "fname": "John", "lname": "Doe", "email": "john@example.com", "userType": "regular" } }
Password Management API
4* Forgot Password
Endpoint: /forgot-password
Method: POST
Request Body: { "email": "john@example.com" }
Response: { "status": "ok" }
5* Reset Password
Endpoint: /reset-password/:id/:token
Method: POST
Request Body: { "password": "newPassword123" }
Response: { "status": "verified" }
User Management API
6* Get All Users
Endpoint: /getAllUser
Method: GET
Response: { "status": "ok", "data": [ { "fname": "John", "lname": "Doe", "email": "john@example.com", "userType": "regular" }, ... ] }
7* Delete User
Endpoint: /deleteUser
Method: POST
Request Body: { "userid": "<user-id>" }
Response: { "status": "Ok", "data": "Deleted" }
Image Management API
8* Upload Image
Endpoint: /upload-image
Method: POST
Request Body: { "base64": "<base64-encoded-image>" }
Response: { "Status": "ok" }
9* Get Image
Endpoint: /get-image
Method: GET
Response: { "status": "ok", "data": [ { "image": "<base64-encoded-image>" }, ... ] }

Frontend Components
1* Login Component
Renders a form for user login.
Sends login credentials to the backend for authentication.

2* Signup Component
Renders a form for user registration.
Sends registration data to the backend for processing.

3* UserDetails Component
Displays user details after successful login.
Differentiates between regular users and administrators.
Allows administrators to manage user accounts.

4* AdminHome Component
Displays a dashboard for admin users.
Allows admins to view and manage user accounts.
Includes functionalities for searching users, deleting users, and logging out.

Architecture
Backend: Built with Node.js and Express.js, providing RESTful APIs for user management and authentication. Uses MongoDB for data storage.
Frontend: Developed with React.js and Bootstrap for responsive UI design. Implements React Router for navigation between pages.
Authentication: Utilizes JSON Web Tokens (JWT) for user authentication and authorization.
Password Management: Supports password reset functionality using email verification.
Image Management: Allows users to upload and retrieve images.
