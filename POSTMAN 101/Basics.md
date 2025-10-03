- To build API request for various activities.
- An API request consists of...
Http Method + API_Server_URL+API_Endpoint + Params (in case of GET request), Headers, AUTHENTICATION 

> NOTE: In case of GET request (use Params) & for POST request (use Body)

2. Collection:
- A group of saved requests, can be organised as folders.

3. Variables:
- A simple value that can be defined and use repeatedly.
- Can be defined globally, in a collection or in an environment as `{{Variables}}`
- eg. {{server_url}}

4. Environment:
- Key-Value pair of variables in Postman.
- Contains 2 values: Initial, Current Value
- `Initial Value is Shared` when a collection is shared. `Never defined sensitive info as Initial Value`.
- `Current Value` is local & doesn't shared with Postman server.
### To create a new Environment:
- New > Environment or ⚙️ Icon