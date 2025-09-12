# 🛠️ Backend API - Node.js & Express

This is a simple backend REST API built using **Node.js** and **Express.js**, with a clean architecture that separates **Routes**, **Controllers**, and **Middleware**.

---

## 📁 Project Structure  <br>
<pre>
backend/  <br>
│                   <br>
├── controllers/              # Route handler logic   <br>
│ └── userController.js    <br>
│                                <br>
├── middleware/              # Custom middleware (e.g., auth, logger)  <br>
│ └── authMiddleware.js  <br>
│                            <br>
├── routes/                 # Route definitions  <br>
│ └── userRoutes.js   <br>
│                      <br>
├── app.js                 # Express app configuration                          <br>
├── server.js              # Entry point to start the server                <br>
├── .env                   # Environment variables                              <br>
└── package.json          # Project metadata and dependencies              <br>

</pre>



---

## 🚀 Technologies Used

- **Node.js** – JavaScript runtime
- **Express.js** – Web framework
- **Dotenv** – Manage environment variables
- **Nodemon** *(dev)* – Auto-restarts server during development

---

## 📦 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd backend

<pre>
  2.Install dependencies
   
  npm install


  3.Create a .env file

  PORT = 3000


  4.Start the server

  for the Development :
  
   npm run dev


  for the production :

  npm start


</pre>
<br>


🧱 Folder Explanation
1. 🛣️ Routes

Defines all the API endpoints and connects them to controllers.

// routes/userRoutes.js
const express = require('express');
const { getUsers } = require('../controllers/userController');
const router = express.Router();

router.get('/', getUsers);

module.exports = router;

2. 🧠 Controllers

Handles the business logic for each route.

// controllers/userController.js
exports.getUsers = (req, res) => {
  res.json({ message: 'List of users' });
};

3. 🛡️ Middleware

Used for things like authentication, logging, etc.

// middleware/authMiddleware.js
module.exports = (req, res, next) => {
  console.log('Authentication middleware');
  next();
};

4. ⚙️ App and Server Files
app.js
const express = require('express');
const userRoutes = require('./routes/userRoutes');

const app = express();

app.use(express.json());
app.use('/api/users', userRoutes);

module.exports = app;

server.js
const app = require('./app');
const dotenv = require('dotenv');

dotenv.config();

const PORT = process.env.PORT || 5000;

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});

📬 API Endpoints
Method	Endpoint	Description
GET	/api/users	Get list of users
🧪 Testing

You can test the API using tools like Postman or cURL:

curl http://localhost:5000/api/users

📄 License

This project is licensed under the MIT License.


---

Would you like me to also generate a sample `package.json` or `.env` file? Or help structure the repo as a downloadable template?

