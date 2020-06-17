---
title: "🎵 Song Lyric Similarizer"
layout: post
date: 2018-01-15 22:10
tag: 
- hackathon
- python
- machine learning
- javascript
headerImage: false
projects: true
featured-projects: false # feature on home page
description: "<i> lyricistics </i> - an AI trained to make lyrically-similar song recommendations"
author: nicholaschin
category: project
externalLink: false
---


# Lyricistics
Lyricistics is an AI trained to make **lyrically-similar** song recommendations, contrary to the genre-based recommendations most music streaming services offer. Built by a team of 3 within the 24 hours of nwHacks 2018, this post serves to illustrates our experimentation with machine learning techniques to analyse and classify the content and meaning behind songs' lyrics make 'appropriate' music recommendations. The idea in practice is rather simple: when listening to a song you enjoy for its lyrical sentiment, the AI's search will (hopefully) yield a list of songs sharing a similar style of lyrics to it.


The intricacies behind its development we found are fascinating; despite the muddled results. We decided to use Genius to parse song lyrics from; its API-support and provision of not only lyrics but line-by-line annotations gave us a larger training set to work with. Doing so however constrainted our selection of song lyrics to earlier, almost exclusively hip-hop/rap songs, with the belief that they would have the most thorough annotations overall. To achieve this, we wrote a script using JavaScript to scrape the Genius database of 25000 lines (approx. 6000-6500 songs); to build our dataset. We used the *bag of words* model to find features and 'vectorize' our lyrics and annotations, allowing us to blur the lines between annotations and lyrics and combine both elements as part of our training data set. The reason for representing vectors as lyrics was grounded in our belief that sentences would better capture an essence of semantic information of the words they contained. The beauty of the English language is that the meaning of words is largely dependent on the context the word occurs in. To 'vectorize' individual words would not be an accurate indicator of an artists' meaning, especially when rap is largely... Thus, our decision to go with such vector representations, in theory, dictates that words occurring in similar contexts will have similar vectors. The next part was to realize it in practice. 

We initially also planned on incorporating NLP (Natural Language Processing) to compress lyrics to only a summary (to reduce the word count and hence trim the overall dataset) using a SMMRY algorithm. But we quickly learned of some amusing patterns that rap songs displayed, most notably artists' usage of stop words - commonly used words that search engines are programmed to ignore (e.g "a", "an", "in" - convinced us otherwise. As such, we left all songs the way they were (and are). Another observation we made, which should come as no surprise, was hip-hop culture's love for incessant profanity. We went through a lot of obscenity that day, but ultimately decided against censoring them - a standpoint one of my teammates vehemently defended - because it would be "a travesty and mockery of our rap godfathers' artistic self-expression." His words not mine. 

Realizing a working model was difficult. We used unsupervised machine learning algorithms to explore the entire database of hip-hop songs we collected. We fed data to a Doc2Vec (a variant of Word2Vec oriented towards paragraphs/collections of words) based neural network that supported our mode of vectorization, as well as a KNN (K-Nearest Neighbours) cluster that used principal component analysis to reduce dimensionality (basically, making our model classify things more accurately). On the neural network, we found that the accuracy and positioning of recommendations was highly dependent on the length of the query and word overlap. As for the KNN cluster, we observed that data separated into three visible clusters. Several anomalies were present in both forms of analysis, which we attributed to a subset of a) songs written in foreign languages, and b) unusually terse or short songs.