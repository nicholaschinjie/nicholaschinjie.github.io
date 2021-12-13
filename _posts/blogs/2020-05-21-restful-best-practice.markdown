<!-- ---
title: "RESTful API Best Practices"
# title: "Maximal Functionality, Minimal Effort"
layout: post
date: 2020-06-13 21:02
tag:
- api
- spring
- java
headerImage: false
blog: true 
blog-highlights: false
description: "spring and java"
category: blog
author: nicholaschin
externalLink: false
---

collection of only the best design practices

## What are APIs?
Recently, I was tasked with a coding assignment as part of an internship position I had applied for. The task was designed to evaluate my understanding of basic API programming and language agnostic design practices. The desired product was to create a backend system that could retrieve and save photos from a third party application API, then store and 'make-accessible' the photos in my own local database.

Now, if you're unfamiliar with what an API is (like I still am), Google defines it as a mechanism that allows for two or more 'devices' to communicate with each other via requests and responses. To build a RESTful API, is to then abide by certain conventions; using HTTP methods (i.e. GET, POST, PUT) to send and these requests and responses. Essentially, REST is one of the [few][https://raygun.com/blog/soap-vs-rest-vs-json/] standard approaches that helps devices (machines / web services / servers) communicate through APIs. 

## 1. Identifying the API
Before we can use an API, we need to first figure out what endpoint to call. Luckily, the third party API I was tasked to integrate calls with was stacked with great [documentation][https://www.themoviedb.org/documentation/api?language=en-US]. I personally think this is single-handedly the most important step in the entire process: hit an API endpoint before doing anything else, and take note what the required request fields and expected response bodies are. Until you've done this, you should not 

![](../assets/blog-images/first-hit-api.png)
 -->
