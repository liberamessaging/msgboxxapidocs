---
title: Public API
layout: default
---

Welcome to the msgboxx Public API documentation.

The msgboxx api is a restful api with the endpoints arranged around the core concepts on an api account, contacts, inboxes, messages and broadcasts, all secured by JWT authentication.

The full swagger documentation of all api endpoints inputs and outputs is available <a href="https://developer.msgboxx.io">here</a>

---

Before you can use any of our public API endpoints you will need to get a Bearer token from our authentication endpoint. All authentication is on the basis of a msgboxx user and the permissions you get in the api are exactly the same as if the user logged directly into the msgboxx platform.

To obtain a JWT token perform a HTTP post against the Auth endpoint.

`POST https://api.msgboxx.io/oauth/token`

with the following body

```json
{
  "username": "myuser@domain.com",
  "password": "mypassw0rd!"
}
```

Upon a successful login you will receive the following response.

`HTTP 200 OK`

```json
{
  "access_token": "string",
  "token_type": "string",
  "scope": "string",
  "expires_at": "string"
}
```

the string in the access_token field is your Bearer token and is required to be passed to all subsequent calls.

All of the common scenarios below require you to have obtained a bearer token above, and send it through to all API calls.

`Authorisation: Bearer mytokengoeshere`

---

# Common Scenarios

WhatsApp support two different message sending scenarios. When a customer sends a message into msgboxx a window of 24 hours is open in which you can reply with a freeform (session) messages via the Message endpoint. If the customer engages in a conversation the window extends and only closes 24 hours after the last message received from them. When the session message window is closed then you need to send a template message via the Broadcast endpoint.

## Sending a Session Messages & Broadcasts

To find out how to broadcast a message <a href="sendbroadcast">view the documentation here</a>

To find out how to send a session message <a href="sendmessage">view the documentation here</a>

## Working with API Accounts

To find out how to get all the api accounts <a href="getapiaccounts">view the documentation here</a>

To find out how to get a specific api account <a href="getapiaccount">view the documentation here</a>

## Working with Inboxes

To find out how to get all the inboxes <a href="getinboxes">view the documentation here</a>

To find out how to get a specific inbox <a href="getinbox">view the documentation here</a>

## Working with Contacts

To find out how to get all the contacts <a href="getcontacts">view the documentation here</a>

To find out how to get a specific contact <a href="getcontact">view the documentation here</a>

To find out how to add a new contact <a href="addcontact">view the documentation here</a>

## Working with Broadcasts

To find out how to get all the broadcasts <a href="getbroadcasts">view the documentation here</a>

To find out how to get a specific broadcast <a href="getbroadcast">view the documentation here</a>

To find out how to send a new broadcast <a href="sendbroadcast">view the documentation here</a>

## More Working with Messages

To find out how to get all the messages <a href="getmessagees">view the documentation here</a>

To find out how to get a specific message <a href="getmessage">view the documentation here</a>

To find out how to send a new message <a href="sendmessage">view the documentation here</a>

## Working with Templates

To find out how to get all the templates <a href="gettemplates">view the documentation here</a>

To find out how to get a specific template <a href="gettemplate">view the documentation here</a>