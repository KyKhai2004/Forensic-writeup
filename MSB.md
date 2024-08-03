### Description
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...

### Related term

**1. COMMAND wget:**

wget is a tool in linux. You can use it to retrieve files from different web servers. It supports protocols such as FTP, SFTP, HTTP and HTTPS.

**2. FTP (File transfer protocol):**

![FTP](https://media.geeksforgeeks.org/wp-content/uploads/20240110113246/File-Transfer-Protocol-and-HTTPS-gif-2.gif)

Like most TCP/IP protocols, FTP is based on the Client – ​​Server model. However, unlike other applications running on TCP/IP, FTP requires 2 TCP connections:

- Control connection (using port 21 - on the server): This is the main logical TCP connection created when the session is established. It is performed between control processes. It is maintained throughout the session and only allows control information to pass through such as commands or responses.
- Data connection (using port 20 – on the server): This connection uses very complex rules because data types can be different. It is performed between data transfers. This connection opens when a file transfer command is issued and closes when the file transfer is complete

**3. SFTP (Security file transfer protocol):**

This protocol is really the same as FTP; it is just different that all the files before transfer be encoded.

![SFTP](https://media.geeksforgeeks.org/wp-content/uploads/20211025154558/SFTPEncryptionandDecryption.jpg)

**4. The difference between HTTP vs. HTPPS:**

Hypertext protocol (HTTP) is a protocol or set of rules followed for client-server communication. When you visit a website, the browser sends an HTTP request to the web server and the web server sends an HTTP response. The web server and your browser will exchange data in plain text. To summarize, the HTTP protocol is the communication network that supports the art facility. As the name suggests, hypertext security protocol (HTTPS) is a more secure version or extension of the HTTP protocol. In HTTPS, the browser and server establish a secure, encrypted connection before transmitting data.
