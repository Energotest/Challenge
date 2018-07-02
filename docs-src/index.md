# Overview

*Design, implement, test and document a minimial working system.*

This challenge was created to check your familiarity with common concepts, standard metodologies and tools used in everyday development.

We assume you can use:

- `Google` to search for documentation
- `GNU/Linux` as primary development platform
- `git` for version control
- `bash` and standard command-line tools like `cat`, `grep`, `ps`, etc.
- terminal-based text editor like `emacs` or `vi`
- `Doxygen` for api reference documentation
- `MkDocs`, `Markdown` and `LaTeX` for general documentation
- `C++` as primary programming language (including features introduced in `C++11` and `C++14`)
- `g++` as primary compiler for `C++` (and `gdb` for debugging)
- `QtCreator` as primary IDE (and`qmake`/`cmake` to build projects)
- standard `C++` libraries like `boost` and `Qt`


!!! warning
    You should also know and understand the difference between clean and noisy code.

## General requirements

- `C++` and cross-platform
- TCP/IP communication between the library and the server
- custom protocol (application layer)
- server works as system service
- client application with graphical user interface using Qt

## Components

Following diagram shows all components.


```plantuml

  left to right direction

  database database

  component library
  component server
  component application

  server -- database

  library --- server : custom protocol

  application -- library


 ```

### Application

User is able to:

- create new event
- view all events

The user should be notified whenever new event is created on the server.

### Server

Custom designed protocol over TCP/IP. Events are created only by connected clients.

### Database

A record in the database represents an event and must have 3 fields:

- timestamp
- priority
- text

!!! note
    You can use any database you like but it must be available for all major platforms (including embedded GNU/Linux).

# Final notes

The challenge is intentionally loosely defined.
You are free to use time-series database instead of relational database if you wish.
You can implement authentication and/or authorization.
You can add support for syslog on unix platforms.
You can add encryption layer to the protocol.
You can use some serialization framework like protocol-buffers to implement the protocol or maybe you wish to define it in EBNF and implement a parser with boost::spirit.
It is up to you.
Show us what you can do in reasonable short time.

If you have any questions regarding this challenge, please send mail directly to: pmason@energotest.com.pl.
