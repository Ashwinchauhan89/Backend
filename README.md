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


## 2.Install dependencies

---
   
  npm install
  ---


##  3.Create a .env file

  PORT = 3000


 ## 4.Start the server
   ---

  for the Development :
  
   npm run dev


  for the production :

  npm start
   



<br>

---

##🧱 Folder Explanation
***1. 🛣️ Routes***

Defines all the API endpoints and connects them to controllers.

```bash
// routes/userRoutes.js
const express = require('express');
const { getUsers } = require('../controllers/userController');
const router = express.Router();

router.get('/', getUsers);

module.exports = router; 
 ---

