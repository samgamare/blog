---
title: 'Enterprise Security – Part I – Login Validation'
date: '2009-11-17T16:31:00+05:30'
author: 'Sam Gamare'
excerpt: 'In this series of application design and security, here is the basic one to start with for Authentication patterns for our applications.'
layout: post
permalink: /blog/2009/11/17/enterprise-security-part-i/
image: /assets/images/icons/icon-enterprise-security-part-i.svg
categories:
    - Uncategorized
tags:
    - Applications
    - Attack
    - Authentication
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

Continued from previous blog [Enterprise Security](/blog/2009/03/27/enterprise-security-part-0/)

Most of you at some point in your career may have setup a local web server installation and probably published articles and pictures using web servers. However here we are talking about a more than the generic setup; we will describe a basic enterprise application centric security setup.

When coupled with a typical windows environment, IIS can offer a very powerful security setup. The following factors come down to NTFS permissions, directory security, form based security, SSL certificates, along with impersonation and services / port lockdown. IIS offers multiple types of security setup when it comes to web access. The following scenarios describe various security setup with the description of how they are likely setup and how they are used.

**Login Validation**: A client accessing the web site through HTTP (generally port 80 – can be different) can be offered “anonymous” access, similar to what most of us experience when we go to most http based web sites. When it is necessary to lock down the usage such that only registered users are able to access the content, directory security is enabled and anonymous access is disabled. You can only login if you enter valid “windows domain based login credentials”, and all content and documents within this website are secure from generic prying. This type of security setup is also called NTLM challenge response based login validation. This is commonly employed within inside and outside of corporate network boundaries.

Another form login validation is called form based security, a choice supported by using a .NET application with form based security. The way it works is when declared correctly in web.config IIS detects validation cookie with every request. In the absence of that cookie, IIS forces the user into a web form which explicitly prompts the user for credentials. The form when submitted generates a underlying windows ticket and ties it back to the secure cookie which is posted back in response to the user request. All further requests from the same client to the website now enjoy secure login and access to other resources available.

Please review the series with :

– [Enterprise Security](/blog/2009/03/27/enterprise-security-part-0/)

– [Login Validation](/blog/2009/11/17/enterprise-security-part-i/)

– [Validate the server](/blog/2009/11/17/enterprise-security-part-ii/)

– [Validate the client](/blog/2009/11/17/enterprise-security-part-iii/)

– [Web Application Security](/blog/2010/01/25/enterprise-security-part-iv/)


Follow the next blog at [Enterprise Security – Part II – Validate the server](https://www.gamare.net/blog/2009/11/17/enterprise-security-part-ii/)