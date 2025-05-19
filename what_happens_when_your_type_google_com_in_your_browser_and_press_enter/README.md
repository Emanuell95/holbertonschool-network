# 🧠 What Happens When You Type `https://www.google.com` and Press Enter?

This project explains the end-to-end process that occurs when a user enters a URL into the browser. It’s a foundational systems design question commonly asked in software engineering interviews.

## 📌 Objective

To demonstrate a thorough understanding of how the modern web stack operates, including:
- DNS Resolution
- TCP/IP Networking
- Firewall filtering
- Secure communication with HTTPS/SSL
- Load balancing
- Web and application server roles
- Database interactions

## 🧩 Process Overview

### 1. DNS Request
The domain `www.google.com` is resolved to its IP address via a DNS lookup, possibly involving:
- Browser/OS cache
- Local DNS server (ISP)
- Root and TLD DNS servers
- Authoritative DNS server

### 2. TCP/IP Connection
Once the IP is known, a TCP connection is established using the three-way handshake:
- SYN → SYN-ACK → ACK  
This ensures a reliable transport layer connection over IP.

### 3. Firewall
The request must pass through firewalls:
- Local firewall (client side)
- Server-side firewall (Google’s data centers)

These filter traffic by IP, port, and protocol to enhance security.

### 4. HTTPS/SSL
Because `https://` is used, the browser and server initiate a TLS/SSL handshake to:
- Authenticate the server with a certificate
- Establish encryption using a session key
- Ensure confidentiality and integrity of data

### 5. Load Balancer
The request hits a load balancer, which:
- Routes traffic to a healthy, least-loaded server
- Distributes traffic globally
- Provides redundancy and high availability

### 6. Web Server
The selected server (e.g., Nginx or a custom Google server):
- Parses the HTTP request
- Serves static content
- Passes dynamic requests to an application server

### 7. Application Server
The application server:
- Handles business logic
- Processes requests like search queries
- Requests data from databases
- Prepares a dynamic HTML or JSON response

### 8. Database
The database:
- Stores user data, session data, search indexes, etc.
- Responds to queries from the application server
- Enables content personalization and fast search results

## 📈 Diagram

The following diagram visualizes the full path of the request and response:

![Web Request Flow](./A_flowchart_diagram_illustrates_the_steps_involved.png)

## ✅ Summary

| Component         | Role                                                                 |
|------------------|----------------------------------------------------------------------|
| DNS              | Resolves domain name to IP address                                    |
| TCP/IP           | Ensures reliable communication                                        |
| Firewall         | Protects network from unauthorized traffic                            |
| HTTPS/SSL        | Encrypts communication and validates authenticity                     |
| Load Balancer    | Distributes traffic across multiple servers                           |
| Web Server       | Handles incoming HTTP(S) requests                                     |
| Application Server | Processes business logic and dynamic responses                     |
| Database         | Provides persistent data storage and retrieval                        |

## 📚 Use Case

This README and associated diagram can be used to:
- Prepare for systems design interviews
- Serve as a portfolio project for web infrastructure understanding
- Educate peers or junior developers about how the internet works under the hood

---

**Author:** Emanuel Mendoza  
 