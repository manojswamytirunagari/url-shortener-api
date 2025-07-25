# Mini URL Shortener API

This is a simple and beginner-friendly URL shortener built with Node.js, Express, and MongoDB.  
It allows users to shorten long URLs, optionally set an expiration date, and get redirected using the shortened link.

---

## Features

- Shortens long URLs
- Allows optional expiration dates for each short URL
- Redirects users from short URLs to the original long URLs
- Tracks how many times a short URL has been visited

---

## Project Structure

url-shortener-api/
│
├── public/                - HTML page to submit long URLs
├── src/
│   ├── index.js           - Main Express server
│   ├── models/
│   │   └── Url.js         - Mongoose schema for URL data
│   └── routes/
│       └── urlRoutes.js   - All backend API routes
├── .env                   - Your MongoDB URI and base URL (not pushed to Git)
├── .gitignore             - Prevents uploading sensitive files like node_modules and .env
├── package.json           - Project metadata and dependencies
└── README.md              - This file

---

## How to Run This Project

### Step 1: Clone the Repository

If you are using Git:

git clone https://github.com/your-username/url-shortener-api.git
cd url-shortener-api

yaml
Copy
Edit

Or download and unzip the project folder manually.

---

### Step 2: Install Node.js

Make sure Node.js and npm are installed.  
You can check with:

node -v
npm -v

yaml
Copy
Edit

If not installed, go to: https://nodejs.org/

---

### Step 3: Install Dependencies

Inside the project folder, run:

npm install

yaml
Copy
Edit

---

### Step 4: Create a .env File

Create a file named `.env` in the root folder and add your MongoDB connection string like this:

PORT=5000
MONGO_URI=your-mongodb-atlas-uri
BASE_URL=http://localhost:5000

yaml
Copy
Edit

Replace `your-mongodb-atlas-uri` with your actual connection string from MongoDB Atlas.

---

### Step 5: Start the Server

Start the backend using:

npm run dev

yaml
Copy
Edit

You should see:

Server running on http://localhost:5000
MongoDB connected

yaml
Copy
Edit

---

## How to Use the API

You can test using:

- A browser (for redirection)
- PowerShell or terminal
- Postman

### To Shorten a URL

Use this PowerShell command:

Invoke-RestMethod -Uri "http://localhost:5000/shorten" -Method POST
-Body '{"url":"https://example.com"}' `
-ContentType "application/json"

css
Copy
Edit

You will receive a response like:

{
"shortUrl": "http://localhost:5000/abc123"
}

yaml
Copy
Edit

---

### To Visit a Short URL

Open this in your browser:

http://localhost:5000/abc123

yaml
Copy
Edit

It will redirect you to the original long URL.

---

## Deployment

You can host this project on platforms like Render, Vercel, or Railway.  
Make sure to set the environment variables (`MONGO_URI`, `PORT`, `BASE_URL`) in the hosting platform's dashboard.  
You can leave out `.env` and `node_modules` from Git using `.gitignore`.

---

## Author

Created by Manoj Swamy Tirunagari  
For demo, visit: https://url-shortener-api-8uyy.onrender.com