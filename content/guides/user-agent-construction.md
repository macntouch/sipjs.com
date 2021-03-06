---
title: User Agent Construction | SIP.js
description: Create a SIP user agent using SIP.js so your WebRTC application can send and receive calls and messages.
---

# User Agent Construction

* TOC
{:toc}

Let's walk through the process of creating a SIP user agent.


### Anonymous User Agent

First we need to include the [SIP.js library](/download/).

In order to make calls and send messages you must create a SIP user agent.  In this example, we will create an anonymous user agent.  To do this, call the `SIP.UA()` method with no arguments.  An anonymous user agent can make calls and send messages to SIP endpoints.  It cannot receive calls or messages.



### Authenticated User Agent

To create an authenticated user agent, pass a configuration object to the `SIP.UA` constructor.

This [configuration object](/api/0.6.0/ua_configuration_parameters/) needs a `uri`.  This will have a username and a domain.  It will look something like `examplename@test.onsip.com` The `authorizationUser` and `password` are used to authenticate with your SIP provider.

~~~javascript
var userAgent = new SIP.UA({
  uri: 'bob@example.onsip.com',
  wsServers: ['wss://sip-ws.example.com'],
  authorizationUser: '',
  password: ''
});
~~~
