## API [In-Depth](https://www.govtech.com/archive/whats-an-api-and-why-do-you-need-one.html)
- Application Programming Interface. [more](https://aws.amazon.com/what-is/api/)
- mechanisms that enable two software components to communicate with each other using a set of definitions and protocols.
- API takes `request` from client/App[^1] <--> Interact with Server[^1] & process the `Response` -> return to Client/App.
- <img width="500" alt="image" src="https://github.com/cybersome/CyberDev/assets/40174034/260695df-5067-44d9-ab2f-6cb3363e7e5e">
- Real Life Case: 
  1. Flight booking websites (uses API’s provided by airlines and hotel)
  2. Users can create an account through Google with just one tap. (Apps uses the Google API to verify the user’s identity)
  3. The weather app on your phone “interact” to this system via APIs and shows you daily weather updates on your phone.

## Types:
- RPC[^2] (client completes a function on the server, and the server sends the output back to the client.)
- SOAP (Client and server exchange messages using XML)
- Websocket[^3] (JSON objects to pass data, supports two-way communication)
- REST (The server uses this client input/Data to start internal functions and returns output data back to the client)

## REST API:
- Representational State Transfer.
- Clients and servers exchange data using HTTP methods.
- REST API is `statelessness`. Statelessness means that `servers do not save client data between requests`


## HTTP Methods:
- REST defines a set of functions like `GET, PUT, DELETE` etc. that clients can use to access server data.
- The most-commonly-used HTTP methods are `POST, GET, PUT, and DELETE`[more](https://medium.com/@9cv9official/what-are-get-post-put-patch-delete-a-walkthrough-with-javascripts-fetch-api-17be31755d28) which correspond to `create, read, update, and delete (or CRUD) operations.`


## API integrations:
- automatically update data between clients and servers.
1. automatic data sync to the cloud from your phone image gallery.
2. the time and date automatically sync on your laptop when you travel to another time zone.

## API Security:
- Authentication tokens, API keys.



[^1]:The application sending the request is called the client, and the application sending the response is called the server. 
[^2]:This is a less flexible API that was more popular in the past.
[^3]:Websocket API is another modern web API development that uses JSON objects to pass data. A WebSocket API supports two-way communication between client apps and the server.
