---
layout: post
title:  "Docker multi-stage builds"
categories: blog
comments: true
share: true
tags: docker devops

---

In this post we'll talk about latest Docker feature, **MULTI-STAGE BUILDS**.

# Introduction

Finally the long waited feature of Docker is released into the stable branch. 
:tada: :tada: From the benefits of this new feature we can point out following:

* Smaller image size
* Some ways of using multiple ```FROM``` in ```Dockerfile```


# Ok, So What the hack is this?!

Docker multi-stage builds provide some way of creating different bundles 
and using the results of previous bundle in your new bundle or image. (Without
the overhead of creating the result of previous bundle).

This will help you significantly reduce the image size of your application
by not including programs needed only for compiling.

# I didn't understand, show me an example

Suppose that you have a web application front-end project, which uses
some javascript transcompilers in order to convert ES2015 to a renderable 
javascript. In this project you have to install lots of libraries and 
dependencies in order to compile your javascripts and css files to sth better.

By using **MULTI-STAGE BUILDS** you'll change the image creation of your 
application into two phase.

* First, compile sass, js or other things
* Then, copy the compiled files from previous step and serve the files with 
your web server.
