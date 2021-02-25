---
description: 'For the purpose of development, retrieving tokens in an easy way'
---

# Development

### Description

Often during local development you need an id\_token or access token in order to run you're tests for example. This is often challenging because you need to authenticate an production user in order to get the required access tokens which means you have to expose the users credentials, which not desired. To make this process easier we deployed a dummy identity provider with reduced security and which does not required the end user to sign in in order to get the required tokens.

### Retrieve an id\_token

```text
https://localhost:5000/connect/authorize?
    client_id=RandomUser&
    scope=openid email&
    response_type=token code&
    redirect_uri=https://localhost/login/callback&
    state=abc&
    nonce=xyz
 
// To copy and past  

https://localhost:5000/connect/authorize?client_id=RandomUser&scope=openid email&response_type=code id_token token&redirect_uri=https://localhost/login/callback&state=abc&nonce=xyz


```

Notice the following

* Normally the redirect uri had to be registered on the client in the identity provider config. With the dummy server this is not a requirement, you can specify any redirect uri at will
* The client\_id is set to "RandomUser", this means you would get back tokens for a random user, this is often useful for load testing. If you would like always get the same user back set the client\_id to "SameUser"

