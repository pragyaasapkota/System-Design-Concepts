# OpenID Connect

![OpenID Connect](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*PIMbmT4FrFciLy2K0GdQgA.jpeg)

Previously, we talked about [Open Authorization (OAuth 2.0)](<https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Open%20Authorization%20(OAuth%202.0)>).

While the Open Authorization was designed to provide access to data and features between applications, OpenID Connect adds login and profile details about the client who logs in. To note, OpenID Connect lies at the top of [OAuth 2.0](<https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Open%20Authorization%20(OAuth%202.0)>).

The Authorization Server is responsible for the OpenID Connect (OIDC) and hence is also known as Identity Provider (IdP). It also relays the information about the Resource Owner to the client and not only one way around. The best thing about OpenID Connect is that it leads us to lower adoption and industry implementation of best practices compared to OAuth.

## Concepts of OpenID Connect

- **Relying Party** — The current application.
- **OpenID Provider** — Service that gives a one-time code to the relying party.
- **Token Endpoint** — Web Server that accepts OTC — One Time Code and provides an Access Code with an hour of the time limit. In OpenID Connect, the token is granted by JWT — JSON Web Token.
- **UserInfo Endpoint** — The Relying Party interacts with User Info Endpoint with a secure Token that helps receive information about the end user.

## Conclusion

OpenID Connect and OAuth 2.0 are both very easy to implement. Both are JSON-based and supported in most web and mobile applications. While comparing, OpenID Connect has more strict configurations and specifications than [OAuth 2.0](<https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Open%20Authorization%20(OAuth%202.0)>).
