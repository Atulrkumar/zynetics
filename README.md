# zynetic-backend
🛠 Backend Developer Assignment – RESTful API Task

📚 Bookstore RESTful API
This is a simple Node.js + Express API to manage books with user authentication (JWT-based), CRUD operations, filtering, pagination, and sorting.

🚀 Setup Instructions
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-username/bookstore-api.git
cd bookstore-api
2. Install Dependencies
bash
Copy
Edit
npm install
3. Create .env File
Create a .env file in the root directory and add the following:

env
Copy
Edit
PORT=5000
MONGO_URI=mongodb://localhost:27017/bookstore
JWT_SECRET=your_jwt_secret
4. Run the Server
bash
Copy
Edit
npm start
Server will run at: http://localhost:5000

📌 API Endpoints
All /books routes are protected and require a JWT token (use cookie or Authorization header).

✅ Auth Routes (/api/auth)
Method	Endpoint	Description
POST	/register	Register user
POST	/login	Login user
GET	/logout	Logout user
📌 Sample Request (Login)
json
Copy
Edit
POST /api/auth/login
{
  "email": "test@example.com",
  "password": "123456"
}
📚 Book Routes (/api/books)
Method	Endpoint	Description
POST	/	Create a new book
GET	/	Get all books
GET	/:id	Get book by ID
PUT	/:id	Update book by ID
DELETE	/:id	Delete book by ID
✅ Filtering, Pagination, and Sorting
http
Copy
Edit
GET /api/books?category=fiction&author=Rowling&rating=4&page=1&limit=5&sortBy=price&order=desc
🛡️ Protected Routes
All book routes require authentication. You must be logged in (JWT) to access them.

🔍 Sample Book Schema
json
Copy
Edit
{
  "title": "The Alchemist",
  "author": "Paulo Coelho",
  "category": "Fiction",
  "price": 10.99,
  "rating": 4.5,
  "publishedDate": "2023-04-01"
}
💡 Assumptions
JWT is stored in cookies or can be passed as Authorization: Bearer <token>.

A MongoDB instance is running locally or remotely.

Passwords are securely hashed using bcrypt.

🌟 Enhancements (Bonus Features)
🔒 Full JWT Auth with middleware

🧪 Input validation and error handling

📄 Pagination + Sorting by price or rating

🔍 Filtering and partial search by title
