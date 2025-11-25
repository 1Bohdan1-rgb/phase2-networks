# Wireshark Lab — Week 8 (Mini Report)

## 1. Overview
During this week I worked with basic network traffic in Wireshark.  
I analysed ICMP, TCP, DNS, HTTP and HTTPS.  
For each protocol, I captured real packets, used filters, and made short notes about what I observed.

---

## 2. TCP Analysis
I captured the TCP three-way handshake using the filter:
tcp.flags.syn == 1 || tcp.flags.ack == 1
I could clearly see SYN → SYN-ACK → ACK.  
Sequence and acknowledgement numbers increased logically as the connection was created.  
After the handshake, the data packets started to flow.

*(Screenshot 1: TCP handshake)*

---

## 3. DNS Analysis
Using dig @8.8.8.8 example.com and the filter dns,  
I saw both the query and the response.  
The answer section returned the A record with the server’s IP address.

*(Screenshot 2: DNS query and response)*

---

## 4. HTTP and HTTPS
With http filter I inspected HTTP headers.  
I could see fields like Host, User-Agent, and Server because HTTP is not encrypted.

With tls filter I analysed the HTTPS handshake.  
I found Client Hello, Server Hello, and the Certificate (Subject and Issuer).  
After the handshake the traffic was encrypted.

*(Screenshot 3: TLS Client Hello / Certificate)*

---

## 5. Summary
This mini-lab helped me understand how different protocols look in Wireshark.  
Now I can recognise TCP handshakes, DNS queries, HTTP headers, and the TLS handshake.  
This is important for future Blue Team and SOC analysis.
