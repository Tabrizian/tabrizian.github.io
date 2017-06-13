---
layout: post
title:  "Making laravel queues faster"
categories: blog

---

In this post I'll talk about how to setup laravel queues using redis, and how
to make them perform faster.

# Introduction
By default laravel waits 3 seconds before pulling new jobs into the queue. In
this post we'll learn how to eliminate this delay and make it perform faster.
