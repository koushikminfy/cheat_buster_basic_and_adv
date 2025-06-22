# Basic cheat Buster App 

```markdown


## Folder Structure

cheat-buster-app/
├── controllers/
│   └── user.controller.js
├── models/
│   └── user.model.js
├── routes/
│   └── user.routes.js
├── public/
│   ├── index.html
│   ├── style.css
│   └── script.js
├── .env
├── index.js
├── seed.js
├── .gitignore

```

---


### 1. Initialize Bun project
```bash
bun init
````

### 2️ Install dependencies

```bash
bun add express mongoose zod axios dotenv
```

---

##  Environment Configuration

Create a `.env` file in the root:

```env
MONGO_URI=your_mongodb_connection_string{i need to replace with mongo db server with my oassword}
PORT=3000
```


---
##  Backend Overview

###  Model — `models/user.model.js`

Defines the Mongoose schema for the user collection.

###  Controller — `controllers/user.controller.js`

Handles validation and logic for searching users.

###  Routes — `routes/user.routes.js`

API endpoint:

###  Main Server — `index.js`

Initializes Express server and connects to MongoDB.

---
##  Seed the Database

Add mock user data for testing:

```bash
bun seed.js
```

---



## 🔁 Frontend–Backend Integration

| What Happens                         | File                       |
| ------------------------------------ | -------------------------- |
| User enters email                    | `index.html` + `script.js` |
| JS sends GET `/api/search?email=...` | `script.js`                |
| Express handles the request          | `user.routes.js`           |
| Controller validates & queries DB    | `user.controller.js`       |
| MongoDB returns user if found        | `user.model.js`            |
| Result shown on webpage              | DOM updated via JS         |

---

## 📸 Screenshots
![Terminal](https://github.com/user-attachments/assets/e738d960-d13b-4126-afc5-689095365a29)
![Home](https://github.com/user-attachments/assets/657f0f74-7e49-4746-bce6-6ee626b933c6)

---








#  Medium Cheat Buster App 
## Overview
  three features:
1. **Search by Name** - Users can search by first or last name
2. **Better Loading State** - Buttons show "Searching..." and are disabled during requests
3. **API Service Refactor** - Clean separation of API calls in a dedicated service

## Project Structure
```
project-root/
├── controllers/
│   └── user.controller.js     # Enhanced with name search
├── models/
│   └── user.model.js          # User schema
├── routes/
│   └── user.routes.js         # API routes
├── public/
│   ├── index.html             # Enhanced UI with dual search
│   ├── script.js              # Main frontend logic
│   └── api.js                 # API service layer
├── index.js                   # Main server file
├── seed.js                    # Database seeding
├── package.json
├── jsconfig.json
└── .env                       # Environment variables
```

## Setup Instructions

### 1. Install Dependencies
```bash
bun install
```
![image](https://github.com/user-attachments/assets/b57a0a4c-1a72-4357-b902-c82a8935b70d)

### 2. Set up Environment Variables
Create a `.env` file in the root directory:
```env
MONGO_URI=mongodb://localhost:27017/cheat-buster-app{here i will give my mongo server url}
PORT=3000
NODE_ENV=development
```

### 3. Seed the Database
```bash
bun run seed.js
```
![image](https://github.com/user-attachments/assets/c62b75c0-8836-45f5-9785-3819c91cc31b)

### 4. Start the Server
```bash
bun run index.js
```
![image](https://github.com/user-attachments/assets/141996ca-46e7-4f9b-b7b1-0e12e125a545)

![image](https://github.com/user-attachments/assets/bba968c6-e419-4604-9006-5f7e9c7e87a2)
![image](https://github.com/user-attachments/assets/9a8ae68d-756b-4387-8462-5b0fac505328)
![image](https://github.com/user-attachments/assets/9990bb6a-b80b-4564-ae28-78914849cf61)




### Search User
```
GET /api/users/search?email=user@example.com
GET /api/users/search?name=John
```

