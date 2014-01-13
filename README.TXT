
Web Client Test 1.1
--------------------

Author:  Patrick J. Gleason
Date:  16-Dec-2006
Project:  Bulletron Internet Operating System 12.0
Operating System:  OS/2 Warp 4.0 and later, eComStation
Compiler:  IBM VisualAge C++ 3.0
Phone: (315) 475-5598
Email: ora68@nehemiah.idkcomp.com
Web Site: http://www.idkcomp.dom

This is a tool for analyzing, debugging and determining the correctness
of web server (HTTP) protocol.  Its primary use is testing new web
server software.  It can also be used to determine what server software
and protocol options any specific web site is using.  It can also be
used as a starting point for developing Dynamic DNS agents, credit card
transation submitters, and other miscellaneous web robots.

The program records times of protocol events and records all data, sent
or received, in both hexadecimal and ASCII formats.

To run it, at a command prompt, enter:

        WCTEST host.domain method url

where

        host    is the name of the specific computer running the web
                server (usually, "www");

        domain  is the name of the network that the host is on (for
                example, "google.com");

        method  is one of: "OPTIONS", "GET", "READ", "POST", "PUT",
                "DELETE", "TRACE" or "CONNECT" (usually "GET");

        url     is the name of the file to fetch from the server,
                including a question mark and parameters, if
                appropriate.  Use "/" to specify the server's
                default home page.

As the program runs, it records events and data in a file named
"WCTEST.LOG".  This is a plain, ASCII text file that you can print or
study with whatever text editor you prefer.

A typical example of program use is in a command file named "WCT.CMD".
This example gets the Google home page.  The results of this are in
the included "WCTEST.LOG" file.

I compiled this for OS/2 Warp 4.0 and up, using IBM VisualAge C++ 3.0.
You could fairly quickly adapt it for Linux or Windows using GCC, but
will have to rewrite the thread handling for POSIX instead of OS/2,
which might take half an hour.  For some sockets implementations, calls
to soclose() and so_cancel() have to be replaced with close(), which
does the same thing though less elegantly.

If you have IBM VisualAge C++ installed on an OS/2 system and want to
build this program, then

        C.CMD   compiles it

        L.CMD   links it

I've never cared much for the grammar of MAKE files.

