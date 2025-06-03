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

#### SMTP & POP3

Some common SMTP commands are:

HELO or EHLO initiates an SMTP session
MAIL FROM specifies the sender’s email address
RCPT TO specifies the recipient’s email address
DATA indicates that the client will begin sending the content of the email message
. is sent on a line by itself to indicate the end of the email message

The SMTP server listens on TCP port 25 by default.

Some common POP3 commands are:

USER <username> identifies the user
PASS <password> provides the user’s password
STAT requests the number of messages and total size
LIST lists all messages and their sizes
RETR <message_number> retrieves the specified message
DELE <message_number> marks a message for deletion
QUIT ends the P

POP3 server listens on TCP port 110 by default

#### IMAP: Syncronizing Email

Some common IMAP commands are:

LOGIN <username> <password> authenticates the user
SELECT <mailbox> selects the mailbox folder to work with
FETCH <mail_number> <data_item_name> Example fetch 3 body[] to fetch message number 3, header and body.
MOVE <sequence_set> <mailbox> moves the specified messages to another mailbox
COPY <sequence_set> <data_item_name> copies the specified messages to another mailbox
LOGOUT logs out

The IMAP server listens on TCP port 143 by default

| Protocol | Transport Protocol | Default Port Number |
|----------|--------------------|----------------------|
| TELNET   | TCP                | 23                   |
| DNS      | UDP or TCP         | 53                   |
| HTTP     | TCP                | 80                   |
| HTTPS    | TCP                | 443                  |
| FTP      | TCP                | 21                   |
| SMTP     | TCP                | 25                   |
| POP3     | TCP                | 110                  |
| IMAP     | TCP                | 143                  |
