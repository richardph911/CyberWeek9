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

Vulnerability #1: Insecure Direct Object Reference

Description:
- From the Find a Salesperson tab https://35.184.234.47/red/public/salesperson.php?id=X, if we enter id = 10 or 11 will display two people that they won't be found in the list. If we change id to other numbers such as 12, 13 then it will redirect to Find a Salesperson page.

<img src="https://recordit.co/BSUs3L4ZLI.gif">

Vulnerability #2: Cross-Site Request Forgery

Description:

- In the Saleperson section, we can edit and update the changes even when we edit csrd_token value from the inspect element form. On the other hand, an invalid request error will display when we try to edit info from green and blue Globitek webpage.

<img src="https://recordit.co/pMMsIbCo7c.gif">

Bonus Objective 2: Build on Objective #4 (XSS)

Description:
- a. By typing <script>document.location="https://www.facebook.com"</script> in Feedback textfield and going to the Feedback under the Staff Menu, it should direct us to the new url for example Facebook page that we provided in the script. 
- b. <script>alert(document.cookie)</script> to read cookie data
- c. <script>document.cookie="username=abcde"</script> to set cookie data.

<img src="https://recordit.co/KCo3sK0PUS.gif">



## Notes

Describe any challenges encountered while doing the work
