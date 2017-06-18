---
layout: post
title:  "How to use nuxt modules"
categories: blog
comments: true

---

In this post I'll talk about how to use Nuxt.js with nuxt modules.

# Introduction

Nuxt.js is a framework based on Vue.js and webpack and has gained 
lots of attentions recently. It's primary purpose is creating
 Universal Vue.js Applications.

In this blog post we're going to talk about how to setup Nuxt.js with
 ```nuxt-modules``` and setting up a simple Nuxt.js module.

# Getting started

## Prerequisites

This tutorial assumes that you already know what is Vue.js. If don't you 
can read about it [here](https://vuejs.org/).

## Installing Nuxt.js

First install Nuxt.js:

As stated in the [docs](https://nuxtjs.org/guide/installation) installing
is pretty simple.

```sh
$ vue init nuxt/starter <project-name>
```

Then simply install the dependencies.

```sh
$ cd <project-name>
$ npm install
```

```sh
$ npm run dev
```

Now you should be able to view the the site on http://localhost:3000

## Using nuxt-modules

Nuxt modules are a modular way of extending Nuxt.js and better integration
with libraries out there. In this tutorial we're going to use the Bootstrap
with Nuxt which is something that you need first when installing Nuxt.

In order to use bootstrap.

Run

```sh
npm install --save @nuxtjs/bootstrap-vue
```

Add ```@nuxtjs/bootstrap-vue``` to modules section of nuxt.config.js

```js
modules: [
    '@nuxtjs/bootstrap-vue'
]
```

Congratulations! :tada: :tada:

Now you can use bootstrap solely or bootstrap with Vue.js friendly API.
To find more about using bootstrap with Vue.js friendly API see [here](https://github.com/bootstrap-vue/bootstrap-vue)

For example inorder to make sure that this works. 

Clear all the contents of the ```layouts/default.vue``` and ```pages/index.vue```.

Put a simple bootstrap card in the ```pages/index.vue```.

```html
<template>
<div class="card">
  <div class="card-block">
    <h4 class="card-title">Card title</h4>
    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="">Another link</a>
  </div>
</div>
</template>
```

Now you should be able to see a bootstrap card on ```http://localhost:3000```.

# Further Reading

If you're intrested and you want to use more ```nuxt.js``` modules see below:

* [Nuxt.js Modules](https://github.com/nuxt/modules)



