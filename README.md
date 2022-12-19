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
