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

 ---
## 2.Install dependencies
   ```bash
  npm install
```
  ---

 ---
##  3.Create a .env file

```bash

  PORT = 3000

```

  ---


  ---

 ## 4.Start the server

 


  for the Development :
  ```bash
  
   npm run dev
```


  for the production :
```bash
  npm start
```



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
 
```

***2.🧠 Controllers***

Handles the business logic for each route.

```bash
// controllers/userController.js


exports.getUsers = (req, res) => {
  res.json({ message: 'List of users' });
};

```

***3.🛡️ Middleware***

Used for things like authentication, logging, etc.

```bash
// middleware/authMiddleware.js


module.exports = (req, res, next) => {
  console.log('Authentication middleware');
  next();
};

```

***4.⚙️ App and Server Files***

***app.js***
```bash
const express = require('express');
const userRoutes = require('./routes/userRoutes');

const app = express();

app.use(express.json());
app.use('/api/users', userRoutes);

module.exports = app;

```


***server.js***

```bash
const app = require('./app');
const dotenv = require('dotenv');

dotenv.config();

const PORT = process.env.PORT || 5000;

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});

```



##📬 API Endpoints

```bash
| Method | Endpoint   | Description       |
| ------ | ---------- | ----------------- |
| GET    | /api/users | Get list of users |

```

##🧪 Testing

You can test the API using tools like Postman or cURL:

```bash
http://localhost:3000/api/users

```

##📄 License

This project is licensed under the MIT License.


---

Would you like me to also generate a sample `package.json` or `.env` file? Or help structure the repo as a downloadable template?


Are you an web developer or learning web development and came to know about Node.js and Express.js and you are confused “where to start ?“or “How to start the node.js project ?”, I got you.

I will guide you step-by-step, and will walk you through the process of setting up your first Node.js backend, including creating a clean folder structure, defining a server using server.js file, creating routes, and setting up a port.

The 5 key Steps :
Step 1: Setting Up the Project

Step 2: Folder Structure

Step 3: Creating server.js file

Step 4: Building Routes

Step 5: Run Your Backend

Step 1: Setting Up the Project
Install Node.js and npm: Before you start, ensure you have Node.js and npm (Node Package Manager) installed. You can download them from the official Node.js website.
Create a Project Directory: Create a dedicated folder for your Node.js project. You can use your computer’s file explorer or the command line to do this. For example, you can run the following command in your terminal:
mkdir my-node-project
cd my-node-project

This will create a new directory called “my-node-project” and navigate you into it.

3. Initialize Your Project: Inside your project directory, initialize a Node.js project by running the following command:

npm init
This command will guide you through creating a package.json file. This file contains project metadata and dependencies.

4. Answer the Prompts: The npm init command will ask you for information like the project name, version, description, entry point, and more. Fill in the details or press Enter to accept the default values.


5. Install Dependencies: Depending on your project requirements, you may need to install packages or dependencies. You can use the npm install command to add packages. For example:

npm install express

This installs the Express.js framework

6. Project Structure: Organize your project files and folders. A common structure includes:

server.js: This file serves as the entry point for your Node.js application.
routes/: Store route files here.
controllers/: Keep your route controllers in this folder.
models/: If your project involves a database, store database models here.
7. Version Control: It’s a good practice to set up version control for your project using a tool like Git. I like to Initialize a Git repository in my project folder:

git init .
Now, your Node.js project is set up and ready for development.

Step 2: Folder Structure
Organizing your project with a well-defined folder structure is essential for maintaining clarity and scalability in your Node.js and Express.js project. Here’s how to structure your project folders:


You can organize your project into subdirectories like:
controllers/: Store controller files that contain business logic and handle HTTP requests and responses.
models/: Keep database models here if your project involves a database. These models define how data is structured in your application.
middleware/: Place middleware functions, which are functions that can process requests before they reach route handlers.
routes/: Define route files to separate different API endpoints or web routes. This keeps your code modular and easy to maintain.
node_modules/: This folder is created when you install dependencies using npm. It contains all the packages and modules required for your project. You typically don't need to modify anything in this folder.
.git/ (if using Git): If you're using version control with Git, this folder stores Git's configuration and repository data. It helps you track changes and collaborate with others.
.env (Optional): Consider including a .env file to manage environment variables such as API keys and sensitive information. This file should be kept out of version control for security reasons.
package.json and package-lock.json: These files contain project metadata and dependencies. package.json is typically generated during the initialization of your project, and package-lock.json locks down the versions of your dependencies.
server.js (or app.js): This file serves as the entry point for your Node.js and Express application. It sets up the server and defines the server logic.
Static Assets (Optional): If your application serves static files like CSS, JavaScript, or images, you can create a directory for them (e.g., public/ or static/) to keep them separate from your application logic.
Dont worry about these folders or directories:
controllers/

middlewares/

models/

we will use these on upcoming articles.

This folder structure provides a clear separation of concerns, making it easier to work collaboratively, maintain, and scale your Node.js and Express project. It’s important to choose a structure that suits your project’s specific requirements and follow best practices in the Node.js and Express.js ecosystem.

Step 3: Creating server.js
Creating a server.js file is a crucial step in setting up your Node.js server. This file serves as the entry point for your Node.js application and defines the server's logic. Here's how you can create and structure your server.js file:

Get Ibrahim’s stories in your inbox
Join Medium for free to get updates from this writer.

Enter your email
Subscribe

Remember me for faster sign in

1. Import Necessary Modules: At the beginning of your server.js file, import the required Node.js modules. Common modules for creating a server include http or express, depending on your application’s complexity.

Lets first create and http server :

2. Set Up the Server: Next, create an HTTP server by calling the createServer method and passing a request/response callback function.

// fileName : server.js 
// Example using the http module
const http = require('http');

// Create an HTTP server
const server = http.createServer((req, res) => {
    // Set the response headers
    res.writeHead(200, { 'Content-Type': 'text/html' });

    // Write the response content
    res.write('<h1>Hello, Node.js HTTP Server!</h1>');
    res.end();
});

// Specify the port to listen on
const port = 3000;

// Start the server
server.listen(port, () => {
    console.log(`Node.js HTTP server is running on port ${port}`);
});

To run the Node.js HTTP server, execute it using node server.js. You can access the server at http://localhost:3000 in your web browser.



Now we will create server using Express.js, the setup would look slightly different:

// Example using Express.js
const express = require('express');
const app = express();
3. Define Routes (if using Express): Now we are finally using Express.js, now define routes and route handlers within your server.js file.

// Example defining a route in Express
app.get('/', (req, res) => {
    res.send('<h1>Hello, Express.js Server!</h1>');
});
4. Specify Port and Listen: Specify the port on which your server should listen and start the server.

// Example specifying the port and starting the server
const port = process.env.PORT || 3000; // You can use environment variables for port configuration
server.listen(port, () => {
    console.log(`Server is running on port ${port}`);
});

5. Handling Requests: In the request/response callback function, you can handle incoming HTTP requests and send responses accordingly. For more complex applications, you may use middleware, route handlers, and controllers to manage different aspects of your server’s functionality, which we will discuss in upcoming article.

By creating a well-structured server.js file, you establish the core logic of your Node.js server, enabling it to listen for incoming requests and respond appropriately.

Step 4: Building Routes
Creating routes is an essential part of setting up a Node.js backend. Routes define how your server responds to specific HTTP requests.

1. Organize Your Routes: Before creating routes, organize your project structure. Commonly, routes are organized in separate files or modules. For example, you can create a “routes” folder and organize routes based on functionality.

this is the complex web application routes structure:


2. Create Route Files: Inside the “routes” folder, create separate route files for different parts of your application. For instance, you can have files like “users.js” for user-related routes and “products.js” for product-related routes.


3. Import Dependencies: In each route file, import the necessary dependencies like Express and any other required modules.

4. Define Routes: Define your routes using Express. Here’s an example of defining a simple route that responds to a GET request:

// routes/users.js
const express = require('express');
const router = express.Router();

// Define a route
router.get('/', (req, res) => {
    res.send('this is user route');// this gets executed when user visit http://localhost:3000/user
});

router.get('/101', (req, res) => {
    res.send('this is user 101 route');// this gets executed when user visit http://localhost:3000/user/101
});

router.get('/102', (req, res) => {
    res.send('this is user 102 route');// this gets executed when user visit http://localhost:3000/user/102
});

// export the router module so that server.js file can use it
module.exports = router;

// routes/products.js
const express = require('express');
const router = express.Router();

// Define a route
router.get('/', (req, res) => {
    res.send('this is product route');// this gets executed when user visit http://localhost:3000/products
});

router.get('/101', (req, res) => {
    res.send('this is product 101 route');// this gets executed when user visit http://localhost:3000/product/101
});

router.get('/102', (req, res) => {
    res.send('this is product 102 route');// this gets executed when user visit http://localhost:3000/product/102
});

// export the router module so that server.js file can use it
module.exports = router;

5. Use Routes in Your Application: In your main server.js file, include and use these route files. This connects your routes to the application.

// server.js
const express = require('express');
const app = express();

// Include route files
const usersRoute = require('./routes/users');
const productsRoute = require('./routes/products');

// Use routes
app.use('/users', usersRoute);
app.use('products', productsRoute);
Press enter or click to view image in full size

6. Test Your Routes: After setting up routes, you can test them by running your server and sending HTTP requests to the defined routes using tools like Postman or by simply opening them in a web browser.








By following these steps, you can create organized and structured routes for your Node.js application. This allows you to handle different parts of your application’s functionality and respond to various client requests effectively.

Step 5: Run Your Backend
Once you’ve set up your Node.js backend and configured everything, it’s time to run your application. Here are the steps to run your backend:

Start Your Server: In your main application file (usually server.js), ensure you have included all the necessary routes. Then, start your server by listening on a specific port.
// run this command on the terminal or cmd inside project directory(folder) every time you make changes in code 
node server.js 
// you can also use nodemon, to avoid running "node server.js" every time you make changes in project code.
// to install nodemon, go to terminal and run : "npm install nodemon -G" to install globally in your host machine.

Test Your Application: Open a web browser or use tools like Postman to test your backend by sending HTTP requests to the defined routes. Verify that your server responds correctly.
Monitor and Debug: Keep an eye on the server logs and any error messages. This will help you identify and fix issues as they arise during development.
Deploy Your Application: Once you are satisfied with the local development and testing, you can deploy your backend to a hosting service or cloud platform to make it accessible on the internet.
Maintenance and Updates: Regularly maintain and update your backend as needed to ensure it runs smoothly and remains secure.
By following these steps, you can successfully run and maintain your Node.js backend, providing services to your applications and users.

If you reached up to this point, please consider following my account, I appreciate your response be sure to clap on this blog post by clicking on “clap 👏” icon below this blog post. This encourages me contribute more to people. Thank you for giving your valuable time😁.

1K


8








