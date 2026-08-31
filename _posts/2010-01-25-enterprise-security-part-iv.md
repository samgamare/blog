---
id: 66
title: 'Enterprise Security – Part IV – Web Application Security'
date: '2010-01-25T18:34:00+05:30'
author: 'Sam Gamare'
excerpt: 'In this series of application design and security, protecting our  applications for malicious attacks.'
layout: post
guid: 'http://ec2-54-197-9-10.compute-1.amazonaws.com/?p=38'
permalink: /blog/2010/01/25/enterprise-security-part-iv/
image: /assets/images/icons/icon-enterprise-security-part-iv.svg
tags:
    - Applications
    - Attack
    - DAST
    - Database
    - DDoS
    - 'Encryption Encrypted Communication Security'
    - 'Enterprise Applications'
    - 'File System'
    - Firewall
    - OS
    - 'Port Scanning'
    - Security
    - 'Session Hijacking'
    - 'Social Engineering'
    - 'SQL Injection'
    - SSO
    - 'User Access'
    - 'Web Application Firewall'

---
<div class="header-image-wrapper">
  <img src="/assets/images/enterprise-security.png" alt="Enterprise Security" width="90%">
</div><br>

---

Continued from previous blog [Enterprise Security – Part III – Validate the client (with certs)](/blog/2009/11/17/enterprise-security-part-iii/)

One of the core requirements for any financial application is to ensure that the code can stand up to abuse from potential hackers. If not hackers, even the plain old script kiddies who just want to play with you need to be kept at bay.

So what are the different aspects we should watch for and how can we solve those. Some of the many to consider are:

**1. SQL Injection – User input field validation**.

A user input field can quickly and easily be abused to make your application validate a invalid user to returning your customer list to that hacker. Using special characters a input field can be manipulated such that the underlying code when executed would return something you did not expect.

Example: In a search for products on sale, the customer types in part of the product name. In the backend the code applies that value and constructs a dynamic query to lookup those products. A con user could trick the system into returning products which are not yet active.

Normal search for product name like “cotton candy”

SELECT \* FROM product\_table WHERE ProductName like ‘%cotton candy’ AND product\_launch\_date &gt; GetDate()

Devious search to obtain other products inserts search for cotton candy with special single quotes AND 1=1

which effectively could become

SELECT \* FROM product\_table WHERE ProductName like ‘%cotton candy’ AND 1=1 AND product\_launch\_date &gt; GetDate()

**Fix:**

The fix to this is possible with security conscious approach.

1\. Instead of passing bare strings to fit dynamic SQL, pass these as bind variables through stored procedures.

2\. Ensure every piece of data is valid from a data type and length perspective.

3\. Strip the data of any invalid characters before passing to the database layer.

**2. Cross Site Scripting**

This is a sophisticated form of attack where the malicious user injects code into your web page by passing arguments which may change the way the page is displayed back to the browser and initiated abnormal processing on the server side.

The manipulated URL (which may be hex coded to) may be sent to a innocent user and when he/she clicks it the details of that user’s credentials could be posted to another location as the malicious script executes on the actual financial application.

There are tons of tools on the market that would do these automated checks for you during development and even run silent checks on production systems – but nothing beats the right coding design, standards and practices.

Please review the series with :


– [Enterprise Security](/blog/2009/03/27/enterprise-security-part-0/)

– [Login Validation](/blog/2009/11/17/enterprise-security-part-i/)

– [Validate the server](/blog/2009/11/17/enterprise-security-part-ii/)

– [Validate the client](/blog/2009/11/17/enterprise-security-part-iii/)

– [Web Application Security](/blog/2010/01/25/enterprise-security-part-iv/)
