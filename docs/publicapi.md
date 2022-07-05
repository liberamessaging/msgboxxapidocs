---
title: Public API
layout: default
---

Welcome to the msgboxx Public API documentation.

The msgboxx api is a restful api with the endpoints arranged around the core concepts on an api account, contacts, inboxes, messages and broadcasts, all secured by JWT authentication.

The full swagger documentation of all api endpoints inputs and outputs is available <a href="https://developer.msgboxx.io">here</a>

Before you can use any of our public API endpoints you will need to get a Bearer token from our authentication endpoint. All authentication is on the basis of a msgboxx user and the permissions you get in the api are exactly the same as if the user logged directly into the msgboxx platform. 

To obtain a JWT token perform a HTTP post against the Auth endpoint.
POST https://api.msgboxx.io/oauth/token
with the following body
{
  "username": "myuser@domain.com",
  "password": "mypassw0rd!"
}

Upon a successful login you will receive the following response.
HTTP 200 OK
{
  "access_token": "string",
  "token_type": "string",
  "scope": "string",
  "expires_at": "string"
}

the string in the access_token field is your Bearer token and is required to be passed to all subsequent calls. 

