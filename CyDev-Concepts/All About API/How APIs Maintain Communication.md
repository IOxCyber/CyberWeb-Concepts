## 🔐 How Do APIs Maintain Communication?

---

### ✅ **Stateful API**
Server remembers the client’s "state".

This is usually done via:

| **Mechanism** | **How it works** |
|---------------|------------------|
| `Session ID`  | Stored on the server (in memory or DB) and referenced using a `session cookie` on the client. |
| `Cookies`     | Sent automatically with each request by the browser. |

So in stateful APIs, once you're logged in, the server uses your `session_id` to "know you" on future requests.

**Example Flow:**
```http
1. POST /login  → Server authenticates and sets: Set-Cookie: session_id=abc123  
2. GET /dashboard → Browser sends Cookie: session_id=abc123  
3. Server looks up the session and responds accordingly.
```

✔️ No need to authenticate every request — the server **remembers** the client.

---

### ✅ **Stateless API**
Server does **not** store anything about the client.

Each request must carry **all necessary info** to verify and respond.

Common ways to maintain communication:

| **Mechanism**   | **How it works** |
|-----------------|------------------|
| `Bearer Token`  | Typically a JWT (JSON Web Token), sent in `Authorization` header. |
| `API Key`       | Sent in headers or query params. Static but less secure. |

The token contains everything the server needs to verify the user. **No lookup needed**.

**Example Flow:**
```http
GET /profile  
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI...
```

✔️ **YES** — in stateless, the user’s browser **must send the token with every request**.

---
