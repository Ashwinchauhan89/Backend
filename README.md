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
