---

title: 'Enterprise Security'
date: '2009-03-27T16:22:00+05:30'
author: 'Sam Gamare'
excerpt: 'An application architects thoughts on how security should be thought of and designed for enterprise applications.'
layout: post
permalink: /blog/2009/03/27/enterprise-security-part-0/
image: /assets/images/icons/icon-enterprise-security-part-0.svg
categories:
    - Uncategorized
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
  <img src="/assets/images/enterprise-security.png" alt="Ducks" width="90%">
</div><br>

---

Enterprise Application Security is indeed a broad topic subject to different levels of definition and interpretation, per system needs. Security needs for top secret Department of Defense projects would be lot different from the security required for an ecommerce application which intends to sell to the consumer. Having worked with different Enterprise Applications across a wide variety of industries, I prefer to look at security holistically with multiple perspectives. As a rule of thumb the more intense the security needs, the higher the cost of the entire implementation.

From an architecture layer perspective some of aspects to be considered are :

\* **User Access security –** These include two factor and three factor access mechanisms driven by passwords, Biometrics, Single Sign On (SSO), Kerberos and various other mechanisms.  
\* **Web Server security** – HTTPS/SSL to encrypt communication between client and server. A mechanism without which most of today’s ecommerce based business on the internet would not exist to this advanced degree. The web server account itself should be a non-Admin level account setup to run within a boxed environment. Communication from the web server to the application server can be encrypted using SSL as needed. Security setup on Microsoft IIS is slightly different from Apache. The integrated support offered by IIS is difficult if not painful to achieve with Apache.  
\* **Application Server security** – The application server has to be running with a non-privileged non-admin account. The application servers have the capability to allow certain types of users based on group criteria. For example: IIS will allow us to define the domain users that are allowed for a certain site based on domain. IIS will allow us to setup impersonation accounts for anonymously access accounts, and so on. Usually the application server will validate the users, based on database/LDAP or other security models. The communication from the application to the database and/or LDAP and other systems can be encrypted using SSL on an as needed basis.  
\* **Database security** – Integrated login versus explicit login. The permission model can be based on windows groups and/or database groups. Complex web applications will provide granular application level security based on application level groups, and permissions per field type. Trusted / Integrated access support by Microsoft SQL Server is a addon but non generic implementation compared to other databases like Oracle, DB2 and others.  
\* **OS Group level security** – OS groups can be used at various levels nested through the web/application server level in conjunction with the file system group allocations in place.  
\* **File system level security** – Protecting the file system on the server is generally left to the level of generic access to everyone who can gain access to the machine. On Microsoft Windows (NT, 2000, 2003, 2008) machines this is NTFS access, while on Unix/Linux (HP UX, Solaris, Ubuntu, Debian, others) based infrastructure this is driven by rwx privileges per user, group and public. File system security access can be detrimental if the box is compromised. Explicit security and encryption can offer great level of protection at this level.  
\* **Proprietary security implementations** – Example the account required to modify the cacert for java based application server or the windows system level privilege requirement which is not even available to windows Administrator users, unless modified by local/Domain group policies through Microsoft Active Directory.

**From an Attack Perspective:**

\* SQL injection  
\* Session Hijacking  
\* Denial of Service  
\* Social engineering to obtain fraudulent credentials  
\* Port scanning  
\* Firewalls  
\* Encryption over the wire

**From a Physical perspective**:

\* Physically securing the location of your infrastructure is crucial to security.  
\* Storage encryption mechanisms to protect data if someone can get access to the data.  
\* Disaster Recovery procedures to quickly address issues related to physical outages in terms of location inaccessible due to massive power failure, fire, floods, and other hazards.

In the following weeks we shall dissect each aspect of security to dive deeper into understanding issues with today’s Enterprise Application Security.

Please review the series with :

– [Enterprise Security](/blog/2009/03/27/enterprise-security-part-0/)

– [Login Validation](/blog/2009/11/17/enterprise-security-part-i/)

– [Validate the server](/blog/2009/11/17/enterprise-security-part-ii/)

– [Validate the client](/blog/2009/11/17/enterprise-security-part-iii/)

– [Web Application Security](/blog/2010/01/25/enterprise-security-part-iv/)

Follow the next blog at [Enterprise Security – Part I – Login Validation](/blog/2009/11/17/enterprise-security-part-i/)