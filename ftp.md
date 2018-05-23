#### FTP

FTP is short for File Transfer Protocol. A protocol is a set of rules that
networked computers use to talk to one another. And FTP is the language that
computers on a TCP/IP network (such as the internet) use to transfer files to
and from each other.

- The FTP protocol is handled by ports 20 and 21 by default

- Anonymous is never really anonymous as far as anonymous FTP is concerned.

- File transfers over FTP take two different forms, ASCII and binary.

- HTTP essentially fixes the bugs in FTP that made it inconvenient to use for
  many small ephemeral transfers as are typical in web pages.

- Data transfer can be done in any of three modes:
  - Stream mode: Data is sent as a continuous stream, relieving FTP from doing any
  processing. Rather, all processing is left up to TCP. No End-of-file indicator
  is needed, unless the data is divided into records.
  - Block mode: FTP breaks the data into several blocks (block header, byte
    count, and data field) and then passes it on to TCP.
  - Compressed mode: Data is compressed using a simple algorithm (usually
    run-length encoding). Some FTP software also implements a DEFLATE-based
    compressed mode, sometimes called "Mode Z" after the command that enables
    it. This mode was described in an Internet Draft, but not standardized.
