## Some term
**pay load:** 
Payload is the data portion of a packet transported between two partners, which does not contain protocol data or metadata that is only sent for use in transporting the payload. Payload is usually text, signs or sounds. Payload is usually located under the header, and depending on the network protocol, there may be an additional trailer.

In computer security, a payload is a part of a piece of malware such as a worm or virus, a piece of code that is run on the victim's computer, used to perform some malicious activity, such as destroying data, sending spam or data encryption. In addition to the payload, such malware has additional overhead code to spread it, or to avoid being identified.
## Description
How about some hide and seek heh? Download this file and find the flag.
## Approach
Open the provided trace.pcap packet capture file in Wireshark

CLick to find a packet
![Screenshot (750)](https://github.com/user-attachments/assets/aff10511-1458-40bf-9ee5-bd675fe1d03e)
*picture show the tool find a packet*

you select option [packet bytes](https://www.wireshark.org/docs/wsug_html_chunked/ChUsePacketBytesPaneSection.html) and type string, find the string "picoCTF" then we will have the result bellow
![image](https://github.com/user-attachments/assets/00b7108d-e086-432b-9205-be57ddbe023f)
*picture show the result*

Found packet #507 @ Timestamp: 0.101450

**TCP payload**
```
0000   45 00 00 52 00 01 00 00 40 06 c3 90 ac 10 00 02   E..R....@.......
0010   0a fd 00 06 00 14 00 15 00 00 00 00 00 00 00 00   ................
0020   50 02 20 00 8b 73 00 00 70 69 63 6f 43 54 46 7b   P. ..s..picoCTF{
0030   50 36 34 50 5f 34 4e 34 4c 37 53 31 53 5f 53 55   P64P_4N4L7S1S_SU
0040   35 35 33 35 35 46 55 4c 5f 35 62 36 61 36 30 36   55355FUL_5b6a606
0050   31 7d                                             1}
```


