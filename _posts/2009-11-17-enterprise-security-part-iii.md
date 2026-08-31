---

title: 'Enterprise Security – Part III – Validate the client (with certs)'
date: '2009-11-17T18:30:00+05:30'
author: 'Sam Gamare'
excerpt: 'In this series of application design and security, verifying the identity of the client for our applications with  certificates.'
layout: post
image: /assets/images/icons/icon-enterprise-security-part-iii.svg
permalink: /blog/2009/11/17/enterprise-security-part-iii/

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

Continued from previous blog [Enterprise Security – Part II – Validate the server](/blog/2009/11/17/enterprise-security-part-ii/)

This setup is little rare to find. This is typically used in extra secure installations where the server application needs to verify the identity of the client browser who is authorized to access the application. This type of setup is generally limited to within the corporate boundary. Assume an example of a mutual fund sr. trader with access to initiate transactions in multi million dollars. In this case, in addition to login credentials based security, the company wants to ensure that this request comes from a corporate machine registered on the network which has limited applications controlled and managed per corporate standards and it is not a rogue laptop on the network.  
The setup in this case is generally a explicit client certificate which is generated using corporate certificate management engine (it might as well be a certificate from Verisign, Thawte, or any other known root provider). This certificate is registered on the client machine and setup to provide that to a specific server based website. During initial requests from the client to the website the client will provide the certificate for validation for the server to validate who he says he is. The server in this case might also be setup to provide certificate to provide who he says he is. The client might be prompted for login credentials by various mechanisms identified in Part I and Part II (on this page). This explicit handshake and login credential validation ensures that the application is being used appropriately by the right party in the correct environment, with “almost” impossible probability for a third party to hack that communication channel.

Please review the series with :

– [Enterprise Security](/blog/2009/03/27/enterprise-security-part-0/)

– [Login Validation](/blog/2009/11/17/enterprise-security-part-i/)

– [Validate the server](/blog/2009/11/17/enterprise-security-part-ii/)

– [Validate the client](/blog/2009/11/17/enterprise-security-part-iii/)

– [Web Application Security](/blog/2010/01/25/enterprise-security-part-iv/)


Follow the next blog at [Enterprise Security – Part IV – Web Application Security](/blog/2010/01/25/enterprise-security-part-iv/)