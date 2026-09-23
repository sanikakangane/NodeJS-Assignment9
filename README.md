# NodeJS-Update-Delete-Assignment9

A beginner-friendly Node.js Express assignment created to understand **updating and deleting users using Express, MongoDB, Mongoose, route parameters, and request body data.**

## Tasks

1. **Update User using PATCH**
2. **Delete User using DELETE**
3. **Error Handling for Update and Delete Operations**

## Project Structure

```text
├── schema
│   └── userSchema.js
│
├── model
│   └── userModel.js
│
├── router
│   └── userRouter.js
│
├── Screenshots
│
├── server.js
├── package.json
└── README.md
```

## Concepts Used

- Node.js
- Express.js
- MongoDB
- Mongoose
- Express Routing
- Route Parameters
- `req.params`
- `req.body`
- PATCH Request
- DELETE Request
- MongoDB ObjectId
- Mongoose Schema
- Mongoose Model
- `findByIdAndUpdate()`
- `findByIdAndDelete()`
- Error Handling
- HTTP Status Codes

## Tasks Performed

### Task 1 - Update User

Created a PATCH API to update an existing user's information using the user ID.

Route:

```text
PATCH /api/users/:id
```

The user ID is extracted using `req.params`, while the updated information is received using `req.body`.

Example:

```text
/api/users/6ab365af890c45a13f0ef91b
```

Request Body:

```json
{
  "age": 23,
  "course": "MCA"
}
```

The response is:

```json
{
  "message": "User updated successfully"
}
```

The updated user information is stored in MongoDB using Mongoose.

### Task 2 - Delete User

Created a DELETE API to delete an existing user using the user ID.

Route:

```text
DELETE /api/users/:id
```

Example:

```text
/api/users/6ab365af890c45a13f0ef91b
```

The response is:

```json
{
  "message": "User deleted successfully"
}
```

The user is removed from the MongoDB `users` collection using Mongoose.

### Task 3 - Error Handling

Added error handling for invalid MongoDB IDs, users that do not exist, and database errors.

#### Invalid MongoDB ID

Example:

```text
/api/users/123
```

Response:

```json
{
  "message": "Invalid MongoDB ID"
}
```

#### User Not Found

If a valid MongoDB ID is provided but the user does not exist:

```json
{
  "message": "User not found"
}
```

#### Database Error

If a database error occurs:

```json
{
  "message": "Database error"
}
```

## MongoDB Connection

The application connects to MongoDB using Mongoose.

Database:

```text
userDB
```

Collection:

```text
users
```

Successful connection displays:

```text
MongoDB connected successfully
```

## How to Run

Navigate to the assignment folder:

```text
cd Assignment-9
```

Install the required dependencies:

```text
npm install
```

Start the server:

```text
node server.js
```

The server will run on:

```text
http://localhost:1100
```

## Routes

| Task | Method | Route | Purpose |
|---|---|---|---|
| Task 1 | PATCH | `/api/users/:id` | Update user |
| Task 2 | DELETE | `/api/users/:id` | Delete user |

## Expected Output

### Task 1 - Update User

Request:

```text
PATCH http://localhost:1100/api/users/6ab365af890c45a13f0ef91b
```

Body:

```json
{
  "age": 23,
  "course": "MCA"
}
```

Response:

```json
{
  "message": "User updated successfully"
}
```

### Task 2 - Delete User

Request:

```text
DELETE http://localhost:1100/api/users/6ab365af890c45a13f0ef91b
```

Response:

```json
{
  "message": "User deleted successfully"
}
```

### Invalid ID

Request:

```text
PATCH http://localhost:1100/api/users/123
```

Response:

```json
{
  "message": "Invalid MongoDB ID"
}
```

### User Not Found

Response:

```json
{
  "message": "User not found"
}
```

## Author

**Sanika Kangane 👩🏻‍💻**
