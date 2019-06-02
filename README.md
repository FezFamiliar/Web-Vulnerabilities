# Web-Vulnerabilities and CTF cheat sheet

In this repo I will try to cover everything about Web Vulnerabilities. There are other, **better** repos for this which covers **ALOT** of material but the main thing which is different in this repo is the fact that i try to explain things **as simply as possible** rather than overload you with a huge wall of text.

This repo is developed gradually, i will add things along the way. I am currently working on the [hacker101](https://www.hacker101.com) CTFs.

* `SQL Injection`: Injecting malicious SQL commands to modify/alter an existing query.

     &nbsp;&nbsp;&nbsp; 1. **Blind SQL Injection** - Asking the Database a series of True/False questions and determines the                      answer based on the applications response.
     
     &nbsp;&nbsp;&nbsp; 2. **Error Based SQL Injection** 
     
     &nbsp;&nbsp;&nbsp; 3. **Time Based SQL Injection** - Using sleep(x) function
     
     &nbsp;&nbsp;&nbsp; 4. **UNION Based SQL Injection** for example: id=-4 (a non existent ID) UNION SELECT ...; Because the id doesn't    exist it will execute the union



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

* `XML External Entities (XEE)` It's a kind of XML injection, an attack against an application that parses XML input. Attacks can include outputting local files. ex: `<%3fxml+version%3d"1.0"+encoding%3d"UTF-8"%3f><!DOCTYPE+foo+[<!ELEMENT+foo+ANY><!ENTITY+xxe+SYSTEM+"file%3a///etc/passwd">]><config><location>%26xxe%3b</location></config>`

* `Lightweight Directory Access Protocol (LDAP) Injection` LDAP injection occurs when user input is not properly sanitized and then used as part of a dynamically generated LDAP filter. This results in potential manipulation of the LDAP statements performed on the LDAP server to either view, modify, or bypass authentication credentials. Its kinda rare and can be easily prevented.


## Recognizing Common Encryption/Hashing Schemes


`b2f5ff47436671b6e533d8dc3614845d` -----> MD5 Hash

`$2y$12$kkRc2xuIGtv5hO4iri08UOnqeQ20bI14M78arJyAv.7J1MFX7MOO.` -----> BCRYPT Hash

`TWFuIGlzIGRpc3Rpbmd1aXNoZWQsIG5vdCBvbmx5IGJ5IGhpcyByZWFzb24sIGJ1dCB==` -----> Base64 Encoding

`67F7BFCF4879A627166F07B0FD31B0ED33438B29` -----> SHA1 Hash

`%2Fhash%2Fge%20%20%2Bner%20ate%20` ----> URL Encoding

`9jqo^BlbD-BleB1DJ+*+F(f,q/0JhKF<GL>Cj@.4Gp$d7F!,L7@<6@)/0JDEF<G%<+EV:2F!,O<DJ+*.@<*K0@<6L(Df-\0Ec5e;DffZ(EZee.Bl.9pF"AGXBPCsi+DGm>@3BB/F*&OCAfu2/AKYi(DIb:@FD,*)+C]U=@3BN#EcYf8ATD3s@q?d$AftVqCh[NqF<G:8+EV:.+Cf>-FD5W8ARlolDIal(DId<j@<?3r@:F%a+D58'ATD4$Bl@l3De:,-DJs8ARoFb/0JMK@qB4^F!,R<AKZ&-DfTqBG%G>uD.RTpAKYo'+CT/5+Cei#DII?(E,9)oF*2M7/c` --> Base85 Encoding



## Useful Number Theory Facts

`If we have a few random multiples of n, with large probability their GCD will be equal to n`

`If p is a prime number, and a is any natural number, then the following holds: a^p = a % p`

`Two integers a and b are co-primes if the only positive integer that divides both of them is 1`

## Common Port numbers
 `20/21` - File Transfer Protocol (FTP)\
 
 `22` - Secure Shell (SSH)
 
 `23` - Telnet
 
 `80` - Hyper Text Transfer Protocol (HTTP)
 
 `119` - Network News Transfer Protocol (NNTP)
 
 `123` - Network Time Protocol (NTP)
 
 `389` - Lightweight Directory Access Protocol (LDAP)
 
 `443` - HTTPS
 
 `554` - Real Time Streaming Protocol (RTSP)
 
 `25/465/587` - Simple Mail Transfer Protocol (SMTP)
 
 `8080` - HTTP Proxy
 
 
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
 
 
 ## A few useful tools/libraries
 
 `Sqlmap` --> For automating SQL injections, written in Python.
 
 `Burp` --> A very handy proxy tool that can be used for manipulating HTTP requests, brute forcing login systems and much more..
 
 `Padbuster` --> For automating Padding Oracle attakcs, encrypting AES payloads etc. You do need to install Perl version 5.28.1
 
 `HxD` --> A free HEX editor
 
 `rayon for rust` ---> a very good and easy to use paralelization library for Rust.
 
 ## Crypto
 
 `DNA codes` --> When you have a sequence of A,T,C,Gs you're dealing with DNA encoding.
 
               A - 00
               
               C - 10
               
               G - 01
               
               T - 11
               
               OR
               
![](https://github.com/FezFamiliar/Web-Vulnerabilities/blob/master/dna.png)

You will find a DNA code cracking tool in my repo, it was built solely for this purpose.
               
               
## Block Cipher modes of encryption: 

Electronic Code Block (ECB)

     In ECB every block is encrypted/decrypted seperately.

![](https://github.com/FezFamiliar/Web-Vulnerabilities/blob/master/ECB_encryption.png)

Cipher Block Chainig (CBC)

In CBC encryption the first block is initially XOR-ed with an IV (Initialisation Vector) then encrypted and then the next block is      XOR-ed with this encrypted value.  So every nth block is first XOR with the n-1th block then encrypted, with the exception of the        first. 



![](https://github.com/FezFamiliar/Web-Vulnerabilities/blob/master/CBC_encryption.png)



 In CBC decryption the first block is decrypted and then XOR-ed with an IV (Initialisation Vector) to get the plaintext. Every nth        ciphertext block is first decrypted and then XOR-ed with the previous ciphertext block to get the plaintext.



![](https://github.com/FezFamiliar/Web-Vulnerabilities/blob/master/CBC_decryption.png)



An important concept to understand in block ciphers is **padding**. In block ciphers, text is encrypted by dividing the inital message in blocks 8 , 16, etc. byte lengths. What happends when your message isn't exactly 16 bytes long? Well, it gets **padded**. So how does it manifest itself? Easy. If you need 3 bytes of padding you get padded **3 bytes of 3**, if you need 1 byte of padding, you get padded **1 byte of 1** and so on. Example: (128-bit AES)

     The word "Computer" consists of 8 bytes, so it needs another 8 bytes of padding, it will be C O M P U T E R \x08 \x08
     \x08 \x08 \x08 \x08 \x08 \x08         
     
An important note here is that you always have padding. Even when you don't need it.
 
     An 8 byte block with equal padding looks like this: T U T O R I A L \x08 \x08 \x08 \x08 \x08 \x08 \x08 \x08

Why does it need padding even if it its equally divisible? This is necessary so the deciphering algorithm can determine with certainty whether the last byte of the last block is a pad byte indicating the number of padding bytes added or part of the plaintext message.
 
 

