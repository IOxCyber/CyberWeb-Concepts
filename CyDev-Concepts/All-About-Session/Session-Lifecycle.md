## Lifecycle of a Session ID (Simple Flow)

### 1. **Session Creation**

- When a user visits the web application (e.g., logging in or adding items to a cart), the server generates a unique **Session ID** and sends it to the browser.

##### **Example Code (Node.js / Express)**:
```javascript
// Express example: Generating and assigning a session ID
const express = require('express');
const session = require('express-session');
const app = express();

// Middleware to handle sessions
app.use(session({
  secret: 'yourSecretKey',
  resave: false,
  saveUninitialized: true,
  cookie: { secure: true }
}));

app.get('/login', (req, res) => {
  // When user logs in, a new session ID is created and stored
  req.session.userID = 'user123'; // Save user data to session
  res.send('Session Created. Session ID: ' + req.sessionID); // Send Session ID
});

app.listen(3000, () => console.log('Server is running on port 3000'));
```

**Flow**:
- User visits the site and logs in.
- The server creates a session and assigns a unique **Session ID** (e.g., `abc123xyz`).
- The **Session ID** is stored on the client side (typically as a cookie).

---

### 2. **Session In Use**

- As the user navigates the site, the **Session ID** is included in every request sent by the browser. The server uses this **Session ID** to fetch the corresponding session data.

##### **Example Code (Sending Session ID in Requests)**:
```javascript
// Client-side: Automatically send session cookies with each request
fetch('/user/dashboard', {
  method: 'GET',
  credentials: 'include' // Ensures cookies (Session ID) are sent with request
})
.then(response => response.json())
.then(data => console.log(data));
```

**Flow**:
- Every request from the user to the server sends the **Session ID**.
- The server uses this **Session ID** to retrieve the session data (e.g., logged-in status, cart contents, etc.).

---

### 3. **Session Expiration/Termination**

- After a period of inactivity (e.g., 30 minutes), or when the user logs out, the session is terminated. The **Session ID** is invalidated, and the server clears the session data.

##### **Example Code (Session Expiration)**:
```javascript
// Setting a session timeout (e.g., 30 minutes of inactivity)
app.use(session({
  secret: 'yourSecretKey',
  cookie: { maxAge: 1800000 } // 30 minutes in milliseconds
}));

// Logging out and destroying the session
app.get('/logout', (req, res) => {
  req.session.destroy(err => {
    if (err) {
      return res.send('Error terminating session');
    }
    res.clearCookie('connect.sid'); // Clear session cookie
    res.send('Session terminated');
  });
});
```

**Flow**:
- The session expires after a predefined timeout or when the user logs out.
- The server invalidates the **Session ID**, and the session data is cleared.

---

### 4. **New Session**

- When the user logs in again or initiates a new action that requires session management, the server generates a new **Session ID** and the cycle begins again.

##### **Example Code (New Session Creation)**:
```javascript
// When user logs in again, a new session and Session ID is created
app.get('/login', (req, res) => {
  req.session.regenerate(err => {
    if (err) return res.send('Session regeneration error');
    req.session.userID = 'newUser123';
    res.send('New Session Created. New Session ID: ' + req.sessionID);
  });
});
```

**Flow**:
- The user logs in again, and the server generates a new **Session ID** (e.g., `xyz789abc`).
- The session management cycle starts over.

---

### Summary of the **Session ID Lifecycle**:

1. **Session Creation**: The server generates a unique Session ID when a user logs in or interacts with the application. This Session ID is sent to the browser as a cookie.
   
2. **Session In Use**: As the user navigates the site, the browser sends the Session ID with each request. The server uses this Session ID to retrieve session-related data.

3. **Session Expiration/Termination**: The session is terminated after a period of inactivity or when the user logs out. The Session ID becomes invalid, and the server clears the session data.

4. **New Session**: When the user logs in again, a new Session ID is generated, and the process starts over.

---
