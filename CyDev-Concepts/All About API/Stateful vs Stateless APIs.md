## 🔄 What: Stateful vs Stateless APIs

| Term        | Meaning                                                                 |
|-------------|-------------------------------------------------------------------------|
| `Stateless` | Every request is independent. Server **doesn’t remember** past requests.|
| `Stateful`  | Server **remembers client data** across multiple requests.              |

---

## ❓ Why It Matters

| Term        | Why Use It                                                             |
|-------------|------------------------------------------------------------------------|
| `Stateless` | Easier to scale, more secure (no stored session), RESTful compliant.   |
| `Stateful`  | Needed when **session continuity** is required (e.g., user login state).|

---

### ✅ Stateless API (REST is stateless by design)
```http
GET /api/user/profile
Authorization: Bearer <token>
```
- 🔸 Client includes **all necessary info** (like tokens) with **every** request.
- 🔹 Server doesn’t track prior requests. It just verifies the token and responds.

### ✅ Stateful API (like traditional web sessions or WebSocket connections)
```http
POST /login
Cookie: session_id=abc123
```
- 🔸 Client logs in once, gets a `session_id`.
- 🔹 All future requests rely on that server-side session.
- 🔻 If the server restarts or loses session, the user may need to log in again.

---

## 🛠 Real-World Implementations

| API Type       | Usually Stateless? | Example Services                                   |
|----------------|--------------------|----------------------------------------------------|
| REST API       | ✅ Yes              | Twitter, GitHub, Stripe                            |
| GraphQL        | ✅ Mostly           | Shopify, GitHub v4                                 |
| WebSocket API  | ❌ No               | Slack (chat continuity), Binance (live feeds)      |
| SOAP           | ❌ Often Stateful   | Older enterprise platforms (ERP, CRM)              |

---

## 💡 In Summary — Easy Points to Remember

1. **Stateless** means the **server treats each request as new**, which makes things fast, scalable, and robust (like REST).
2. **Stateful** means the server **tracks client data** across multiple calls (like user login sessions).
3. Stateless is ideal for **cloud-native apps**, CI/CD, and load balancing.
4. Stateful APIs are useful when **context matters**, like real-time games, chat, or financial transactions.

---

> TL;DR: Stateless is "talk-and-go", Stateful is "let’s stay on the line".
