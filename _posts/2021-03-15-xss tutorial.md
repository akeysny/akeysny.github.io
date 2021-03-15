---
layout: post
title: "Find your cookies"
subtitle: "Javascript and your Browser"
background: '/img/posts/cookies/cookies.png'
---

## Warm Up

Let's warm up by taking a look at what cookies look like. Try to look inspect them a few different ways.

Using Burp
Go to facebook.com, and look at the request header in Burp. As you can see, multiple cookies are sent with each request. The cookies are sent as a single string, where each cookie is a key-value pair, separated by semicolons.