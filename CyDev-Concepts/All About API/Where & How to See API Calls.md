## 👁️‍🗨️ **Where & How to See API Calls**

| **Tool**            | **How to Use It**                                                   | **What You Can See**                                                        |
|---------------------|----------------------------------------------------------------------|------------------------------------------------------------------------------|
| 🧪 **Browser DevTools (Network Tab)** | Press `F12` or `Ctrl+Shift+I` → Go to `Network` tab → Filter `XHR/fetch` or type `api` in filter. | All frontend HTTP requests: headers, methods, status, response. |
| 🐞 **Burp Suite (Proxy + HTTP History)** | Start **Burp**, set browser to use Burp’s proxy (usually `127.0.0.1:8080`) → Browse the site → Check `HTTP history`. | Full intercepted requests + raw data, even hidden headers, tokens, cookies. |
| 🧰 **Burp Suite (Repeater & Decoder)** | Right-click any request in HTTP history → `Send to Repeater`. Edit & re-send it to test APIs. | Replay, manipulate, fuzz API calls easily. |
| 🌐 **Browser Address Bar** (Limited)   | Some APIs like REST GETs show up right in the URL (`/api/product?id=123`) | Only good for very basic observation, not POSTs or payloads. |

---

## 💥 Real Scenarios & What to Look For

| **Page/Action** | **Where to Look in Browser DevTools** | **What API Calls to Expect**                      |
|-----------------|----------------------------------------|---------------------------------------------------|
| 🏠 Home page     | `XHR` tab, first few requests         | `/api/homepage`, `/api/featured`, `/api/banner`   |
| 🔍 Search bar    | Type something → check `XHR`          | `/api/search?q=...` (Stateless GET or POST)       |
| 👤 Login form    | Submit → `XHR` tab                    | `POST /api/login` (with credentials payload)       |
| 🛒 Add to cart   | Click Add → `XHR` tab                 | `POST /api/cart/add` or `PUT /api/cart/{id}`       |
| 💳 Checkout      | `XHR` or `Fetch`                      | `/api/checkout`, `/api/payment/initiate` (Stateful) |
| 💬 Chat pop-up   | Might use WebSocket → `WS` tab        | Check persistent socket to `/chat/ws/...`         |
| 📡 Webhook       | Not in browser — only Burp can log it if you're mocking the endpoint | `POST` from 3rd-party service                     |

---

## 🔓 Bonus: Burp Suite Extensions for API Testing

| **Extension**        | **What It Helps With**                          |
|----------------------|--------------------------------------------------|
| `JWT Editor`         | Decode & tamper JWT tokens easily               |
| `Autorize`           | Detect broken access controls (IDORs etc.)      |
| `Hackvertor`         | Encode/decode tricky payloads (JWT, base64, etc)|
| `Logger++`           | Enhanced logging beyond HTTP history            |
| `Turbo Intruder`     | Fuzz APIs at lightning speed                    |

---
