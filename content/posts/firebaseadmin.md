+++
title = 'So I came across Firebase Admin...'
date = 2024-07-17T09:47:16+10:00
draft = false
comments = false
+++
One of the things I've always loved about Firebase is how it enables developers (or frankly anyone with some intermediate competency of coding) to quickly translate their ideas into a product. Backend infrastructure can be costly to setup and when it comes to validating if an idea has promise, it may not always be a top priority if some suitable BaaS service can be used in the interim.

That being said, what happens once an idea shows promise? Typical concerns for using platforms like Firebase is a loss of cost/scalablity and control over time. For a SaaS product, these are core issues that should be handled (or at least considered) with the same level of intensity as developing new product features.

Recently, I asked myself the question of how do I maximise getting an idea out as quickly as possible whilst having some level of control of my backend. I've been playing around with Next.js which has been a great tool for full-stack development. Having used Firebase before (but only from client-side), I thought it could be a good starting point for setting up my backend.

Except this time around, I didn't use the standard imports from `@firebase` and instead found a new friend:

**And so began the tale of `@firebase-admin` being welcomed into my stack**

Firebase has an Admin SDK which you can integrate into your backend to access a broad range of service with higher privileges. For example, if you have a Firestore Database with security rules set that no one can read/write, the admin SDK can actually bypass this.

It's simplified a lot of things for me in terms of integrating backend services offered by Firebase into existing server code. I can also write functions for operations such as DB reads/writes with some level of generality that allows me to implement these methods for other services as well (should I choose to switch in future). 

So back to the topic of building apps quickly whilst making sound infrastructure decisions along the way - utilising Firebase Admin gave me a pathway to do just that and is a handy mention worth talking about.
