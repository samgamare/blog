---
id: 65
title: 'Enterprise Security – Part II – Validate the server'
date: '2009-11-17T18:32:00+05:30'
author: 'Sam Gamare'
excerpt: 'In this series of application design and security, verifying the identity of the server for our applications with public/private certs.'
layout: post
guid: 'http://ec2-54-197-9-10.compute-1.amazonaws.com/?p=36'
permalink: /blog/2009/11/17/enterprise-security-part-ii/
image: /assets/images/icons/icon-enterprise-security-part-ii.svg
tags:
    - Applications
    - Attack
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

Continued from previous blog [Enterprise Security – Part I – Login Validation](/blog/2009/11/17/enterprise-security-part-i/)

Certificates are used for a variety of implementations to secure communication from any non intended third party. In this case we are discussing the most generic of the certificates commonly known – server based SSL (secure socket layer) certificate. The purpose of the certificate is to prove beyond doubt that the server is who we think it is. This kind of security is generally setup to work on a security port – usually tied to port 443 (note – it does not have to be) and supported by the browser as “https”; an extension to the standard http protocol.

When a request is initiated for a secure https based website, the website responds with a certificate signature which identifies who it is. The browsers by means of setup root certificate authority (the list of root security certificates is pretty limited), are able to verify the signature provided so we can be sure that the data that is passed from the client browser to the server is encrypted and not pry to any prying eyes.

Various aspects related to corporate root certificate authority, and secure communication based on SSL would be a good read.

Please review the series with :


– [Enterprise Security](/blog/2009/03/27/enterprise-security-part-0/)

– [Login Validation](/blog/2009/11/17/enterprise-security-part-i/)

– [Validate the server](/blog/2009/11/17/enterprise-security-part-ii/)

– [Validate the client](/blog/2009/11/17/enterprise-security-part-iii/)

– [Web Application Security](/blog/2010/01/25/enterprise-security-part-iv/)


Follow the next blog at [Enterprise Security – Part III – Validate the client (with certs)](/blog/2009/11/17/enterprise-security-part-iii/)