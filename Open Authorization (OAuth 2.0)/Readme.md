# Open Authorization (OAuth 2.0)

![Open Authorization](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*MDikMrGgdJwA89aU4xXyZg.jpeg)

OAuth 2.0 is an authorization protocol that provides consented access to the available resources on behalf of the user. No user credentials are ever shared with the Open Authorization since it provides the access to the resources such as remote APIs, user data, etc. To note, OAuth 2.0 is only an authorization protocol but no authentication protocol.

## Concepts of OAuth 2.0

- **Resources Owner** — The owner of protected resources who can provide the access to them.
  Client — The one who requires access to the resources.

- **Authorization Server** — The one to receive a request from the client to get an Access Token. It even issues the tokens to authenticate and consent by the Resource Owner.

- **Resource Server** — Protects the resources and gets the access requests from the client to accept and validate an Access Token and return the resources as required.

- **Scopes** — Specifies the reason why the resources need to grant. It depends on the Resource server for values and related resources.

- **Access Token** — Data token with authorization to access the resources on the behalf of the client.

## How does OAuth 2.0 work?

1. The client places an authorization request to the Authorization Server with the client ID. There are scopes and an endpoint URI to send the Access Token.

2. The Authorization Server verifies if the requested scopes are allowed while also checking the authenticity of the client.

3. The Authorization Server works with Resource Owner to grant access to the scopes.

4. The Authorization Server directs back to the client with Access Token according to the type of grant. We can also expect a Refresh Token.

5. The client can use the Access Token to request access to the resources from the Resource Server.

![Open Authorization](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ClH9ReTIL8qH2_obuH60yQ.jpeg)

## Does OAuth 2.0 have any disadvantages?

There are a few disadvantages to using OAuth 2.0. Let’s list them out: -

- There are no built-in security features.
- You cannot get a common set of scopes.
- There is no standard implementation.
