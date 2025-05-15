PermaList 📝📌
PermaList is a minimalist list-keeping web application that helps users create, manage, and revisit important lists that matter — from life goals and reading logs to packing checklists and shared group plans. Built with Node.js, Express, and PostgreSQL.

Features
Create and manage multiple permanent lists

Add, edit, and delete items inside each list

Share lists across devices (and optionally across users)

Store everything in a PostgreSQL database for persistence

Clean UI with a focus on simplicity and usability

Technologies Used
Node.js

Express.js

PostgreSQL

pg (node-postgres)

EJS / React (depending on your frontend stack)

CSS / Tailwind / Bootstrap (depending on styling)

dotenv for environment config

Installation
Clone the repository:

bash
Copy
Edit
git clone https://github.com/your-username/permalist.git
cd permalist
Install dependencies:

bash
Copy
Edit
npm install
Set up the database:

Create the database:

sql
Copy
Edit
CREATE DATABASE permalist;
Create tables:

sql
Copy
Edit
CREATE TABLE lists (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100)
);

CREATE TABLE list_items (
  id SERIAL PRIMARY KEY,
  list_id INTEGER REFERENCES lists(id),
  content TEXT,
  is_done BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
Create a .env file:

ini
Copy
Edit
DB_HOST=localhost
DB_USER=your_username
DB_PASSWORD=your_password
DB_NAME=permalist
DB_PORT=5432
Run the server:

bash
Copy
Edit
node index.js
Usage
Navigate to http://localhost:3000

Create a new list (e.g., "Bucket List")

Add items to the list (e.g., "Skydive in Dubai", "Visit Kyoto")

Check off completed items

Delete or update items anytime

Example Screenshots (Optional)
Add UI screenshots showing list creation and item management.

API Routes (if applicable)
Method	Route	Description
GET	/lists	Show all lists
POST	/lists	Create a new list
GET	/lists/:id	View a specific list
POST	/lists/:id/items	Add item to a list
PUT	/items/:itemId	Update item content/status
DELETE	/items/:itemId	Delete an item

Future Improvements
User authentication (login/signup)

Shared lists with other users

Drag-and-drop sorting

Mobile responsiveness

Dark mode

Tagging and filtering

License
MIT License
