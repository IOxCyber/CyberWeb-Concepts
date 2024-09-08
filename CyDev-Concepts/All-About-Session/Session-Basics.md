## 1. Session:
A session is a `temporary, interactive information exchange between two entities` (usually a user and a web application) that is maintained across multiple requests. 
It is established when a user logs into a system or accesses a service and ends when the user logs out, or the session expires.

## Purpose:
`Track a user’s state and actions` across multiple interactions with a web application (e.g., login status, shopping cart).
Sessions provide a way for web applications to store user data across different HTTP requests, which are stateless by default.

## 2. Session ID:
A Session ID is a `unique identifier` that is assigned to each session to distinguish different users and their interactions with the web application. 
The `Session ID is usually stored in cookies, URL parameters, or HTTP headers.`

## Purpose: 
It acts as a key for retrieving session-related information (like login state, preferences, etc.) from the server.

## 3. How it works:
A user logs in, and the server generates a Session ID.
The Session ID is sent to the user's browser (usually stored in cookies).
For subsequent requests, the browser sends the Session ID to the server to maintain the user’s state.
