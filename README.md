# Intro to Backend Development - freeCodeCamp YouTube Tutorial

This repository contains the completed backend code following the freeCodeCamp "Intro to Backend Development" video tutorial.

➡️ **Course Video:** [Intro to Backend Web Development – Node.js & Express Tutorial for Beginners](https://www.youtube.com/watch?v=KOutPbKc9UM)

---

## 🛠️ Features Implemented
- **Node.js & Express Setup:** Modern ES Modules structure (`"type": "module"`).
- **MongoDB Connection:** Connected via Mongoose ODM.
- **Model-Route-Controller Architecture:**
  - `User` model with password hashing via `bcrypt` (10 salt rounds) and password verification.
  - `Post` model with name, description, and age schema validation.
- **Authentication Routes (`/api/v1/users`):**
  - `POST /register`: Registers a user, hashes password with bcrypt.
  - `POST /login`: Validates credentials and logs in the user.
  - `POST /logout`: Logs out the user.
- **CRUD Operations for Posts (`/api/v1/posts`):**
  - `POST /create`: Create a new post.
  - `GET /getPosts`: Retrieve all posts.
  - `PATCH /update/:id`: Update an existing post by ID.
  - `DELETE /delete/:id`: Delete a post by ID.

---

## 🚀 How to Run Locally

### 1. Install Dependencies
```sh
npm install
```

### 2. Configure Environment Variables
Create or edit `.env` in the root directory:
```env
PORT=4000
MONGODB_URI="your_mongodb_connection_string_here"
```

### 3. Start the Server
- Development mode (with auto-reload using `nodemon`):
  ```sh
  npm run dev
  ```
- Production mode:
  ```sh
  npm start
  ```

Server will run at `http://localhost:4000`.

---

## 📬 API Endpoints Summary

### User Routes (`/api/v1/users`)
| Method | Endpoint | Description | Request Body |
|---|---|---|---|
| `POST` | `/api/v1/users/register` | Register new user | `{ "username": "...", "email": "...", "password": "..." }` |
| `POST` | `/api/v1/users/login` | Login user | `{ "email": "...", "password": "..." }` |
| `POST` | `/api/v1/users/logout` | Logout user | `{ "email": "..." }` |

### Post Routes (`/api/v1/posts`)
| Method | Endpoint | Description | Request Body |
|---|---|---|---|
| `POST` | `/api/v1/posts/create` | Create a post | `{ "name": "...", "description": "...", "age": 25 }` |
| `GET` | `/api/v1/posts/getPosts` | Fetch all posts | None |
| `PATCH` | `/api/v1/posts/update/:id` | Update post by ID | `{ "name": "Updated Name" }` |
| `DELETE` | `/api/v1/posts/delete/:id` | Delete post by ID | None |
