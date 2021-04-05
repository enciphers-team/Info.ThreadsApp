+++
title = "About Threads"
date = "2020-12-16"
sidemenu = "true"
description = "A Vulnerable Web Application Lab"
+++

It’s a NodeJs based application and it has also uses EJS as a frontend development templating engine with bootstrap and a mix of simple HTML, CSS is used to build this web application.

This web application comes up with various web application vulnerabilities just like some real web applications have and these vulnerabilities are the challenges on this web application which  need to be solved by its users. So this application acts as a vulnerable web lab where users can have hands-on practice on the different vulnerabilities present in it.  

It  consist of  various features like:

* A user can sign up and create his account  in this application.Then he can Login to the Threads application via Login page.
* A user can create posts, he/she can also add images to the post he/she creates. 
* A user can also tag other users present on this application in his posts.
* A user can like, comment on other users posts.
* A user can share and bookmark other users post.
* A user can also chat with other users in the group chat section.
* A user can follow another user and also  can get followed by other users.
* A user has to enter his Aws credentials in the config.env file to upload a post containing an image.
* You can add 25 dummy users to the application by entering 'yes' while installing the application.
* A user can delete his account after which all information  like his post,bookmarks,likes,comments,following,followers will get deleted.
* Profile section has bio field where you can write about yourself.

The idea behind ThreadsApp is to create something which is a go to app, for starting with Web App security. The idle use of this app would be: 

+ Using the local setup of lab to start with basic web app security learning
+ Using the ThreadsApp in basic web hacking trainings

To make the application a good start for beginners, we have decided to include examples of all  the OWASP Top 10 vulnerabilities [**NOTE**: This release of the app, have some of the examples missing from OWASP Top 10. We will add them in future releases.]

1 Injection (present)
  - NoSQL Injection

2 Broken Authentication (present)
  - JWT

3 Sensitive Data Exposure (Working on it)
  
4 XXE (Working/Will come in further Update)

5 Broken Access Control (present)
  - IDOR
  - SSRF
 
6 Security Misconfiguration 
  - Present in the form of rate limits on the comment section.
  - No password required for account delete.
  - Clickjacking issue with sensitive action (delete account)

7 Cross-Site Scripting 
  - Stored cross Site scripting 
  - Self XSS

8 Insecure Deserialization (Will come in further update)

9 Using Component with Known Vulnerabilities (working on it)

10 Insufficient logging and monitoring (present)
  - Present in the form of two or more simultaneous sessions being kept active.




Learn more on [Github](https://github.com/enciphers/ThreadsApp).

Have questions or suggestions? Feel free to [open an issue on GitHub](https://github.com/enciphers/ThreadsApp) or [ask me on Twitter](https://twitter.com/EnciphersLabs).

Thanks for reading!
