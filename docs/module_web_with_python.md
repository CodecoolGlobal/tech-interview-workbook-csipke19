# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!
- Use uppercase characters when you use a statement (like "SELECT", "FROM")
- Separate the different statements in line from each other ("SELECT" in first row, "FROM" in next row)
- lower case characters to column name, when you name them (like "AS salary")
- Specify the SELECT-ed elements, don't use "*"
- semicolon at the end of the query(";")
#### What layers can you name in a simple web application?
- Presentation layer
- Data service layer
- Business logic layer
- Data access layer

### Error handling
#### What error can occur, when an array does not have an element on the requested index?
In Javascript, if your index is greater than the array length, then the value will be "undefined"
#### What is the “finally” block, and how would you use it?
The finally block is part of the try/catch statement. The block runs even if the result is not the one we looked for.
#### Why should we catch special exception types?
Because you can handle a specific error which can appear during the function.

### Security
#### What is SQL injection? How to protect an application against it?
What is SQL injection?:
SQL Injection attacks are one of the oldest and most dangerous web application vulnerabilities. They can go around authentication and authorization of a web page or web application and retrieve the content of the entire SQL database. They use SQL Injection to add, modify, and delete records in the database.
How to prevent it?:
- Must protect all sort of inputs (not just the login forms)
- Turn off visibility of database errors
- Remove single quotes
#### What is XSS? How to protect an application against it?
XSS (Cross-site scripting) 
#### How to properly store passwords?
You want to hash the password using a salt and a secured server to store that.
#### What is HTTPS?
HTTPS means that the HTTP connection is Secure. 
#### What is encryption and decryption?
Encryption is a method to keep valuable information (like passwords) safe from the spying eyes. Encrypters like the MD5 converts the decimal values into a hexadecimal one, so we can't know the original value at once. Decryption is the process, when we decipher the encrypted value.
#### What is hashing?
Hashing is the process of changing a plain text or a key to a hashed value by applying a hash function. Hashing is a one-way encryption process such that a hash value cannot be reverse engineered to get to the original plain text.
#### What is the difference between encryption and hashing? When would you use which?
Hashing helps protect the integrity of the information and Encryption is used to secure the data from the reach of third parties.
Hashing emphases on the integrity of the information while Encryption focuses on the confidentiality of the data.
#### What encryption methods do you know?
AES, DES, RSA
#### What hashing methods do you know?
MD5, SHA, Bcrypt
#### How/where would you store sensitive data (like db password, API key, ...) of your application?
On a different server that can only authorized people can access and not on a server where my website is.

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?
Stack and Queue data structures are object containers, the "Stack" follows the LIFO (Last in first out) principle while the "Queue" follows the FIFO (First in first out) principle.
#### What is BubbleSort? Describe the main logic of this sorting algorithm.
Bubble sort or sinking sort is a sorting algorithm, repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order. The sorting algorithm is named for the way smaller or larger elements "bubble" to the top of the list.
#### Explain the process of finding the maximum and minimum value in a list of numbers!
You get the first element in a list, and with a for iteration you compare it with the other numbers in the list and swap the first element if the checked number is smaller/bigger (it depends on the thing you want to get as a result)
#### Explain the process of calculating the average value in an array of numbers!
You need to add every every number in the array and then subtract them with the length of the array.
#### What is Big O complexity? Explain time and space complexity!
Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity.
#### Explain the process of calculating the average value in a list of numbers!
You need to add every every number in the list and then subtract them with the length of the list.

### Procedural
#### How the CASE condition works in SQL?
The CASE statement goes through conditions and returns a value when the first condition is met (like the switch-case statement in JS)
#### How the switch-case condition works in JavaScript?
The switch statement is used to perform different actions based on different conditions and after the first case the rest of the cases runs too (that's why you need to use a break in the cases)
#### How to achieve a switch-case-like structure in Python?
In python 3.10, it got a switch condition in the form of "match-case" and it works like the switch-case in JS, but you don't need to use "break" to prevent the other cases from running
#### Explain variable scoping in Python!
The variable is only avaliable in the scope it is created. (like in a function or globaly)
#### What’s the difference between const and var in JavaScript?
Const's value is "constant", so it can't be modified. "var" was used before the let and const variable declarations. The problem with var that the declared variable can be used globaly (if you use var for a for loop variable, you can access it globaly)
#### How the list comprehension looks like in Python?
"[x for x in list]" x get placed in the list for every variable the x pick up as value from the "list" list
#### How the “ternary expression” looks like in Python?
"x = 1 if y = 2 else 0" x = 1 if the y is equals to 2 otherwise the variable has the 0 as value
#### How the ternary expression looks like in JavaScript?
"let x = (y = 2) ? 1 : 0" Not like in python, the condition is declared first, then a question mark, then on the left side the value if the condition it true, on the otherside the value if it's false
#### How to import a function from another module in Python?
"import python_file_to_import"
#### How to import a function from another module in JavaScript?
you need to put the "export" beside the function you want to export, then "import {functionName} from "./file/path/jsFileToImport.js"

### Functional
#### What is recursion?
A recursive function is a function that calls itself until it doesn’t. A recursive function always has a condition to stop calling itself. Otherwise, it will call itself indefinitely.
#### Write a recursive function which calculates the Fibonacci numbers!
function fibonacci(num) {
    if(num < 2) {
        return num;
    }
    else {
        return fibonacci(num-1) + fibonacci(num - 2);
    }
}
const nTerms = prompt('Enter the number of terms: ');
for(let i = 0; i < nTerms; i++) {
        console.log(fibonacci(i));
    }
#### How to store a function in a variable in Python?
x = function()
#### What is an event listener? How to attach one?
Event listener are used on tag elements (or on the whole page) to watch for some kind of event to take place (like a left mouse click in the example) and then run a JS function if it happens.
You can attach one like this:
document.getElementById("id_x").addEventListener("click", jsFunction)
#### How to trigger an event in JavaScript?
let event;
if(document.createEvent){
    event = document.createEvent("HTMLEvents");
    event.initEvent("dataavailable", true, true);
    event.eventName = "dataavailable";
    element.dispatchEvent(event);
} else {
    event = document.createEventObject();
    event.eventName = "dataavailable";
    event.eventType = "dataavailable";
    element.fireEvent("on" + event.eventType, event);
}
#### What is a callback function? Tell some examples of its usage.
A callback is a function passed as an argument to another function.
Callbacks are mainly used in asynch functions (like in the fetch API), where the function need to wait for the other function to finish
#### What is a Python decorator? How does it work? Tell some examples of its usage.
A decorator takes in a function, adds some functionality and returns it. 
Like in Flask, the "@app.route("/")" take the function declared under it, and makes the route for the Flask server, so users can access it.
#### What is the difference between synchronous and asynchronous execution?
Synchronous execution is when the program waits for the other calculations to finish before going to the next.
Asynchronous execution is used when the program for example, use a fetch API request and you don't need to wait for the request to finish, so the program runs while the fetch API request runs.

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?
#### When do you use the DISTINCT keyword in SQL?
DISTINCT is used when you want only distinct (different) values as a result (like in a COUNT where you only want to count the different values)
#### Talk about the behavior/goal of these base SQL clauses: WHERE, GROUP BY, HAVING, ORDER BY?
- WHERE: With this clause, we can get back specific data from a query. It needs to be called before the the GROUP BY statement, and it can't accept functions.
- HAVING: This clause can give you back specific data like the "WHERE" statement, but it must be declared after the GROUP BY statement and it can accept functions AND can only be applied to rows which appears in the GROUP BY statement.
- GROUP BY: This statement groups repeating data into one and summarize the rows.
- ORDER BY: Orders the data by the given collums, the first row will be the main order and the next one is the second one. The ORDER BY has a DESC and ASC (default) command and it can be used after the row to declare the ordering way.
#### What are aggregate functions in SQL? Give 3 examples.
Aggregate functions are mathematical computations involving a range of values
Examples:
- SUM
- COUNT
- MAX
#### What kind of JOIN types do you know in SQL? Could you give examples?
- INNER JOIN: You use this JOIN, when you only want the that can be find in both tables only
- LEFT JOIN: You a table to the current table, where the current table's data is fully represented, while the table's data only represents the data where it sees connection.
- RIGHT JOIN: The same as LEFT JOIN just with the connected table as the one with all it's rows
#### What are the constraints in sql?
SQL constraints are used to specify rules for data in a table. (like UNIQUE, PRIMARY_KEY, FOREIGN_KEY)
#### What is a cursor in SQL? Why would you use one?
#### What are database indexes? When to use?
#### What are database transactions? When to use?
#### What kind of database relations do you know? How to define them?
#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?
" SELECT address FROM table WHERE adress ILIKE "%miskolc%" "
#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?
#### How to include a JavaScript file in a webpage?
With the "script" tag, and you need to give the "src" beside it in the tag, like: "../data/js/usedscript.js"
#### How to include a CSS file in a webpage?
With the link tag, then you need to give the "rel"ation for the file, which is "stylesheet" and then you need to give the path where you can find the given css file after a "href" attribute
#### How to select an element using its id in CSS?
If you want to work withonly the ID, then you need to use the "#" before the id (like "#medal-owner")
#### How to select elements using their class in CSS?
For the classes, you need to use a "." before the class name (like .cards)
#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?
.alpha, .beta { }
#### How to select all list items in all ordered lists on the page in CSS?
With the "ol li" or the "ol > li" reference
#### How to select elements using their attributes in CSS?
You need to give the element (like input) and then in a square bracket the attribute you want to specify (like input[type="text")
#### What are UX and UI?
UX (User Experience) is when you try to see the webpage with the eye of the users, to make the page easy to use and understandable.
UI (User Interface) is when you try to make the webpage appealing to the user's eyes.
#### Please list some points that an application should fulfill to have good UX.
- Make the functions user friendly
- Plan the route the user will walk on to fulfill his goals.
#### What is XML, XSLT, DTD?
#### What is the difference between HTML and XML?

### Javascript

#### What is javascript?
Javascript (JS or ECMAscript (ES)) is a text-based programming language used both on the client-side and server-side that allows you to make web pages interactive.
#### When to use AJAX? Bring examples of its usage.
AJAX stands for (A)synchronous (J)avaScript (A)nd (X)ML, but nowadays the XML format got replaced with JSON. AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page. 
AJAX example: 
- Fetch API (widely used)
- XMLHttpRequest (outdated)
When you use Fetch API, the function which uses the result from this API request, needs to wait for the answer, or the result will be undefined OR you get a Promise as a result, because the API request is slower than the function progress, and this is why you need to use an asynchronous function with a "wait" statement, where you ask for the API request result.
#### What is DOM and how to manipulate it from Javascript?
DOM (Document Object Model) is a W3C (World Wide Web Consortium) standard. To manipulate it, you need to 
#### What is event bubbling/capturing? How would you use it?
Event bubbling is when we first capture the clicked event and then the parent elements are called.
Event capturing is when the most outer element gets called first, all the way to the clicked element.
You can capture events if you write true 
element.addEventListener("click", ()=>{alert("this is an alert")}, true)
#### What is JSON and how do we use it?
JSON (JavaScript Object Notation) is a text-based data format following JavaScript object syntax. JSON exists as a string and used when you want to transmit data across a network.

## Software engineering

### Version control

#### What type of branching strategy would you use?
Every new feature needs to be separeted from the main branch
#### What would you do if you find a bug on the production code (master branch)?
#### How can you move changes from one branch to another in GIT?
#### How does a VCS help with code reviews?
#### What is your favorite git command? Why?
push, because it means that i'm done everything I wanted to do and from that point my work is safe on the github.
#### What does remote/local mean in Git? 
The project version I have on my computer and not necessarily the same as the one on Github.

### DevOps

#### Why is it good to use a package manager software?
Package managers keep track of the used programs and you can easly update, delete or install new programs with them.
Examples:
- pip
- pacman
- apt-get
#### Why is it good to use a virtual environment for a project?
Because you can work in an enviroment that has still version of the used programs, and you only work with the ones you want with. (like pyton, jinja, bcrypt)

### Networks

#### What kind of HTTP status codes do you know?
- 200 OK status, it means that everything runs flawlessly.
- 500 Internal Server Error, it means that an uxepected error happened. This error is usually returned by the server when no other error code is suitable.
- 400 Bad Request, this means that the page calls a method which is not allowed on the route.
- 404 Page not found means that the server can't find the requested resource (like the route you want to reach doesn't exist)
#### What is a API?
The API (Application Programming Interface) simplifies software development and innovation by enabling applications to exchange data and functionality easily and securely.
#### What is REST API?
A REST API is an API that adjust to the rules of the REST (Representational State Transfer).
Examples
- Use GET method when you want to get data
- Use POST method if you create data
- Use PUT method if you modify data
- Use DELETE method if you delete data 
#### What is JSON? When to use?
JSON (JavaScript Object Notation) is a text-based data format following JavaScript object syntax. You can use it during API requests to send data to other computers.
#### What is TCP/IP? What layers does it define, what are they responsible for?
#### What’s the difference between TCP and UDP?
TCP is ceóonnection oriented while UDP is a connetionless protocoll. TCP is slower, but you don't suffer packet losses while with UDP, you do.
#### How does an HTTP Request look like? What are the most relevant HTTP header fields?
#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
#### What is DNS? How does it work?
DNS (Domain Name System) allows us to call a webpage by typing a simple domain name (www.promanproject.com) instead of the IP adress (10.142.43.127)
#### What is a web server?
A web server is a computer that runs websites.
#### Explain the client-server architecture.
#### What would you use a session for?
#### What would you use a cookie for?
For example, cookie is used to keep a user logged in to a website for a longer period (or permanently)

## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
The main feature behind this methodologies, is that the team can adjust to something and can do things according to it, so they always stay on the track.
Methodologies: SCRUM, Agile, Waterfall
#### What are the SCRUM roles?
SCRUM leader, Product owner, development team
#### What are the SCRUM ceremonies?
Backlog grooming, sprint planning, daily scrum, sprint review, sprint retrospective
#### What are the SCRUM artifacts?
product backlog, sprint backlog, increments
#### What is the main goal of a retrospective meeting?
To see what the team did wrong and what they should do better next time.
#### Explain, when would you recommend to use the waterfall methodology?
If the tasks depends on the previous ones.
