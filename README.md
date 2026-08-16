#  Full Stack Notes (Doubts I Cleared)

These are my personal notes while learning Full Stack Development. I wrote them in simple words so I can revise them quickly whenever I need.

---

# MVC Architecture

MVC helps keep the backend organized by separating different responsibilities.

## Route
- Receives the request.
- Decides which controller should handle it.
- Think of it as the **entry gate**.

## Controller
- Handles the request.
- Talks to the model.
- Sends the final response back.

## Model
- Handles data.
- Reads and writes data from the database or file.
- Never sends responses directly.

### Flow

```
Client
   ↓
Route
   ↓
Controller
   ↓
Model
   ↓
Database / JSON
```

**Easy Rule**

- Route → Where to go
- Controller → What to do
- Model → Where the data is

---

# Backend & API

## Frontend

The part users can see and interact with.

Examples:
- Buttons
- Forms
- Images
- Text

---

## Backend

Works behind the scenes.

It:
- receives requests
- processes data
- stores data
- sends responses

---

## API

API is simply a bridge between frontend and backend.

Frontend asks something.

Backend returns the answer.

Example:

```
Frontend
     ↓
API
     ↓
Backend
```

---

# Request & Response

## Request

Data sent from client to server.

Example:

```
GET /users
```

---

## Response

Data returned by the server.

Example:

```json
{
   "name":"Himanshu"
}
```

---

# Status Codes

| Code | Meaning |
|------|----------|
|200|Success|
|201|Created Successfully|
|400|Bad Request|
|401|Unauthorized|
|404|Not Found|
|500|Internal Server Error|

Always send the correct status code.

---

# JSON

JSON is the common language used between frontend and backend.

Example

```json
{
   "name":"Himanshu",
   "age":19
}
```

---

# Why Postman?

Browsers mostly send GET requests directly.

Postman helps test:

- GET
- POST
- PUT
- PATCH
- DELETE

without creating a frontend.

---

# Backend Flow

```
Browser
   ↓
Route
   ↓
Controller
   ↓
Model
   ↓
Database
   ↑
Response
```

---

# JavaScript Basics

## Objects

Objects store information using key-value pairs.

Example

```javascript
const student = {
   name: "Himanshu",
   marks: 90
}
```

Access values

```javascript
student.name
```

---

## Arrays

Arrays store multiple values.

```javascript
const students = [
   "Info",
   "Himanshu",
   "Alpha"
]
```

---

# Useful Array Methods

## forEach()

Runs a function on every item.

```javascript
students.forEach()
```

---

## map()

Creates a new array.

---

## filter()

Returns matching items.

---

## find()

Returns the first matching item.

---

## some()

Returns true if at least one item matches.

---

## every()

Returns true only if all items match.

---

## sort()

Sorts the array.

---

## reduce()

Converts the array into a single value.

Example:

Total marks.

---

# Error Handling

Errors can happen anytime.

Examples

- Wrong input
- Missing file
- Database issue

Use

```javascript
try{

}catch(error){

}
```

- try → Execute code
- catch → Handle error

Never crash the server.

Always return a proper response.

---

# Backend Folder Structure

```
project/
│
├── routes/
├── controllers/
├── models/
├── middleware/
├── app.js
```

## routes

Handles URLs.

---

## controllers

Contains business logic.

---

## models

Works with database or JSON data.

---

## middleware

Runs before the request reaches the controller.

Examples

- Authentication
- Logging
- Validation

---

# Express Middleware

```javascript
app.use(express.json())
```

Used to read JSON data from the request body.

Always place it before your routes.

---

# Important Terms

## req

Contains data sent by the client.

---

## res

Used to send data back.

---

## Route

Receives incoming requests.

---

## Controller

Processes the request.

---

## Model

Works with data.

---

# Git vs GitHub

## Git

Version control system installed on your computer.

Tracks code changes.

---

## GitHub

Cloud platform where Git repositories are stored online.

---

# Git Workflow

## Initialize

```bash
git init
```

---

## Add Files

```bash
git add .
```

---

## Commit

```bash
git commit -m "Added Login Page"
```

---

## Push

```bash
git push origin main
```

---

## Check Status

```bash
git status
```

---

## Clone Repository

```bash
git clone <repository-url>
```

---

# Good Commit Messages

## Good

```
Added Login Page
```

```
Fixed Navbar Bug
```

```
Created User API
```

## Bad

```
update
```

```
final
```

```
changes
```

---

# CORS

CORS stands for

**Cross-Origin Resource Sharing**

It allows one website to access another server.

Example

Frontend

```
localhost:3000
```

Backend

```
localhost:5000
```

Since ports are different, the browser blocks the request unless CORS is enabled.

Enable it in Express:

```javascript
const cors = require("cors");

app.use(cors());
```

For production:

```javascript
app.use(
    cors({
        origin: "https://yourwebsite.com"
    })
);
```

---

# Quick Revision

✔ Route → Receives request

✔ Controller → Handles logic

✔ Model → Works with data

✔ API → Connects frontend and backend

✔ JSON → Data format

✔ Postman → API Testing

✔ req → Incoming data

✔ res → Outgoing response

✔ Middleware → Runs before controller

✔ Git → Version Control

✔ GitHub → Online Repository

✔ CORS → Allows requests between different origins

---

# Final Note

While building backend applications, always remember this flow:

```
Client
   ↓
Route
   ↓
Controller
   ↓
Model
   ↓
Database
   ↑
Response
```

Keeping these responsibilities separate makes the project easier to understand, debug, and maintain.
