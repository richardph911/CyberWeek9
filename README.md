# Project 8 - Pentesting Live Targets

Time spent: **6** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQL INJECTION

Description:
- By editing the session id from the url in the form of ?id=' OR 1=1'--, the page redirects to "Database query failed". It means there is SQLI vulnerabiltiy occurred for both blue and red section. 

<img src="https://recordit.co/PB2sNiIda3.gif">

Vulnerability #2: Session Hijack/Fixation
Description:
- Using Firefox to login to the blue Globitek page. Then go to public/hacktools/change_session_id.php to get the session id. 
- Open Chrome and go to public/hacktools/change_session_id.php and change the default session id by the one we got from Firefox. We can login without using our account.

<img src="https://recordit.co/4Amiidazq0.gif">

## Green

Vulnerability #1: Username Enumeration

Description:
- When I trying to login using an incorrect username, the inspect class shown "failed" compared to "failure" if using the correct username such as jmonroe99. Plus, the text message will be bold to the correct username account. 
<img src="https://recordit.co/z8n3yqChZ5.gif">

Vulnerability #2: Cross-Site Scripting

Description:
- Go to the Contact Us page, enter a random name and email then type  <script>alert('Richard found the XSS!')</script> for the feedback. Next, go to Feedback section and the alert "Richard found the XSS!" will appear. 

<img src="https://recordit.co/uiNp7MjSh5.gif">


## Red

Vulnerability #1: __________________

Description:

<img src="red-vuln1.gif">

Vulnerability #2: __________________

Description:

<img src="red-vuln2.gif">


## Notes

Describe any challenges encountered while doing the work
