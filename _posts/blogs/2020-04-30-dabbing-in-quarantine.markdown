---
title: "Dabbing" 
layout: post
date: 2020-04-31 12:00
image: /assets/images/dab.gif
headerImage: false
featuredImage: true
tag:
- Machine Learning
- for-fun
category: blog
blog: true 
# star: true
blog-highlights: true
author: nicholaschin
description: Dabbing my way back into sanity in a 24-hour quarantine hack
---

<!-- https://github.com/TimHillier/Dabbot -->

## What are APIs?
Recently, I was tasked with a coding assignment as part of an internship position I had applied for. The task was designed to evaluate my understanding of basic API programming and language agnostic design practices. The desired product was to create a backend system that could retrieve and save photos from a third party application API, then use my own API to store and 'make-accessible' the photos in my own local database.

Now, if you're unfamiliar with what an API is (like I still am), Google defines it as a mechanism that allows for two or more 'devices' to communicate with each other via requests and responses. To build a RESTful API, is to then abide by certain conventions; using HTTP methods (i.e. GET, POST, PUT) to send and these requests and responses. Essentially, REST is one of the [few][https://raygun.com/blog/soap-vs-rest-vs-json/] popular approaches that helps devices (machines / web services / servers) communicate through APIs. 

## 1. Identifying their API
Before we can use an API, we need to first figure out what endpoint to call. Luckily, the third party API I was tasked to integrate calls with was stacked with great [documentation][https://www.themoviedb.org/documentation/api?language=en-US]. After reading through it, I was able to hit an API endpoint and retrieve the data I was looking for.


![](../assets/blog-images/first-hit-api.png)
<p align="center">
  <i style="font-size:90%;">With this initial API call, I can ascertain the methods and endpoints of my request, along with the expected response body and fields in JSON format.</i>
</p>

I personally think this is single-handedly the most important step in the entire process. Making an API call to test it allows for developers to note what the required request fields and expected response bodies are. 

## 2. Building your API
Essentially, my task is to build something identical to the third-party API I just called (except on a much smaller scale). How this works: 

![](../assets/blog-images/sd-part1.png)



first API (users call me, I call them)