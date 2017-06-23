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

# I don't like web show me use case in C

In C, C++ or Go things are actually the same. You have a code that is written
in one language and needs to be compiled and what you really want is the
compiled binary. By using multi-stage builds you can compiled them in a seprate
container and run the binary produced from previous stage in another container.

# Awesome, can you provide a sample ```Dockerfile```

Sure, assume that we have a Dockerfile like below and we want to seperate 
compile phase from the run phase.

```Dockerfile
FROM ubuntu:latest

RUN apt-get update
RUN apt-get install -y gcc cmake

COPY . .

# Compile the binaries
RUN mkdir build && cd build && cmake ..

# Run the binary
CMD ["./a.out"]
```

Now we can split this ```Dockerfile``` into two stage.

First, compile the binaries and then run them.

Below is the multi-stage ```Dockerfile```.

```Dockerfile
FROM ubuntu:latest as builder

RUN apt-get update
RUN apt-get install -y gcc cmake

WORKDIR /app

COPY . .

# Compile the binaries
RUN mkdir build && cd build && cmake ..

FROM alpine

WORKDIR /app

COPY --from=builder /app/build/a.out /app


CMD ["./a.out"]
```

Congratulations :tada: tada: . You've created a multi-stage docker build
with very minimal images size. That's awesome.


