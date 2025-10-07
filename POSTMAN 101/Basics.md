---

# API Request Essentials in Postman:

## 1. API Request

- An **API Request** is built to communicate with a server for various operations like fetching, creating, updating, or deleting data.

### Structure of an API Request:

`HTTP Method + API_Server_URL + API_Endpoint + (Params / Body) + Headers + Authentication`

### Notes:
- **GET Request:** Use **Params** to send data.  
- **POST Request:** Use **Body** to send data.

| Component | Purpose | Example |
|------------|----------|----------|
| **HTTP Method** | Defines the action to perform | `GET`, `POST`, `PUT`, `DELETE` |
| **API Server URL** | The base server address | `https://api.example.com` |
| **API Endpoint** | Specific path of the resource | `/users`, `/login` |
| **Params / Body** | Data sent to the server | `?id=10` (Params) or `{ "name": "John" }` (Body) |
| **Headers** | Define metadata like content type or auth | `Content-Type: application/json` |
| **Authentication** | Secures API access | API Key, OAuth, Bearer Token |

---

## 2. Collection

- A **Collection** is a group of saved API requests organized into folders.

| Purpose | Use Case | Example |
|----------|-----------|----------|
| Group related requests | Easier management & testing | Login, Create User, Fetch User Details in one collection |

---

## 3. Variables

- **Variables** store reusable values to avoid repetition across multiple requests.

| Type | Description | Example |
|------|--------------|----------|
| **Global Variable** | Available in all requests/environments | `{{base_url}}` |
| **Collection Variable** | Specific to a collection | `{{user_id}}` |
| **Environment Variable** | Specific to an environment | `{{auth_token}}` |

> Variables are referenced using double curly braces — e.g., `{{server_url}}`.

---

## 4. Environment

- An **Environment** is a set of key-value pairs (variables) used for different contexts like **Dev**, **Staging**, or **Production**.

| Value Type | Description | Shared with Postman Server? |
|-------------|--------------|------------------------------|
| **Initial Value** | Used for sharing or team sync. Avoid storing sensitive info. | ✅ Yes |
| **Current Value** | Used locally. Not shared with others. | ❌ No |

### 🔧 How to Create a New Environment:
1. Click **New → Environment**  
2. Or click the **⚙️ (Settings Icon)** in the top-right corner  
3. Add variables with their **Initial** and **Current** values  
4. Select the environment before sending requests  

---

### ✅ Summary:

- **API Request** = Command to interact with a server.  
- **Collection** = Folder containing related API requests.  
- **Variable** = Placeholder for reusable values.  
- **Environment** = Context setup (e.g., Dev, Test, Prod).  

---

### Real-Life Use Case
When testing an e-commerce API:
- **Collection:** Contains endpoints like `/login`, `/products`, `/checkout`.  
- **Environment:** `Development`, `Staging`, and `Production` each have unique URLs and tokens.  
- **Variables:** Store `{{base_url}}`, `{{token}}`, and `{{user_id}}` for quick reuse.  

**Examples:** Used in Postman, Insomnia, Hoppscotch, and SwaggerHub.

---
