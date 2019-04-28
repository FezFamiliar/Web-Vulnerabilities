# Web-Vulnerabilities and CTF cheat sheet

In this repo I will try to cover everything about Web Vulnerabilities. There are other, **better** repos for this which covers **ALOT** of material but the main thing which is different in this repo is the fact that i try to explain things **as simply as possible** rather than overload you with a huge wall of text.

This repo is developed gradually, i will add things along the way. I am currently working on the [hacker101](https://www.hacker101.com) CTFs.

* `SQL Injection`: Injecting malicious SQL commands to modify/alter an existing query.

     &nbsp;&nbsp;&nbsp; 1. **Blind SQL Injection** - Asking the Database a series of True/False questions and determines the                      answer based on the applications response.
     
     &nbsp;&nbsp;&nbsp; 2. **Error Based SQL Injection** 
     
     &nbsp;&nbsp;&nbsp; 3. **Time Based SQL Injection** - Using sleep(x) function
     
     &nbsp;&nbsp;&nbsp; 4. **UNION Based SQL Injection**





* `Cross Site Scripting (XSS)`: JavaScript injection into the browser.

     &nbsp;&nbsp;&nbsp; 1. **Stored (XSS)**: The payload is stored somewhere (database, message forum, comment field, etc.) and when the      victim retrieves it, you get XSS.
     
     &nbsp;&nbsp;&nbsp; 2. **Reflected (XSS)**: The payload is immediately returned by the web app in a form of error message, search        result etc. For ex. you input `<script>alert('XSS');</script>` in the URL --> you get an alert back.
     
     &nbsp;&nbsp;&nbsp; 3. **DOM-based (XSS)**
     

* `Cross Site Request Forgery (CSRF)` CSRF is an attack that tricks the victim into submitting a malicious request.

* `Server Side Request Forgery (SSRF)`SSRF is an attack that lets you read or update resources on a server.

* `Path Traversal`:  Climbing out of the web root (by appending '../') and trying to gain unauthorized access to some files.

* `File Inclusion`: If the application uses some kind of "dynamic file inclusion" for ex. (php include), this can lead to **code execution on the server (RCE), outputting the contents of a file, Sensitive Information Disclosure,  DOS(Denial Of Service)**

     &nbsp;&nbsp;&nbsp; 1. **Remote File Inclusion (RFI)**  is the process of including remote files

     &nbsp;&nbsp;&nbsp; 2. **Local File Inclusion (LFI)** is the process of including files, that are already locally present on the server
     
* `Remote Code Execution (RCE)`

* `Broken Authentication`

* `Sensitive Data Exposure`

* `XML External Entities (XEE)` It's a kind of XML injection, an attack against an application that parses XML input. Attacks can include outputting local files.

* `Lightweight Directory Access Protocol (LDAP) Injection` LDAP injection occurs when user input is not properly sanitized and then used as part of a dynamically generated LDAP filter. This results in potential manipulation of the LDAP statements performed on the LDAP server to either view, modify, or bypass authentication credentials. Its kinda rare and can be easily prevented.


## Recognizing Common Encryption/Hashing Schemes


`b2f5ff47436671b6e533d8dc3614845d` -----> MD5 Hash

`$2y$12$kkRc2xuIGtv5hO4iri08UOnqeQ20bI14M78arJyAv.7J1MFX7MOO.` -----> BCRYPT Hash

`TWFuIGlzIGRpc3Rpbmd1aXNoZWQsIG5vdCBvbmx5IGJ5IGhpcyByZWFzb24sIGJ1dCB==` -----> Base64 Encoding

`67F7BFCF4879A627166F07B0FD31B0ED33438B29` -----> SHA1 Hash

`%2Fhash%2Fge%20%20%2Bner%20ate%20` ----> URL Encoding



## Useful Number Theory Facts

`If we have a few random multiples of n, with large probability their GCD will be equal to n`

`If p is a prime number, and a is any natural number, then the following holds: a^p = a % p`

`Two integers a and b are co-primes if the only positive integer that divides both of them is 1`

## A few HTTP status codes and what they mean
`Moved Permanently 301` ----> Used when the requested URL has been moved. The response should contain in the Location header the URL where the resource now resides.

`Bad Request 400` ----> Syntax Error

`Unauthorized 401` ---> Username and password required

`Forbidden 403` ----> The server won't allow you to visit the requested file

`Not Found 404` ---> The request file doesn't exist on the server

`Method Not Allowed 405` ---> Used when a request is made with a method that is not supported for the requested URL. The Allow header should be included in the response to tell the client what methods are allowed on the requested resource.

`Gone 410` ----> Similar to 404, but the server once held the resource.

`Internal Server Error 500` ----> Something has gone wrong on the server


## HTTP Requests

 `GET` ---> Used to retrieve information from a given server via a given URL.
 
 `POST` ----> Used to send data to a server (sensitive) file uploads, customer information, login credentials etc. 
 
 `PUT` ----> Same as POST but multiple PUT requests always produce the same response.
 
 `HEAD` -----> Same as GET but without the Header Body.
 
 `OPTIONS`  -----> Describes the communication methods allowed for a given resource.
 
 `TRACE` ----> Often used as a debugging mechanism, TRACE performs a loop-back test along the path to the target resource.
 
 `DELETE`  ------> The HTTP DELETE request method deletes the specified resource.
 
 `CONNECT` ----> Starts a two-way communication with a given resource. It is often used to access websites with a valid SSL(Secure Socket Layer) HTTPS. 
 
 `PATCH` ----> PATCH applies partial modifications to a resource. It is similiar to PUT but similiar requests, *may* have different effects.
 
 
 ## A few useful tools
 
 `Sqlmap` 
 
 `Burp`
 
 ## Crypto
 
 `DNA codes` --> When you have a sequence of A,T,C,Gs you're dealing with DNA encoding.
 
               A - 00
               
               C - 10
               
               G - 01
               
               T - 11
               
               OR
               
               ![DNA](https://github.com/FezFamiliar/Web-Vulnerabilities/blob/master/dna.png)
               
               

 

