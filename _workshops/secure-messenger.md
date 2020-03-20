---
layout: talk
title: "Build your own Secure Messenger in 3 Hours"
date: 2018-07-01
hideDate: true
---
Maybe you've written a blog in 5 minutes, but what about a secure, encrypted communications application in 3 hours?

This workshop will get you started with a simple application, and build it up to become an end-to-end encrypted chat platform.

You'll learn how to add encryption layers to the system, design data structures that won't leak metadata, and even provide mechanisms for plausible deniability.

# Detail

Using pre-defined containers, this workshop allows beginner level participants to keep up and complete the workshop, while still allowing for an engaging experience fro the more advanced participants.

We start with a basic SPA, and add authentication so that we can get a JWT. Next, we create some lambda functions (I like Zeit for its simplicity of deployment without the need for git repositories). These functions interact with a simple data store like jsonbox.io to fetch user profile information, and separately also chat data.

Finally, we add asynchronous encryption to secure the chat data, and end with a demonstration of what would happen if an application error led to sensitive chat data being leaked.
