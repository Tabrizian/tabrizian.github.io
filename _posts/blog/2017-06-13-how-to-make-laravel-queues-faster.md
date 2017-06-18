---
layout: post
title:  "Making laravel queues faster"
categories: blog
comments: true

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

* [Redis](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-redis-on-ubuntu-16-04)
* [Laravel](https://laravel.com/docs/5.4/installation)


If you have not installed them click on them to see the installation guide.

And assumes that you already know what is laravel queues and how it works
if don't make sure to read the article below:

* [Laravel Queues](https://laravel.com/docs/5.4/queues)

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
QUEUE_DRIVER=sync
```

to this

```sh
QUEUE_DRIVER=redis
```

Also make sure to correctly populate below paramateres:

```sh
REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379
```

## Make it FAST :)

Instead of simply running the ```php artisan queue:work``` which by 
default waits 3 seconds before pulling new jobs you can use 
```php artisan queue:work --sleep=0``` which doesn't sleep before pulling
new jobs.

## Final Steps

Depending on the configuration that you are using for your redis make sure
to change this in it. To make sure that it works perfectly fine.


