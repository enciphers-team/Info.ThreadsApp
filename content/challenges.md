+++
title = "Challenges"
date = "2020-12-16"
sidemenu = "true"
description = "A Vulnerable Web Application Lab"
+++

As we know there are many vulnerabilities present in the Threads web application so to find out and exploit each of  these vulnerabilities are the challenges on Threads application. We have categorized the vulnerabilities into 4 parts (low,medium,high,critical) on the basis of how it is going to affect your system.

**Note** : ( In order to solve the challenges hints are provided with them).
   
Here is the list of all the challenges according to the severity category to solve and practise:


## Low 

### XSS(Self-XSS)

**About**: [Self-xss](https://portswigger.net/web-security/cross-site-scripting/reflected) has the behaviour similar to Reflected XSS however it can not be executed with simple ways like Url Crafting, Cross domain request.In this victim themself submit the xss payload (javascript code) in their browser that means you/victim yourself can exploit only. So in order to exploit this vulnerability as an attacker you need to convince the victim to submit/paste the javascript code in the browser (which is not simply not possible). Hence it is considered as a low vulnerability until unless chaining with other vulnerabilities like CSRF. 

Reference to Learn more:[Self-Cross Site Scripting](https://portswigger.net/web-security/cross-site-scripting/reflected) 


### Hidden Directories

**About**: Sometimes Application has hidden directories which are not visible on a public website and these can reveal useful information for potential attacks. Hidden Directories can be found via brute force using a wordlist.


### No Password Policy

**About**: Sometimes the  application does not require that users should have strong passwords,  which makes it easier for attackers to compromise user accounts. There are many password policy followed by many application like:
  - use of both upper-case and lower-case letters (case sensitivity).
  - inclusion of one or more numerical digits.
  - inclusion of special characters, such as @, #, $.
  - prohibition of words found in a password blacklist.
  - prohibition of words found in the user's personal information.
  - prohibition of use of company name or an abbreviation.
  - prohibition of passwords that match the format of calendar dates, license plate numbers, telephone numbers, or other common numbers.

When all these policies are followed by the application then it becomes tough for attackers to get password for a user account. 

Reference to Learn More:[No password policy](https://en.wikipedia.org/wiki/Password_policy)


### Weak Reset Password Implementation

**About**: Password reset functionality is performed within the application,so when passwords are reset they are either rendered within the application or emailed to the user. Many of times the application doesn't allow to reset the password as the old password which was already used which comes under good password policy.

Reference:[Weak Reset Password implementation](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/04-Authentication_Testing/09-Testing_for_Weak_Password_Change_or_Reset_Functionalities)

### Automatic User Enumeration

**About**: In many application while logging in if we put any one of the credentials wrong  then it shows error message that your password or emailID is invalid or wrong but in some cases it tells you specifically which one of the credential is entered incorrectly because of which an attacker can get to know which credential he has to bruteforce to enter as the other user.     

### No password required for account deletion

**About**: In many application it doesn't ask for password before deleting account. If someone leaves his account open in some office,cafe,library then any  intruder can come and try to delete the user's account. Intruder can easily delete the account because the system did not protect it by asking the password to validate that the person deleting the account is the real user.

### Simultaneous sessions are being kept active on the same browser 

It's a common request or recommendation that a web application not allow a user to have more than one session active at a time. In other words, after a user logs into an application, he should not be permitted to open a different type of browser (or use another computer) to log in again until his first session has ended.

## Medium 

### No rate Limiting

**About**: [No Rate limiting](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html#rate-limiting) Application or Server does not keep any restriction on sending the request from one client to server or web-application in a particular time frame which can cause problems to web applications/server. And bad people can perform DDos attacks by creating unusual traffic to server/web applications.

 Reference to learn more:[No Rate limiting](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html#rate-limiting)


### Failure to invalidate the session after password change

**About**: In many application once a user changes his password then the application directs him to login page and end his session from everywhere wherever his account was open (on different computers, mobiles). This is a good way to secure user information. 

### Clickjacking

**About**: Clickjacking is an attack that tricks a user into clicking a webpage element which is invisible or disguised as another element. This can cause users to unwittingly download malware, visit malicious web pages,provide credentials or sensitive information, transfer money, or purchase products online.

Reference to Learn more: [Clickjacking](https://owasp.org/www-community/attacks/Clickjacking)

### Bruteforce of password leading to account takeover

**About**: If the Password policies are not followed by the application strictly then it gets very easy to get an user password which can be done by bruteforcing with the Help of BurpSuite.

## High

### Insecure Direct Object Reference

**About**: An insecure direct object reference [(IDOR)](https://portswigger.net/web-security/access-control/idor) is an access control vulnerability. Which occurs when unvalidated input is used to reference or access an object by using an unique ID. If by changing ID the attacker can access the details/object which should not be accessible, it's an IDOR. 

 Reference to learn more:[Insecure Direct Object Reference](https://portswigger.net/web-security/access-control/idor)

**Note**: There are two IDOR present in the application.

### Server-side Request Forgery(SSRF)

**About**: In a Server-Side Request Forgery [(SSRF)](https://owasp.org/www-community/attacks/Server_Side_Request_Forgery) victim server makes the http request on the behalf of the attacker to some other mentioned server by the attacker.

 Reference to learn more:[Server-side Request Forgery](https://owasp.org/www-community/attacks/Server_Side_Request_Forgery)

**Note**: There are two SSRF present in the application. one of which is a blind SSRF


### XSS(Stored XSS)

**About**: [Stored xss](https://portswigger.net/web-security/cross-site-scripting/stored) occurs when the application processes and stores untrusted data (malicious javascript) at the server side and includes that data in later http response in a unsafe way which can triggers the malicious javascript as input to application.

 Reference to learn more:[Stored-Cross Site Scripting](https://portswigger.net/web-security/cross-site-scripting/stored) 

**Note**: There are two Stored XSS in the application.

### Chaining of IDOR with XSS

**About**: We can input XSS payload while doing an IDOR attack. These both attacks combined can be too dangerous. Usually as we perform IDOR attack this Attack is also performed in the same way all we have to do is input the xss payload instead of some random input in this to change some credentials like (name,mail, password,bio etc) of the other users account via IDOR. 

## Critical   

### JWT Authentication

**About**: JWT(JSON Web Token) are used for authentication and A statement from “RFC 7518 (JSON Web Algorithms) states that "A key of the same size as the hash output (for instance, 256 bits for "HS256") or larger MUST be used with this algorithm. Because shorter can be brute forced this is the one of the weak points that can occur while implementing jwt.

 Reference to learn more:[JSON Web Token](https://jwt.io/introduction/)

**Note**:  For JWT challenge, hardcoded email is ‘admin@threadsapp.co.in’. So first make  an account with  the given email id and then try to forge the token.

### NoSQL Injection

**About**: It is a vulnerability which can be found in databases such as MongoDB which don't run on Sql queries. In this attacker injects a payload where the application asks for user provided data for example, a web page may request user account credentials in a web form, store authentication information in a MongoDB database, and perform credential checks using JavaScript.

Reference to Learn more: [NoSQL Injection](https://owasp.org/www-pdf-archive/GOD16-NOSQL.pdf)

These are all the challenges present on Threads application which you can solve.
Happy learning,Happy hacking!
 

