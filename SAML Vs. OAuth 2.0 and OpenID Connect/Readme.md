# Security Assertion Markup Language (SAML) Vs. OAuth 2.0 and OpenID Connect (OIDC)

![SAML Vs. OAuth 2.0 and OpenID Connect](https://miro.medium.com/v2/resize:fit:720/format:webp/1*9MhaHdmekqumuAuu7Js0uA.jpeg)

We previously discussed [Security Assertion Markup Language (SAML)](<https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Single%20Sign%20On%20(SSO)>), [OAuth 2.0](<https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Open%20Authorization%20(OAuth%202.0)>), and [OpenID Connect](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/OpenID%20Connect) individually. In this one, we will discuss the differences between these authentication protocols.

While [OAuth 2.0](<https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Open%20Authorization%20(OAuth%202.0)>) and [OpenID Connect](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/OpenID%20Connect) use JSON to pass the messages, SAML uses XML.

The former provides us simple and better user experience and the latter is more focused on enterprise security. This happens because [OAuth 2.0](<https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Open%20Authorization%20(OAuth%202.0)>) and [OpenID Connect](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/OpenID%20Connect) have RESTful communication to support mobile applications as well. Whereas SAML keeps a session cookie in the browser to provide the access to certain web pages which is good for short-lived workloads but not for long ones.

Further, [OpenID Connect](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/OpenID%20Connect) is simpler to implement which expands the range of use cases for it to higher levels. They are also developer friendly and can be developed from scratch at a speed with the help of freely available libraries in most common programming languages. On the other hand, SAML is complicated — both installation and maintenance-wise. Due to this reason, it is mostly enterprise-size companies that look at SAML implementation.

OpenID Connect lies on top of the OAuth framework which means it offers a built-in layer of permission that asks a user to agree about what service provider might access. However, SAML also allows consent flow with the help of hard coding carried out by a developer but not part of its protocol.

## Conclusion

These authentication protocols are better at what they do and as a developer, we need to know about our use cases and target audience before deciding on a specific protocol for the system.
