---
title: 'Application Secrets Management'
date: '2020-08-04T01:43:57+05:30'
author: 'Sam Gamare'
excerpt: 'Protect your application secrets and credentials from misuse by implementing a Vault solution, tailored to your use case.'
layout: post
image: /assets/images/icons/icon-application-secrets-management.svg
permalink: /blog/2020/08/04/application-secrets-management/
tags:
    - 'Access Control'
    - ACL
    - AWS
    - 'AWS Secrets Manager'
    - Azure
    - 'Azure Key Vault'
    - Credentials
    - Encryption
    - 'Enterprise Applications'
    - GCP
    - 'Google Secrets Management'
    - Hashicorp
    - 'Hashicorp Vault'
    - Secrets
    - Security
---
<div class="header-image-wrapper">
  <img src="/assets/images/application-secrets.png" alt="Ducks" width="90%">
</div><br>


The aim of this article is to discuss the need to secure your application secrets / credentials, understand possible solutions and how to move towards an implementation.

### **What is a secret?**

In the context of a typical application, secrets may include API tokens, certificates, local accounts, SSH keys, Git Tokens, Cloud credentials, database connection strings and domain or non-domain service accounts. Typically, such secrets are static in nature (change infrequently).

### **Why is it important to safeguard your secrets?**

All of us understand that our applications are made available to accomplish a business objective. That business objective in most cases has a monetary impact to the company. A compromised secret can at a minimum can cause the application to be unavailable. If the malicious entity has other nefarious motives, they can potentially delete your data, modify your data or even encrypt it has ask for ransom (ransomware). This invalidates the trust with your end users and may have long term effect towards your company’s credibility as a trusted secure provider of one or more services.

Bottom line its critical to ensure your secret is always well protected, and accessible only to the applications that need access based on strong ACLs, which are periodically validated.

### **Problem statement**

Applications provide service to a set of end users. Typically, a given application is part of a larger ecosystem where they need to interact with other services and databases. Historically secrets needed to connect to the other services and databases have been stored using several different mechanisms like config files within code, in version-controlled repo like GIT/TFS, in initialization time parameters, and/or in external files or databases. Most enterprises will experience the notion of “Secrets Sprawl” where secrets have sprawled all over the place with different access mechanisms. Without a consistent access control mechanism, and audit logging (who accessed the secrets when), and a streamlined location for the secrets to reside, this is a problem. These issues need to be resolved at the core, and the secrets need to be encrypted during transmission and at rest.

In today’s day of DevOps, Application Secrets Management is intertwined with automation at the core and is required to manage these secrets in several phases of a typical application’s lifecycle.

### **Typical Use Cases**

<figure class="wp-block-image size-large">![Application Secrets Management - Use Cases](https://www.gamare.net/wp-content/uploads/2020/08/ApplicationSecretsManagement-UseCases-1024x586.jpg)</figure>- Ad-hoc access for Application Administrators via a browser
- Deployment-Time: When application is deployed, it may need credentials for the target platform.
- Run-time: When application needs to get secrets/credentials to access other services like Databases, Queues, and Any-Sub-Systems at run-time, the application will need the ability to retrieve secrets and use them.


<div class="header-image-wrapper">
  <img src="/assets/images/ApplicationSecretsManagement-UseCases.jpg" alt="Application Secrets Pattern" width="90%">
</div><br>


### **Desired Traits**

- Secrets should be encrypted at rest and in transit
- Secrets should be segregated by domain or application in a multi-tenant scenario
- Secrets should be accessible through policies. Policies should be mapped to one or more sets of access channels. These could be groups in LDAP, or specific tokens that have access to that set of policies and effectively the underlying data.
- Support integrated or native capability to retrieve secrets. Example: when using platforms like Kubernetes, and PCF
- Support an API based model to store and retrieve secrets.
- Scalable
- High Availability
- Resilient to Failures
- Disaster Recovery
- Audit Tracking
- Monitoring KPI's

### **Possible Solutions**

There are several solutions that can help you achieve your goals, depending on the complexity of your application ecosystem.

[AWS Secrets Manager](https://aws.amazon.com/secrets-manager/)

AWS Secrets Manager helps you protect secrets needed to access your applications, services, and IT resources. The service enables you to easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle. Users and applications retrieve secrets with a call to Secrets Manager APIs, eliminating the need to hardcode sensitive information in plain text. Secrets Manager offers secret rotation with built-in integration for Amazon RDS, Amazon Redshift, and Amazon DocumentDB. Also, the service is extensible to other types of secrets, including API keys and OAuth tokens. In addition, Secrets Manager enables you to control access to secrets using fine-grained permissions and audit secret rotation centrally for resources in the AWS Cloud, third-party services, and on-premises

[Azure Key Vault](https://azure.microsoft.com/en-us/services/key-vault/)

 Secure key management is essential to protect data in the cloud. Use Azure Key Vault to encrypt keys and small secrets like passwords that use keys stored in hardware security modules (HSMs). For more assurance, import or generate keys in HSMs, and Microsoft processes your keys in FIPS 140-2 Level 2 validated HSMs (hardware and firmware). With Key Vault, Microsoft doesn’t see or extract your keys. Monitor and audit your key use with Azure logging—pipe logs into Azure HDInsight or your security information and event management (SIEM) solution for more analysis and threat detection

[Google Secrets Management](https://cloud.google.com/solutions/secrets-management/)

Improve security with secrets management and principles of least privilege. Plus, you can encrypt, store, secure, and manage secrets on Google Cloud with the tools you already know.

[Hashicorp Vault](https://www.vaultproject.io/)

Secure, store and tightly control access to tokens, passwords, certificates, encryption keys for protecting secrets and other sensitive data using a UI, CLI, or HTTP API.

### **How would you choose?**

The answer is “it depends on your use cases”. Here are few ways to think about it.

- If you are a company with no previous baggage, and you are hosted strictly on one of the cloud providers, you may choose to leverage [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/) / [Azure Key Vault](https://azure.microsoft.com/en-us/services/key-vault/) / [Google Secrets Management](https://cloud.google.com/solutions/secrets-management/) within that cloud platform provider. The advantages of using Vault-As-A-Service (VaaS) makes it very easy to setup and start using it. You pay for what you use and nothing more.
- If you are a company with hybrid footprint of on-premises data center and also hosted on the cloud, you may still choose to use the cloud services [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/) / [Azure Key Vault](https://azure.microsoft.com/en-us/services/key-vault/) / [Google Secrets Management](https://cloud.google.com/solutions/secrets-management/) for quick and easy setup and also take advantage of pay-for-what-you-use model.
- If you want to have 100% residency of your secrets on-premises or your corporate security policies mandate that all your secrets should reside on-premises, then you may consider leveraging a solution like Hashicorp Vault. It is also possible to host Hashicorp Vault as a service within AWS and Azure, leveraging pre-configured images, licensed through the online marketplace, or installed by you in its entirety.

With standard public cloud solutions you get instantly usable, globally scalable, resilient, and disaster recovery features out-of the-box. However if you need on-premises implementation, you have some work ahead of you to accomplish the same instantly usable, globally scalable, resilient, and disaster recovery characteristics.

Selecting the products/services is just part of the story. You must change your processes, tools, code, and support services to ensure secrets are always stored and retrieved using Vault with appropriate security controls in place.

### **Conclusion**

There are several good solutions to choose from, with effort on your part to protect your secrets. Implementing "Application Secret Management" is an important step towards improving your applications security posture.

**Disclaimer:** I have setup and used [Azure Key Vault, <u>AWS Secrets Manager</u>, and <u>Hashicorp Vault</u> ](https://azure.microsoft.com/en-us/services/key-vault/) products and am comfortable using these. Each product has its pros and cons, but they were all good enough for my use cases. I tend to gravitate towards fully scalable pay-as-you-go cloud model.