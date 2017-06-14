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

## Prerequisites

This tutorial assumes that you have already installed:

* [https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-redis-on-ubuntu-16-04](Redis)
* [https://laravel.com/docs/5.4/installation](Laravel)

If you have not installed them click on them to see the installation guide.

**NOTE:** The redis installation guide contains important steps about making
your redis to start on startup follow the instructions carefully.

## Configuring Laravel to Use Redis

In order to configure laravel to use redis as your queue driver, 
first:

```sh
composer require predis/predis
```

And then change this line in the .env

```sh
```

