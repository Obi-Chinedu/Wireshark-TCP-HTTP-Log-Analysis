# Wireshark-TCP-HTTP-Log-Analysis

### This project aims to provide comprehensive understanding and analysis of TCP/HTTP logs captured using Wireshark. 

### This project helps to gain insights into network traffic, identify potential security threats, and troubleshoot network issues.

## `Documentation`
In this reading, you’ll learn how to read a Wireshark TCP/HTTP log for network traffic between employee website visitors and the company’s web server. 
Most network protocol/traffic analyzer tools used to capture packets will provide this same information

This Wireshark TCP log section provided to you starts at log entry number (No.) 47, which is three seconds and .144521 milliseconds after the logging tool started recording. 
This indicates that approximately `47 messages were sent and received by the web server in the 3.1 seconds after starting the log.` 
This rapid traffic speed is why the tool tracks time in milliseconds. 

The source and destination columns contain the source IP address of the machine that is sending a packet and the intended destination IP address of the packet. 
``In this log file, the IP address 192.0.2.1 belongs to the company’s web server.`` ``The range of IP addresses in 198.51.100.0/24 belong to the employees’ computers.`` 

The Protocol column indicates that the packets are being sent using the TCP protocol, which is at the transport layer of the TCP/IP model. In the given log file, you will notice that the protocol will eventually change to HTTP, at the application layer, once the connection to the web server is successfully established.

``The Info column provides information about the packet.`` ``It lists the source port followed by an arrow → pointing to the destination port.``

``In this case, port 443 belongs to the web server. Port 443 is normally used for encrypted web traffic.``

- The next data element given in the Info column is part of the three-way handshake process to establish a connection between two machines. 

**In this case, employees are trying to connect to the company’s web server:**
- The ``[SYN] packet`` is the initial request from an employee visitor trying to connect to a web page hosted on the web server. SYN ``stands for “synchronize.”`` 
- The ``[SYN, ACK] packet`` is the web server’s response to the visitor’s request agreeing to the connection. The server will reserve system resources for the final step of the handshake. SYN, ACK ``stands for “synchronize acknowledge.”``
- The ``[ACK] packet`` is the visitor’s machine acknowledging the permission to connect. This is the final step required to make a successful TCP connection. ACK ``stands for “acknowledge.”``

Notice that the handshake process takes a few milliseconds to complete. Then, you can identify the employee’s browser requesting the sales.html webpage using the HTTP protocol at the application level of the TCP/IP model. Followed by the web server responding to the request.

![image](https://github.com/Gingercapo/Wireshark-TCP-HTTP-Log-Analysis/assets/56441231/6113681b-b6ea-4ce4-9059-6a0f6d2e955e)

## `The Attack`







