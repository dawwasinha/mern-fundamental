# MERN FUNDAMENTAL#1

## Overview

This project consists of two main components:

1. **Frontend**: A React application for the user interface.
2. **Backend**: A Node.js and Express application for handling server-side logic and interacting with a database.

---

## Project Structure

---

## Setup Instructions

### 1. Create the Project Folder
Run the following commands in your terminal to set up the project structure:
```bash
mkdir mern-fundamental
cd mern-fundamental
npx create-react-app client

### 2. Create the React Project (Client)
npx create-react-app client

### 3. Create the Node/Express Project (Server)
mkdir server
cd server
npm init -y

---

## Backend Setup (Server)

### 1. Install Express
cd server
npm install express

### 2. Create the index.js File
Create a file named index.js in the server folder and add the following code:

const express = require('express');
const app = express();
const cors = require('cors');

app.use(cors());

app.get('/', (req, res) => {
  res.send('Hello from our server!');
});

app.listen(8080, () => {
  console.log('server listening on port 8080');
});

### 3. Start the Server
Run the following command in the server directory:

bash
Copy code
node index.js

---

## Frontend Setup (Client)

### 1. Install Axios
In the client directory, run:

bash
Copy code
npm install axios

### 2. Update the App.js File
Replace the default content of App.js with:

import axios from 'axios';
import './App.css';

const apiCall = () => {
  axios.get('http://localhost:8080').then((data) => {
    console.log(data);
  });
};

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <button onClick={apiCall}>Make API Call</button>
      </header>
    </div>
  );
}

export default App;

### 3. Start the React App
Run the following command in the client directory:

npm start

---

## CORS Configuration
To avoid CORS errors, we use the cors package in our backend. Install it by running:

cd server
npm install cors

Update the index.js file to include:

const cors = require('cors');
app.use(cors());

---

## Testing the Application
Start the server:

cd server
node index.js
Start the React app:

cd client
npm start

Open the React app in your browser, click the Make API Call button, and check the console for the response from the server.













