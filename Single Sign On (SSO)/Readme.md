# Single Sign On (SSO)

![Single Sign On (SSO)](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*lnPlenRVVA3QK1OL2vmFZQ.jpeg)

SSO — Single Sign On is an authentication process where a user can access multiple applications using a single set of credentials. It helps the user not to have to log into numerous applications separately. There is a centralized system that stores the user credentials called Identity Provider (IdP). The IdP is a trusted system that provides the access to other different websites and applications.

We can see SSO-based systems in enterprise environments because the people involved in them need to access various applications and systems simultaneously.

## Components of SSO

### Identity Provider (IdP)

All the information related to the user is managed by the centralized service called Identity Provider (IdP). In addition, the IdP verifies the user and authenticated them so they can get into the service provider. The user can automatically authenticate with a username and password validation or by validating an assertion about the user detail presented in a separate identity provider.

Moreover, it also manages those data so the service provider wouldn’t have to think about it. Some common examples of the IdPs are Okta, Google, Autho, OneLogin, etc.

### Service Provider

This provides service to the end-user and relies on identity providers to maintain the user identity. Further, there are local accounts for the user with attributes unique to the service provider.

### Identity Broker

Moving on, we have an identity broker — an intermediate system to connect multiple service providers with the identity providers. The identity brokers let you use SSO on any application without unnecessary protocols.

## SAML

Standing for Security Assertion Markup Language, SAML is an open standard for clients to share security information related to identity, authentication, and permission across multiple systems. It uses XML — Extensible Markup Language for data sharing and enables identity federation so the IdPs would easily pass the authenticated identities and attributes to the service providers.

## How does SSO work?

1. The user opens the application and sends the requests for resources.

2. The user is redirected to Identity Providers (IdP) for authentication.

3. The user signs in to the application.

4. IdP sends an SSO response to the application.

5. Access is granted.

![SSO](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*JT8d1Y4Wbr2OqVl35bzvnw.jpeg)

## Advantages of SSO

- Users can remember only one set of credentials.
- Users don’t have to go through a lengthy authorization process.
- Sensitive data are protected with security and compliance enforcement.
- IT support costs and admin time is lessened with management simplification.

## Disadvantages of SSO

- Every application needs to request an SSO provider for verification each time making it slower than the traditional authentication process.
- There is a single password which if compromised in one single application, all the other applications are sure to be compromised.
