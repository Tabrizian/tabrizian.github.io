---
layout: post
title:  "Making laravel queues faster"
categories: blog

---

In this post I'll talk about how to setup Laravel queues using redis, and how
to make them perform faster.

# Introduction
By default laravel waits 3 seconds before pulling new jobs into the queue. In
this post we'll learn how to eliminate this delay and make it perform faster.

# What ?! Redis ?
Redis is a key-value based, in-memory NoSQL database which has serveral use 
cases. In this post we're going to use it as a message queue for Laravel.

# Getting Started

## Install Redis
Firstly, you should install redis in order to use it as message queue.

```sh
wget http://download.redis.io/redis-stable.tar.gz
tar xvzf redis-stable.tar.gz
cd redis-stable
make
```
