# TryHackMe Notes 🧠

This file contains my notes from the TryHackMe learning paths I've worked through, including core concepts, commands, and key takeaways. Each section maps to a specific room or module for easy reference.

---

## Cyber Security 101 Learning Path

### Networking Core Protocols
Learn about the core TCP/IP Protocols

#### Four main types of DNS (Domain Name System) Records:

- A record: The A (Address) record maps a hostname to one or more IPv4 addresses. For example, you can set example.com to resolve to 172.17.2.172.

- AAAA Record: The AAAA record is similar to the A Record, but it is for IPv6. Remember that it is AAAA (quad-A), as AA and AAA would refer to a battery size; furthermore, AAA refers to Authentication, Authorization, and Accounting; neither falls under DNS.

- CNAME Record: The CNAME (Canonical Name) record maps a domain name to another domain name. For example, www.example.com can be mapped to example.com or even to example.org.

- MX Record: The MX (Mail Exchange) record specifies the mail server responsible for handling emails for a domain.

#### HTTP / HTTPS

- Hyper Text Transfer Protocol (Secure)
- TCP Ports 80 & 443 respectively

Some of the commands or methods that your web browser commonly issues to the web server are:

- GET retrieves data from a server, such as an HTML file or an image.
- POST allows us to submit new data to the server, such as submitting a form or uploading a file.
- PUT is used to create a new resource on the server and to update and overwrite existing information.
- DELETE, as the name suggests, is used to delete a specified file or resource on the server.

#### Commands
- nslookup (used to look up the ip address of a domain)
- whois (provides information about the entity that registered a domain name)
