# Project 8 - Pentesting Live Targets

Time spent: ** 6 ** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection(SQLi): Most of the data input received by these websites is being sanitized properly. However, one of the three sites has one place where the input is not being sanitized before being used in an SQL query. Determine which color has the vulnerability.

GIF Walkthrough: ![alt text](https://github.com/Sudeepti-S/CodePathWeek8/blob/master/Blue_2.gif)


Vulnerability #2: Session Hijacking/Fixation:: Two of the three websites expire their active sessions and require users to re-login every 30 minutes. That is probably too aggressive for the real world, but it is better than the third site which allows sessions to be a year old, and never regenerates the session ID, even when the user agent string changes. This makes it vulnerable to both session hijacking and session fixation attacks.

GIF Walkthrough: ![alt text]()

## Green

Vulnerability #1: Username Enumeration: A careless developer mistake has created a username enumeration vulnerability. Determine which color has the vulnerability. You can use the existing username "jmonroe99" as a test(I used pperson as an existing username since I was provided with that one). Next, figure out what mistake the developer made. The developers  included two different failure messages for existing account vs non-existing accounts. 

GIF Walkthrough: ![alt text](https://github.com/Sudeepti-S/CodePathWeek8/blob/master/Green_UE.gif)

<img src='2.png' alt="failed png"/>
<img src='1.png' alt="failure png"/>


Vulnerability #2: Cross-Site Scripting (XSS): All three sites do a good job of protecting against a reflected XSS attack. However, one of the sites has a mistake which leaves the site vulnerable to a stored XSS attack. A reflected XSS attack would be easy to reveal, while a stored XSS does not provide instant feedback. You will need to log into the admin area and look through the CMS in order to "spring the trap" and find out if your attack succeeded. Determine which color has the vulnerability. Use your name in the XSS so that your results won't be confused with anyone else's (example: <script>alert('Mallory found the XSS!');</script>).

GIF Walkthrough: ![alt text](https://github.com/Sudeepti-S/CodePathWeek8/blob/master/Green_1.gif)


## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR):One of the three sites is missing code which would prevent some sensitive information from being made public. Determine which color has the vulnerability. Then, figure out what the other two sites did correctly to prevent the information leak.

GIF Walkthrough: ![alt text]()

Vulnerability #2: Cross-Site Request Forgery (CSRF): One of the three sites does not have CSRF protections on the admin area. A clever attacker could design a form which would automatically submit form data to the staff area and take advantage of a logged in user's access permissions. Be the attacker and design a form which will make a change to the spelling of some database content. (For example, change the first user from "James" to "Jim", or change "Alabama" to "Alabamaaaa".) Then point the form action at each of the three sites to find out which color has the vulnerability. Do not neglect to be stealthy with your form—your unsuspecting, logged-in admin should neither see the form nor the results of the form submission.

GIF Walkthrough: ![alt text]()


## Notes

Describe any challenges encountered while doing the work
