## [How Web Works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)

## 1. Overview:
- `Computers connected to the internet are called clients(user's internet-connected devices) and servers(computers that store webpages, sites, or apps)`
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/c53e1920-a443-427c-976d-14b6e5b0d5be">
- eg. imagine that the web is a road. On one end of the road is the client, which is like your School. On the other end of the road is the server, which is a Library.

## 2. Other Terms:
- `Internet connection`: Allows you to send and receive data on the web eg. The Road/Street.
- `TCP/IP`: Transmission Control Protocol and Internet Protocol eg. Transport mechanism.
- `DNS (Domain Name System)`: an address book to lookup website's IP address. eg. looking up the address of the Library.
- `HTTP: Hypertext Transfer Protocol`: defines a language for clients and servers to speak to each other. eg. language you use to order the books.
- `Component files`: eg. Different books for a subject.
    - `Code files: HTML, CSS, and JavaScript.`
    - `Assets`: Collective name for all the other stuff that makes up a website, such as `images, music, video, Word documents, and PDFs.`

## 3. What Exactly It happens within a Browser:
- Step by Step:
  1. The browser `connects to the DNS server, and finds the IP` address of the web server.
  2. The browser `sends an HTTP request message to the server`, asking it to send a copy of the website to the client.
  3. If the `server approves the client's request`, the server sends the client a "200 OK" message(which means the browser can get a copy of the website) & starts sending the website's files to the browser as a series of small chunks called `data packets`.
  4. The `browser assembles the small chunks into a complete web page and displays it.`


## 4. Parsing of Data by Browser:
- The `browser parses the HTML file first (any <link> or <script>)`
- Then, It `sends requests back to the server for any CSS files & JavaScript files` it has found, then parses the CSS and JavaScript.
- The browser `generates an in-memory DOM tree` from the parsed HTML, `generates an in-memory CSSOM structure from the parsed CSS`, and compiles and executes the parsed JavaScript.
- As the browser builds the DOM tree and applies the styles from the CSSOM tree and executes the JavaScript, a visual representation of the page is painted to the screen i.e Rendering happened.



## Other Info: 
1. The DOM(Document Object Model):
- Represents the structured representation (as a tree) of an HTML document within the browser's memory.
- creates a hierarchical tree-like structure consisting of nodes that represent each element, attribute, and text within the HTML document.
- Used for  
     - Manipulation and Modification (JavaScript can use the DOM to `dynamically modify the web page's structure, content, and styling`)
     - Rendering (process of `transforming HTML, CSS, and other resources into a visual representation` that users can see and interact with on their web browsers.)
     - JS Event Handling (process of `detecting and responding to specific actions` or events that occur within a web page or web application by the User Interaction)

2. CSSOM (CSS Object Model):
- CSSOM represents the computed styles and rules from parsed CSS files. It provides a structured representation of CSS stylesheets.
- Used for
     - `Style Computation` ( to compute the final styles that should be applied to each DOM element)
     - `Layout and Rendering` (positioning, sizing, and visual presentation of elements on the web page)
     - `Responsive Design and Media Queries` (enables the browser to handle media queries)

## DNS explained:[DNS Lookup](https://www.nslookup.io/website-to-ip-lookup/)
- DNS use for assign the IP a name which can be remember/use easily.
- IP address represents a unique location on the web.
