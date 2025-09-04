Ticketing System (Express.js)

A simple Ticketing System API built with Express.js using a JSON file (db.json) as the database.
Supports CRUD operations, middleware validation, and a resolve endpoint for tickets.
Follows the MVC architecture for clean structure.

🚀 Features

Create, Read, Update, Delete tickets

Default ticket status = pending

Resolve a ticket (pending → resolved)

Middleware validation for required fields

404 handling for undefined routes

Modular structure (Models, Controllers, Routes, Middleware)

📂 Project Structure
ticketing-system/
│── db.json
│── server.js
│── package.json
│── models/
│   └── ticketModel.js
│── controllers/
│   └── ticketController.js
│── routes/
│   └── ticketRoutes.js
│── middlewares/
│   └── dataCheckMiddleware.js

🛠️ Setup Instructions

Clone the project / create folder:

mkdir ticketing-system
cd ticketing-system


Initialize project & install dependencies:

npm init -y
npm install express fs


Add the given folder structure & files.

Run the server:

node server.js


Server runs at:

http://localhost:3000

📌 API Endpoints
🎟 Tickets
1. Get all tickets
GET /tickets

2. Get ticket by ID
GET /tickets/:id

3. Create a ticket (with middleware validation)
POST /tickets


Request Body:

{
  "title": "Login Issue",
  "description": "Unable to login",
  "priority": "high",
  "user": "John Doe"
}


👉 Default status: "pending"

4. Update a ticket
PUT /tickets/:id


Request Body (any updatable field):

{
  "title": "Updated Title",
  "priority": "medium"
}

5. Delete a ticket
DELETE /tickets/:id

6. Resolve a ticket
PATCH /tickets/:id/resolve


👉 Updates status: "resolved"

❌ Error Handling

Missing required fields in POST /tickets →

{ "error": "Data insufficient, please provide all required fields" }


Invalid ID →

{ "error": "Ticket not found" }


Undefined route →

{ "error": "404 Not Found" }

🧪 Testing

Use Postman or browser (for GET requests).
Example:

GET http://localhost:3000/tickets

POST http://localhost:3000/tickets with JSON body

PATCH http://localhost:3000/tickets/1/resolve

📖 Example db.json
{
  "tickets": [
    {
      "id": 1,
      "title": "System Crash",
      "description": "PC restarts randomly",
      "priority": "high",
      "user": "Alice",
      "status": "pending"
    }
  ]
}

✅ Tech Stack

Node.js

Express.js

File System (fs) module

JSON (as a simple database)
