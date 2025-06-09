# Create-a-simple-REST-API-with-Express.js

 Objective: The goal of this assessment is to evaluate your ability to create a simple REST API using Express.js. You will demonstrate on understanding of Node.js, Express.js, and RESTful API principles.

 ## Features

* Express.js setup with JSON middleware
* Root route with welcome message
* Full CRUD for `/items`
* In-memory data storage (array)
* Proper error handling (400, 404, 500)
* Input validation

## Getting Started

### Prerequisites

* Node.js (v14+ recommended)

### Installation

```bash
# Clone the repository
https://github.com/your-username/express-rest-api.git
cd express-rest-api

# Install dependencies
npm install

# Run the server
node index.js
```

### Server

By default, the server runs at:

```
http://localhost:3000
```

---

## API Endpoints

### GET `/`

Returns a welcome message.

```json
"Hello, World!"
```

### GET `/items`

Returns all items.

```json
[
  { "id": 1, "name": "Item A", "description": "Description of Item A" }
]
```

### GET `/items/:id`

Returns a single item by ID.

**Success (200):**

```json
{ "id": 1, "name": "Item A", "description": "Description of Item A" }
```

**Error (404):**

```json
{ "error": "Item not found" }
```

### POST `/items`

Creates a new item.

**Request Body:**

```json
{
  "name": "Item A",
  "description": "Description of Item A"
}
```

**Success (201):**

```json
{
  "id": 1,
  "name": "Item A",
  "description": "Description of Item A"
}
```

**Error (400):**

```json
{ "error": "Name and description are required" }
```

### PUT `/items/:id`

Updates an item by ID.

**Request Body:**

```json
{
  "name": "Updated Item",
  "description": "Updated Description"
}
```

**Success (200):**

```json
{
  "id": 1,
  "name": "Updated Item",
  "description": "Updated Description"
}
```

**Error (400):**

```json
{ "error": "Name and description are required" }
```

**Error (404):**

```json
{ "error": "Item not found" }
```

### DELETE `/items/:id`

Deletes an item by ID.

**Success (204):**
No content

**Error (404):**

```json
{ "error": "Item not found" }
```

---

## Example Postman Requests

**POST /items**

```json
{
  "name": "Notebook",
  "description": "A ruled notebook."
}
```

**PUT /items/1**

```json
{
  "name": "Updated Notebook",
  "description": "Now spiral-bound."
}
```

**DELETE /items/1**
No body required. 
