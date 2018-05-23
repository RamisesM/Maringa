#### SMTP

Simple Mail Transfer Protocol (SMTP) is a standard communication protocol for
sending email messages on business networks and the Internet.  SMTP was
originally developed in the early 1980s and remains one of the most popular
protocols in use worldwide.

Email software most commonly uses SMTP for sending and either the Post Office
Protocol 3 (POP3) or Internet Message Access Protocol (IMAP) protocols for
receiving mail. Despite its age, no real alternative to SMTP exists in
mainstream usage.

##### How SMTP Works

All modern email client programs support SMTP.  The SMTP settings maintained in
an email client include the IP address of an SMTP server (along with the
addresses of either a POP or IMAP server for receiving emails). Web-based
clients embed the address of an SMTP server inside their configuration, while PC
clients provide SMTP settings that allow users to specify their own server of
choice.

A physical SMTP server may be dedicated to servicing email traffic only but is
often combined with at least POP3 and sometimes other proxy server functions.

SMTP runs on top of TCP/IP and uses **TCP port number 25** for standard
communication. To improve SMTP and help combat spam on the Internet, standards
groups have also designed TCP port 587 to support certain aspects of the
protocol. A few Web email services, such as **Gmail, use the unofficial TCP port
465 for SMTP**.

##### SMTP Commands

The SMTP standard defines a set of commands - names of specific types of
messages that mail clients to the mail server when requesting information. The
most commonly used commands are:

- **HELO and EHLO** - commands that initiate a new protocol session between client
    and server. The EHLO command requests them to respond with any optional SMTP
    extensions it supports
- **MAIL** - command to initiate sending an email message
- **RCPT** - command to provide one email address for a recipient of the current
    message being prepared
- **DATA** - command indicating the start of transmission
    of the email message. This command initiates a series of one or more
    follow-on messages each containing a piece of the message. The last message
    in the sequence is empty (containing only a period (.) as a termination
    character) to signify the end of the email.
- **RSET** - while in the process of
    sending an email (after issuing the MAIL command), either end of the SMTP
    connection can reset the connection if it encounters an error
- **NOOP** - an empty ("no operation") message designed as a kind of ping to check
    for responsiveness of the other end of the session
- **QUIT** - terminates the protocol session

The recipient of these commands replies with either success or failure code
numbers. Issues with SMTP

SMTP lacks built-in security features. Internet spammers have been enabled to
exploit SNMP in the past by generating huge amounts of junk email and having
them delivered via open SMTP servers. Protection against spam has improved over
the years but are not foolproof. Additionally, SMTP does not prevent spammers
from setting (via the MAIL command) fake "From:" email addresses.
