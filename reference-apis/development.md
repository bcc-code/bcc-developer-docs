---
description: 'For the purpose of development, retrieving tokens in an easy way'
---

# Development

### Description

Often during local development you need an id\_token or access token in order to run you're tests for example. This is often challenging because you need to authenticate an production user in order to get the required access tokens which means you have to expose the users credentials, which not desired. To make this process easier we deployed a dummy identity provider with reduced security and which does not required the end user to sign in in order to get the required tokens.

### Retrieve an id\_token

```text
https://localhost:5000/connect/authorize?
    client_id=Auth0&
    scope=openid email&
    response_type=code&
    redirect_uri=https://devlogin.bcc.no/login/callback&
    state=abc&
    nonce=xyz
```

