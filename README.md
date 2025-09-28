# Lab 2 - Cookie Session Authentication

This repository is part of **LAB 6 - Security in NodeJS**.  
It demonstrates **authentication using session and cookies** with MongoDB.

---

## How to Run
1. Install dependencies:
   ```bash
   npm install
   ```
2. Start the server:
   ```bash
   node app.js
   ```
3. Server will run at:
   ```
   http://localhost:3000
   ```

---

## API Endpoints
### Register
- **POST** `http://localhost:3000/auth/register`
- Body:
  ```json
  { "username": "koanh", "password": "22632471" }
  ```

### Login
- **POST** `http://localhost:3000/auth/login`
- Body:
  ```json
  { "username": "koanh", "password": "22632471" }
  ```

### Profile
- **GET** `http://localhost:3000/auth/profile`  
- Requires valid session cookie.

### Logout
- **GET** `http://localhost:3000/auth/logout`  
- Destroys session and clears cookie.

---

## Testing with Postman
1. Register → check MongoDB `users` collection.  
2. Login → cookie `connect.sid` created.  
3. Profile → accessible only if logged in.  
4. Logout → cookie/session deleted → profile no longer accessible.

---

## Check in MongoDB Compass
- Database: `sessionAuth`  
- Collection `users` → stores registered users.  
- Collection `sessions` → stores login sessions.  
- After logout, cookie is invalid → Compass will eventually auto-remove expired sessions.

---


