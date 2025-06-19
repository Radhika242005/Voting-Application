SECURE VOTING WEB APPLICATION
=============================


A full-stack secure voting platform built with Node.js, Express.js, EJS, and MySQL, designed for use in environments such as classroom elections. It includes user authentication, admin controls, voting statistics, and a strong focus on security best practices.


PROJECT STRUCTURE
-----------------
.
├── app.js               - Main Express server file
├── db.js                - MySQL connection setup
├── bcrypt.js            - Script to test password hashing
├── .env                 - Stores environment variables securely
├── src
│   ├── routes
│   │   ├── admin.js     - Admin-specific routes
│   │   ├── login.js     - Login and session management
│   │   ├── stats.js     - Voting stats and reports
│   │   └── voter.js     - Voter-facing routes
│   └── views
│       ├── admin.ejs
│       ├── login.ejs
│       ├── stats.ejs
│       └── voter.ejs
├── public               - (optional) Static assets like CSS/images


SECURITY FEATURES
-----------------
- Environment Variables (.env): Stores DB credentials and secrets securely.
- Helmet: Sets secure HTTP headers to reduce vulnerabilities.
- Express-session: Manages session state with secret stored in .env.
- Bcryptjs: Secure password hashing and validation.
- Static File Restriction: Prevents direct access to internal files.
- Modular Routing: Ensures maintainable, RBAC-ready structure.
- Error Handling Middleware: Prevents leaking of stack traces to clients.


ENVIRONMENT VARIABLES (.env)
----------------------------
Create a .env file in the root directory and add your credentials:


DB_HOST=localhost
DB_USER=root
DB_PASSWORD=Radhika@2005
DB_NAME=voting_system
SESSION_SECRET=sanj@3134


In app.js, load environment variables using:
require('dotenv').config();


GETTING STARTED
---------------
1. Clone the Repository:
   git clone https://github.com/your-username/secure-voting-app.git
   cd secure-voting-app


2. Install Dependencies:
   npm install
   npm install helmet
   


4. Set Up MySQL Database:
   CREATE DATABASE voting_system;


   CREATE TABLE users (
     id INT PRIMARY KEY AUTO_INCREMENT,
     username VARCHAR(255) UNIQUE,
     password VARCHAR(255)
   );


5. Run the App:
   nodemon app.js
   or
   node app.js


   Then open: http://localhost:3000


TESTING PASSWORD HASHING
-------------------------
To test password hashing using bcrypt:
   node bcrypt.js


FUTURE IMPROVEMENTS
-------------------
- Add input validation with express-validator
- Implement rate limiting using express-rate-limit
- Enable CSRF protection using csurf
- Add admin dashboard UI for viewing voter statistics
- Audit login attempts and session expiry
