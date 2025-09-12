# 🛠️ Backend API - Node.js & Express

This is a simple backend REST API built using **Node.js** and **Express.js**, with a clean architecture that separates **Routes**, **Controllers**, and **Middleware**.

---

## 📁 Project Structure  <br>

backend/  <br>
│
├── controllers/ # Route handler logic
│ └── userController.js    <br>
│
├── middleware/ # Custom middleware (e.g., auth, logger)
│ └── authMiddleware.js
│
├── routes/ # Route definitions
│ └── userRoutes.js
│
├── app.js # Express app configuration
├── server.js # Entry point to start the server
├── .env # Environment variables
└── package.json # Project metadata and dependencies
