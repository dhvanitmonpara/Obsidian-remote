### How Email Works (From a Computer Networking Perspective)

#### Overview

Email communication involves the transmission of electronic messages over the Internet. It relies on a client-server model and several protocols to ensure that emails are sent, received, and stored correctly.

#### Key Protocols

1. **SMTP (Simple Mail Transfer Protocol)**
2. **POP (Post Office Protocol)**
3. **IMAP (Internet Message Access Protocol)**

#### SMTP (Simple Mail Transfer Protocol)

**Function**:
- Used for sending emails from a client to a server or between servers.

**Workflow**:
1. **Email Composition**: The user composes an email in an email client (like Outlook, Thunderbird).
2. **Mail Submission**: The email client sends the email to an SMTP server using the SMTP protocol.
3. **Mail Transfer**: The SMTP server transfers the email to the recipient's email server.
4. **Mail Delivery**: The recipient's email server stores the email until the recipient retrieves it.

**Ports**:
- Default port: 25
- Secure SMTP (SMTPS): 465 (deprecated) or 587 (current standard for secure submission).

**Commands**:
- `HELO`: Identifies the client to the server.
- `MAIL FROM`: Specifies the sender's email address.
- `RCPT TO`: Specifies the recipient's email address.
- `DATA`: Initiates the transfer of the message body.
- `QUIT`: Terminates the session.

#### POP (Post Office Protocol)

**Function**:
- Used for retrieving emails from a server to a client. It downloads the emails to the local device and often deletes them from the server.

**Workflow**:
1. **Connection**: The email client connects to the email server using POP.
2. **Authentication**: The client provides credentials to authenticate with the server.
3. **Email Download**: Emails are downloaded from the server to the client device.
4. **Deletion (optional)**: Depending on the settings, emails may be deleted from the server after download.

**Ports**:
- Default port: 110
- Secure POP3 (POP3S): 995

**Commands**:
- `USER`: Specifies the username.
- `PASS`: Specifies the password.
- `STAT`: Requests the status of the mailbox.
- `RETR`: Retrieves a specific email.
- `DELE`: Deletes a specific email.
- `QUIT`: Closes the connection.

#### IMAP (Internet Message Access Protocol)

**Function**:
- Used for accessing emails on a server without downloading them to the client. It allows for email management directly on the server, supporting multiple devices.

**Workflow**:
1. **Connection**: The email client connects to the email server using IMAP.
2. **Authentication**: The client provides credentials to authenticate with the server.
3. **Email Management**: Emails can be read, deleted, or organized into folders on the server.
4. **Synchronization**: Changes made on one client are reflected on all devices connected to the email account.

**Ports**:
- Default port: 143
- Secure IMAP (IMAPS): 993

**Commands**:
- `LOGIN`: Authenticates the user.
- `SELECT`: Selects a mailbox to access.
- `FETCH`: Retrieves specific emails.
- `STORE`: Changes flags associated with messages (e.g., read/unread).
- `SEARCH`: Searches for emails matching specific criteria.
- `LOGOUT`: Ends the session.

#### Comparison of POP and IMAP

| Feature            | POP                         | IMAP                       |
|--------------------|-----------------------------|----------------------------|
| Storage            | Local device                | Server                     |
| Access             | Single device               | Multiple devices           |
| Syncing            | No                          | Yes                        |
| Email organization | Limited                     | Server-side folders        |
| Offline access     | Yes (after download)        | Limited (depending on client settings) |
