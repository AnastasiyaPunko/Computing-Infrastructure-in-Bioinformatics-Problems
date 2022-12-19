# Working with remote servers
## Theory

**What are computer ports on a high level? How many ports are there on a typical computer?**<br>
A port is a virtual point where network connections start and end. Ports are software-based and managed by a computer's operating system. Each port is associated with a specific process or service. Ports allow computers to easily differentiate between different kinds of traffic.<br>
There are 65,535 possible port numbers. Port numbers have three ranges: System Ports (0-1023), User Ports (1024-49151), and the Dynamic and/or Private Ports (49152-65535).<br>

**What is the difference between http, https, ssh, and other protocols? In what sense are they similar? Name default ports for several data transfer protocols.**<br>
HTTP: The Hypertext Transfer Protocol (HTTP) is used for transferring data between devices. HTTP belongs to the application layer (layer 7), because it puts data into a format that applications can use directly, without further interpretation. The lower layers of the OSI model are handled by a computer's operating system, not applications.<br>
HTTPS: The problem with HTTP is that it is not encrypted — any attacker who intercepts an HTTP message can read it. HTTPS corrects this by encrypting HTTP messages.<br>
SSH means “Secure Shell”. It has a built-in username/password authentication system to establish a connection. It uses Port 22 to perform the negotiation or authentication process for connection. Authentication of the remote system is done by the use of public-key cryptography and if necessary, it allows the remote computer to authenticate users.<br>
Both ssh and HTTP are protocols to communicate between client and server.<br>

The protocols can be broadly classified into three major categories: <br>
*Communication protocols* are really important for the functioning of a network. They are so crucial that it is not possible to have computer networks without them. These protocols formally set out the rules and formats through which data is transferred. These protocols handle syntax, semantics, error detection, synchronization, and authentication. (For example, HTTP, TCP, UDP, IP)<br>
*Management protocols* assist in describing the procedures and policies that are used in monitoring, maintaining, and managing the computer network. These protocols also help in communicating these requirements across the network to ensure stable communication. Network management protocols can also be used for troubleshooting connections between a host and a client. (For example, FTP, POP3)<br>
*Security protocols* secure the data in passage over a network. These protocols also determine how the network secures data from any unauthorized attempts to extract or review data. These protocols make sure that no unauthorized devices, users, services can access the network data. Primarily, these protocols depend on encryption to secure data. (For example, HTTPS, SSL)<br>

*Default ports for several data transfer protocols*<br>
HTTP - 80<br>
HTTPS - 443<br>
SSH - 22<br>
DNS - 53<br>
FTP - 20, 21<br>
POP3-110<br>

**Explain briefly: (1) what is IP, (2) what IPs are called 'white'/public, (3) and what happens when you enter 'google.com' into the web browser.**<br>
An *Internet Protocol* address (IP address) is a numerical label that is connected to a computer network that uses the Internet Protocol for communication. An IP address serves two main functions: network interface identification and location addressing.<br>

A *public IP* address is an IP address that is used to access the Internet. Public IP addresses can be routed on the Internet, unlike private addresses. 
The presence of a public IP address on router or computer will allow you to organize own server (VPN, FTP, WEB, etc.), remote access to computer, video surveillance cameras, and get access to them from anywhere on the global network.<br>
With a public IP address, we can set up any home server to publish it on the Internet: Web (HTTP), VPN (PPTP/IPSec/OpenVPN, WireGuard), media (audio/video), FTP, NAS, game server, etc.<br>

*What happens when you enter 'google.com' in the web browser*<br>
Resolve IP address of the URL via DNS<br>
Generate an HTTP request with headers (accept, user-agent, cookie, etc)<br>
Open an HTTP connection to the resolved IP address<br>
Send the request to the server<br>
Receive the response from the server<br>
Parse response headers<br>
Depending on the response headers, perform additional operations<br>
Decompress the response body if it's compressed<br>
Parse the HTML code inside the response body<br>
Resolve any additional resources (images, stylesheets, scripts, etc)<br>
Start loading those resources via their URLs using the same steps<br>
Render the HTML as soon as required resources are loaded, continue loading remaining resources in background<br>
When all the resources are loaded, close the HTTP connection<br>

**What is Nginx? How does it work on the high level? List several alternative web servers.**<br>
*NGINX* is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.<br>

*How does NGINX work*<br> 
Nginx is built to offer low memory usage and high concurrency. Rather than creating new processes for each web request, Nginx uses an asynchronous, event-driven approach where requests are handled in a single thread.<br>
With Nginx, one master process can control multiple worker processes. The master maintains the worker processes, while the workers do the actual processing. Because Nginx is asynchronous, each request can be executed by the worker concurrently without blocking other requests.<br>

NGINX uses a predictable process model that is tuned to the available hardware resources:<br>
The master process performs the privileged operations such as reading configuration and binding to ports, and then creates a small number of child processes (the next three types).<br>
The cache loader process runs at startup to load the disk‑based cache into memory, and then exits. It is scheduled conservatively, so its resource demands are low.<br>
The cache manager process runs periodically and prunes entries from the disk caches to keep them within the configured sizes.<br>
The worker processes do all of the work! They handle network connections, read and write content to disk, and communicate with upstream servers.<br>

*Several alternative NGINX*<br>
The best alternative is Apache HTTP Server, which is both free and Open Source. Other great apps like nginx are Caddy, lighttpd, Traefik and Varnish.<br>


**What is SSH, and for what is it typically used? Explain two ways to authenticate in an SSH server in detail.**<br>
The *SSH protocol* (Secure Shell) is a method for secure remote login from one computer to another. It provides several alternative options for strong authentication, and it protects the communications security and integrity with strong encryption.<br>

*Typical uses of the SSH protocol*<br>
The protocol is used in corporate networks for:<br>
-providing secure access for users and automated processes<br>
-interactive and automated file transfers<br>
-issuing remote commands<br>
-managing network infrastructure and other mission-critical system components.<br>

The two widely used *methods of SSH authentication* for secure remote access are:<br>
-Password authentication (using user name and passwords)<br>
-Public key-based authentication (using public and private key pairs)<br>
*Password-based authentication*<br>
In password-based authentication, after establishing secure connection with remote servers, SSH users usually pass on their usernames and passwords to remote servers for client authentication. These credentials are shared through the secure tunnel established by symmetric encryption. The server checks for these credentials in the database and, if found, authenticates the client and allows it to communicate. <br>
*Public key-based authentication*<br>
In Public key-based authentication, after the client establishes a connection with the remote server, the client informs the server of the key pair it would like to authenticate itself with. The server verifies the existence of this key pair in its database and then sends an encrypted message to the client. The client decrypts the message with it’s private key and generates a hash value which is sent back to the server for verification. The server generates its own hash value and compares it with the one sent from the client. When both the hash values match, the server is convinced of the client’s authenticity and allows it to communicate with the server.
