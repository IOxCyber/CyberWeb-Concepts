# GET: `Used to Fetch a file or webpage`
- Once the file is uploaded the Get request will fetch the files & server. `eg: GET /path/to/file`
- GET requests should not have side effects; they should `only retrieve data`. This is why file uploads or any action that changes the state of the server should not be done with GET requests.
```
GET /files/report.pdf HTTP/1.1
Host: example.com
```

# POST: `Used to send data to the server to create/update a resource via a form submission.`
- An attacker can upload a suspicious file using the POST method. `eg: POST/upload`
- POST requests are `designed to send data to the server`, which can include files, form data, or any other content that needs to be processed by the server.
```
POST /upload HTTP/1.1
Host: example.com
Content-Type: multipart/form-data; boundary=---------------------------974767299852498929531610575

-----------------------------974767299852498929531610575
Content-Disposition: form-data; name="file"; filename="malicious.php"
Content-Type: application/x-php

<?php echo 'This is a malicious script.'; ?>
-----------------------------974767299852498929531610575--
```
