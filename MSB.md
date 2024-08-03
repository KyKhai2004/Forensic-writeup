### Description
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...

### Related term

**1. Linux Command:**

- "wget" is a tool in linux. You can use it to retrieve files from different web servers. It supports protocols such as FTP, SFTP, HTTP and HTTPS.
- "grep" for find key word
- "ls" list content in folder
- ["vi"](https://helpdesk.inet.vn/knowledgebase/huong-dan-co-ban-su-dung-vi-trong-linux) for Search, replace, delete, save files...
  example : "vi outputSB.txt" after that we use"/pico" to find keyword pico
- Compare file opening commands in Linux command line
In the Linux environment, there are many different commands used to open and view the contents of files. Each command has its own characteristics and uses. Below is a detailed comparison between some popular commands:

1. cat command:
Function: Display the entire content of one or more files on the screen.
Advantages: Simple, fast.
Disadvantages: Not suitable for files that are too large because they can overflow the screen.
Usage: cat file_name
For example: cat log.txt
2. More command:
Function: Displays the content of the file page by page, helping you view the content slowly.
Advantages: Easy to use, suitable for medium sized files.
Disadvantages: Can only view from beginning to end, cannot search quickly.
Usage: more file_name
For example: more config.txt
3. less command:
Function: Similar to more but provides more features, such as searching, moving up and down in files, viewing by line number, etc.
Advantages: Flexible, powerful, suitable for many uses.
Cons: Can be more complicated for beginners.
Usage: less file_name
For example: less output.log
4. Text editor (vi, nano, emacs):
Function: Not only view but also allows you to edit the content of the file.
Advantages: Flexible, offers many text editing features.
Cons: Needs time to get used to commands and keyboard shortcuts.
Use:
en file_name
nano file_name
emacs file_name
For example: vi script.sh

press "h" for vision list of short key

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

**5. TCP (transmission controll protocol):**

![TCP](https://blog.vinahost.vn/wp-content/uploads/2021/11/giao-thuc-tcp-la-gi-1.png)

- The client sends the server a SYN packet — a connection request from its source port to the server's destination port.
- The server responds with a SYN/ACK packet, confirming receipt of the connection request.
- The client receives the SYN/ACK packet and replies with its own ACK packet.
Once a connection is established, TCP works by dividing the transmitted data into segments, each segment is packaged into a data packet and sent to its destination.

### Approach

The description and name of challenge suggests data may be hidden in the Most Significant Bit (MSB) of the RGB pixels values within the image.

Rather than writing a program to do this analysis, a quick google search found a python tool sigBits.py that can extract data from both LSB and MSB for analysis.

**STEP 1**

use this code bellow to download the picture

```
$ wget https://artifacts.picoctf.net/c/306/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
```
then use command "ls" to check the file is exist or not
**STEP 2**

use this command to downloan python tool, which is can read deep data in picture
```
$ wget https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py
```

**STEP 3**

use this command to read the picture then use "ls" to check the file name "outputSB.txt"
```
$ python3 sigBits.py -t=msb Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
```

**STEP 4**
use of the command less, nano, vi, emacs to read and find the key word "pico"

finally you will have the flag:
```
picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_572ad5fe}
```

