# WEB


### What are the three primary Fielding constraints? (Bonus if you can say who Fielding is!)
Client-Server, Stateless, Uniform Interface

### What sub-constraints make up a Uniform Interface
Identification of Resources, manipulation of resources through representations, self-descriptive messageshypermedia, hypermedia

### Walk through an arbitrary example of a RESTful request/response cycle, and describe what makes it RESTful


###  What happens when you type in www.google.com and hit enter?
1. The browser checks the cache for a DNS record to find the corresponding IP address
2. If the requested URL is not in the cache, ISP’s DNS server initiates a DNS query to find the IP address of the server
3. Browser initiates a TCP connection with the server
4. The browser sends an HTTP request to the web server
5. The server handles the request and sends back a response
6. The browser displays the HTML content


### Why do we need a DNS?
It links websites strings to their corresponding IP address


### Explain TCP, and why it is a necessary protocol
Transmission Control Protocol is a way to make sure every piece of data you requested is accounted for before being given to you computer. it ensures that all data is sent for a more reliable experience

App => Transport => Internet => Network


### What are the common HTTP methods? When are they used, and what do they accomplish?
1.	GET
The GET method is used to retrieve information from the given server using a given URI. Requests using GET should only retrieve data and should have no other effect on the data.
2.	HEAD
Same as GET, but transfers the status line and header section only.
3.	POST
A POST request is used to send data to the server, for example, customer information, file upload, etc. using HTML forms.
4.	PUT
Replaces all current representations of the target resource with the uploaded content.
5.	DELETE
Removes all current representations of the target resource given by a URI.
6.	CONNECT
Establishes a tunnel to the server identified by a given URI.
7.	OPTIONS
Describes the communication options for the target resource.
8.	TRACE
Performs a message loop-back test along the path to the target resource.

### What is the difference between HTTP and HTTPS
HTTP has the ability to fall to a Man in the Middle Attack, HTTPS is a bit more secure


### What is the difference between localStorage and sessionStorage?
localStorage persists data after the browser is closed and sessionStorage does not

### Why is it important that users cannot modify their cookies?
They contain authentication information so if users change that info, they server thinks they are someone else

### When are cookies sent to the server?
All cookies valid for a page are sent from the browser to the server for every request to the same domain - this includes the original page request, any subsequent Ajax requests, all images, stylesheets, scripts, and fonts


### What is the danger of an XSS
Cross-site Scripting (XSS) refers to client-side code injection attack wherein an attacker can execute malicious scripts (also commonly referred to as a malicious payload) into a legitimate website or web application. XSS is amongst the most rampant of web application vulnerabilities and occurs when a web application makes use of unvalidated or unencoded user input within the output it generates.


### What is a CSRF Attack?
An attack whereby a malicious entity tricks a victim into performing actions on behalf of the attacker in two parts. The first part is to trick the victim into clicking a link or loading up a page. This is normally done through social engineering which works exceptionally well into leveraging a victim’s curiosity to click on malicious links. The second part is to send a crafted request in the victim’s browser, that will send a legitimate looking request to the web application. The request will be sent with the values that the attacker wants, including any Cookies that the victim has associated with that website. This way, the web application knows that this victim can perform certain actions on the website and any request sent with these HTTP credentials or Cookies, will be considered as legitimate, even though the victim would be sending the request on the attacker’s command.

### How can you prevent CSRF Vulnerabilities?
Synchronizer Tokens, Same Site Cookies

### Select the correct statement(s) about HTTP methods and status codes
D) A 201 code could be what you should expect when you create a valid blog post
E) A 301 code could indicate that the data cached in your browser already matches what would be returned by your request

### Select the correct statement(s) about HTTP methods
A) POST requests cannot be bookmarked
B) GET requests can contain a body, but you should not expect it to have meaning to what is returned
C) PATCH requests are interpreted to replace only the specified fields
D) PUT requests that omit a field will update the resource b setting that field to null

### Choose the correct statement(s) about HTTPS
A) Successful Man in the Middle attacks can alter the request you are sending without your knowledge
D) Asymmetric Key exchange usually relies on a Certificate Authority to certify public keys

### What is an XMLHttpRequest?
an API in the form of an object whose methods transfer data between a web browser and a web server. The object is provided by the browser's JavaScript environment. The XMLHttpRequest object can be used to exchange data with a server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.


### When are two pages considered to have the same origin?
Two pages have the same origin if the protocol, port (if one is specified), and host are the same for both pages

### How might you allow cross-origin resource sharing?
HTTP Request Headers

### What is CORS?
Cross-Origin Resource Sharing (CORS) is a mechanism that uses additional HTTP headers to tell a browser to let a web application running at one origin (domain) have permission to access selected resources from a server at a different origin. A web application makes a cross-origin HTTP request when it requests a resource that has a different origin (domain, protocol, and port) than its own origin.

### What are the advantages and disadvantages of NoSQL databases vs. SQL databases?
SQL - columns and rows, relational data but can't handle huge scales

NoSQL - can handle huge scales, but needs to be constructed by experts


### What are the different type of SQL Joins?
Inner, Left, Right, Full

### What is the difference between an Inner Join and a Left Join
For two tables A and B, a left join is all the data from one table regardless of join condition and data from another table if that data meets a join condition.  Inner join is data form both table that meets a join condition

### What are the issues one may face when scaling horizontally?
Horizontal scaling means that you scale by adding more machines into your pool of resources; issues include whether the licensing costs for those additional servers, the additional operations cost of powering and cooling and the large footprint they will occupy in the data center

### What is Vertical Scaling?
Vertical scaling means that you scale by adding more power (CPU, RAM) to an existing machine.

### What is a Load Balancer?
A blackbox that balance client requests with multiple servers to keep service time down

### What are some exampels of Horizontal Scaling?
Buying more lower tech servers, shared db's, load balancing

<!-- WEEK 4 -->
### What is Round Robin DNS binding?
a load balance technique where 1 user will request a website and will get one ip address, a second user will request the same website but get a different server, and so on until N servers and then requests are sent to the first server again

### What issue arises regarding sessions when implementing a Load Balancer?
If you are switched to a different server during your session, then your two sessions will have different session tokens or cookies and information will be mismatched

### What is striping when talking about writing to a Hard drive?
Striping is writing portions of data across multiple harddrives to increase write speed

### What is RAID and what functionality can it give you?
Redudant Array of Independent Discs, using multiple harddrives to strip data across them or mirror data. It helps recover data if a harddrive fails

### How can you solve the sticky-session issue without shared file storage on the back-end?
A load balancer can insert a cookie to send a user to the correct server
 
### Explain why you might want to compile and store static HTML pages for something like a Craigslist post.
It can increase performance tie by reducing server requests
 
### What does using 'memcache' do for you?
Stores data in RAM so that data can be pulled from RAM rather than the database


### Why would you want to use an LRU cache in a backend server?
You can send data more quickly for heavy users and keep a track of what that user currently accesses the most and delete the least used for new data

### In the Master-Slave paradigm, what tasks are commonly done by the slave databases and why?
Slaves replicate data from the master database in case the master goes down. Reading from the database can be sent to slave databases


### In a multi-tiered architecture, how do we get redundancy and responsiveness?
A Load balancer for all multiple servers and a load balancer for read queries to slave databases and a master database for adding to the database

### When does DNS load-balancing become necessary?
When traffic becomes so high that you need to load balance between servers in different physical locations (global load balancing)

### What is the principle of Least Privilege and how does it relate to the responsibilities of the Load Balancer?
in a particular abstraction layer of a computing environment, every module (such as a process, a user, or a program, depending on the subject) must be able to access only the information and resources that are necessary for its legitimate purpose

IF a malicious user gets into a server, then they can't access another server because the server they are on can only access certain modules from there


### What is database partitioning?
A collection of databases that are identical, but users are assigned a specific database request from

### Explain high availability and how it relates to the master-master paradigm
A collection of servers that check each other for a "heartbeat" and take on the burden should one server die

<!-- WEEK 5 -->

### Why is FTP a bad idea?
If you send intellectual property or configuration codes, anyone can intercept it, such as server login credentials

### What kinds of information is at risk when comunicating over HTTP?
session information, cookie header information

### Why should you ensure that files on a web server are not being executed by root?
A malicious user can take advantage of a vulnerability and execute a command to mess up the server


### What is WPA2?
An encryption protocol used by wireless routers to block users from sniffing your traffic

### What is public key cryptography?
A protocol where two keys are creatd differently but related: a private key and public key. the public key is encrypted, the private key is the only thing that can decrypt the public key. a sender can send information that has been encrypted in the receiver's public key and the receiver's private key can decrypt the information

### What is a certificate authority?
Entity that issues digital certificates. The digital certificate certifies the ownership of a public key by the named subject of the certificate. This allows others (relying parties) to rely upon signatures or assertions made by the private key that corresponds to the public key that is certified.

In this model of trust relationships, a CA is a trusted third party that is trusted by both the subject (owner) of the certificate and the party relying upon the certificate.

### Why do certificate authorities exist?
it's a middleman that two users can trust to be secure their data between transfers

### Explain Diffie-Hellman key exchange. Why does it work?
its a mathematical formula. P is a large prime number and G is a generated number (usually 2). One coputer chooses a nmumber for A and another computer chooses a number for B. B creates a number TB from the formula and A multiplies that number by regular A, and B does the same thing for TA. both users A and B agree on g^(A*B)%p, so neither one needs to know that other's number to get back their TA or TB

### What is SQL injection? How do you avoid it?
A type of attack where a user can insert a SQL query or command into a form that will get executed. You can avoid it with Real Escape String

### What is same-origin policy?
a policy that prevents document or script loaded form one origin form getting or setting properties of a  document frmo a different origin . Two pages have the same origin  if the protocol, port given, and host are the same for both pages

### When is it not enforced?
When you request data from the same server

### What is JSONP?
padded JSON, grab data from a server and tell the server what function you want called and if the server cooperates, then you can incorporate that data into your DOM


### What are the 9 areas of inquiry that you you should define froma high level before diving into implementation?
1. Features
2. Define APIs
3. Availability
4. Latency Performance
5. Scalability
6. Durability
7. Class Diagram
8. Security and PRivacy
9. Cost Effectiveness

### compare ACID vs. BASE
ACID: Autonomous, Consistent, Isolation, Durability. Used mor ein relational databases
 
BASE: Basically Available SoftState Eventual Consistency. Used more for NoSQL databases

### What is consistent hashing?
Equaling splitting data across several nodes of a database

### What is optimistic vs. pessimistic locking?
O: When multiple transactions update a record, the one with the latest timestamp or version number is kept

P: when multiple transactions update a record, it is done one at a time

### What is strong vs. eventual consistency?
Strong: Reads will always see latest writes
Eventual: Reads will see some writes and eventually see new writes

### Compare and contrast SQL vs. NoSQL vis a vis the above
SQL: has ACID properties

NoSQL: Scales quickly and better

### Why is caching important in system design?
It's used to speed up requests if certain data is frequently needed


### What is a bloom Filter?
used to decide if an element is part of a set or not, may have false positive but never false negatives. super space efficient

### What is PAXOS?
derive consensus over distributed hosts

### What is Pub-Sub pattern?
A publisher sends a message to a queue, a subscriber gets the message from the queue

### What is Map Reduce?
used to distributed and paralle processing of big data. MAP filters and sorts data and REDUCE summarizes the data

### What is multi-threading?


### What is Redis?
REmote DIctionary Store. Key-Value storage, NoSQL DB, in-memory DB with persistence, can be set up as a cluster to provide more availabilty and replication. Can flush data on the harddrive if needed

### What is Kafka?
Distributed, Partitioned, Replicated pub-sub service for online and offline messaging 

### What are NGINX and HAProxy?
Very efficient Load balancers and servers

### What is Docker?
software platform provinding containers inside which you can develop and run distributed applications. can be run on laptop, cloud, or data center 

### What is Hadoop/Spark?
A faster version of MapReduce

### Explain the decision to use 7 characters for the tinyURL
at 1000 requests per second, it would take 100 years to exhaust 62^7 (3.5 trillion) unique strings (62 = a-z, A-Z, 0-9)

### How do you turn a random number between 1 and 3.5 trillion into a 7 character string?
any number can up to 3.5 trillion can be represented as a 43-bit number which can be turned into a string


### What is the downside to just generating a random string, checking the db and putting it if it doesn't exist?
If another user is doing the same thing at the same time, there could be a corruption for what the tinyUrl is referencing


### What is the downside to generating a random string, putting into the DB, getting and checking they are the same?
IT can require multiple requests if the random string generator produces collisions


### What is the MD5 based approach? Advantages/disadvantages?
Calculate the MD5 of the longer URL then take the first 43 bits of the MD5 and use it to generate the tinyURL. MD5 is a hashing function that returns a 128 bit long hash. C

ADV: saves space in the database
DIS: Collisions are still possible

### Explain the counter based approach
A worker will be given a counter number and then rhe counter will increment for the next worker's request. This is to give unique numbers to workers

### What are the advantages with a range-based counter apporach?

### What is a Trie?
A tree structure with letters at each node

### What might you want to store in each node in your Trie?
A letter

### How do you handle it when your Trie becomes too large to be stored on one machine?
You can split the alphabet into subsections and direct requests to those subsections

### How would you collect and update the top results for a certain node in the Trie?

### Explain Websockets
Fully bidirectional connection;  both server and client can initiate requests.


### How would an application know that someone is online?
The app can find when the last time a heartbeat was detected by the user and see if it is within the frequency of sent heartbeats

### What happens when you send a message to someone who isn't online?
A server will persist the messages and ping for a heartbeat until the offline user is online again and then send the messages

### What is the matter with the Naive solution for Timeline?
find out who the user is following, then select all tweets from all followed users and then sort by time 

### How would you ensure high availability of the timeline?
when a user tweets, a table associated with each follower is updated to contain that tweet which can be accessed when the page is loaded

### Discuss Searching, Indexing, and Push notifications in the context of Designing Twitter
...

### What is ambiguous at the outset of the garage problem?
size, type of garage, type of vehicles in spaces

### What is the value of enum as a datatype?
it is an enumerable set of numbers. those numbers can be mapped to other things, such as 1: red, 2: blue

### Explain the idea of an abstract class
a datatype created to store specific information that will help solve an overall problem through object oriented programming