---
title: "🎵 Lyric-Based Music Recommendations"
layout: post
date: 2018-01-15 22:10
tag: 
- hackathon
- python
- machine learning
- javascript
# headerImage: false
projects: true
featured-projects: false # feature on home page
description: "<i> lyricistics </i> - an AI trained to make lyrically-similar song recommendations"
author: nicholaschin
category: project
externalLink: false
---

<p align="center">
    <a href="https://github.com/nicholaschinjie/song-lyric-similaritizer"> 
        <img src="https://img.shields.io/badge/github-lyricistics-E15967.svg?style=for-the-badge&logo=github">
    </a>
</p>
<p align="center">
    <img src="https://img.shields.io/badge/contributors-3-brightgreen.svg" />
    <img src="https://img.shields.io/badge/hackathon-nwHacks%202018-4DA0B2.svg" />
    <img src="https://img.shields.io/github/languages/top/azh/song-lyric-similaritizer.svg?colorB=00A9FD"
        alt="Backend language" />
</p>


<a href="https://github.com/nicholaschinjie/song-lyric-similaritizer"> Lyricistics</a> is an neural network trained to make **lyrically-similar** song recommendations, contrary to the genre-based recommendations most music streaming services offer. Built by a team of 3 within the 24 hours of <a href="https://nwhacks2018.devpost.com/"> nwHacks 2018</a>, this post serves to illustrates our experimentation with machine learning techniques to analyse and classify the content and meaning behind songs' lyrics make 'appropriate' music recommendations. The idea in practice is rather simple: when listening to a song you enjoy for its lyrical sentiment, the network's search will (hopefully) yield a list of songs sharing a similar style of lyrics to it. 

Here's a sneak peak of the end result: 
<p align="center">
    <img src="/assets/images/projects/lyricsknn.png" width="100%" />
</p>

## Methodology

The intricacies behind its development we found are fascinating; despite the muddled results. We decided to use <a href="https://genius.com/">Genius</a> to parse song lyrics from; its API-support and provision of not only lyrics but line-by-line annotations gave us a larger training set to work with. Doing so however constrained our selection of song lyrics to earlier, almost exclusively hip-hop/rap songs, with the belief that they would have the most thorough annotations overall. To achieve this, we wrote a script using JavaScript to scrape the Genius database of 25000 lines (approx. 6000-6500 songs); to build our dataset. We used the <a href="https://machinelearningmastery.com/gentle-introduction-bag-words-model/">*bag of words*</a> model to find features and 'vectorize' our lyrics and annotations, allowing us to blur the lines between annotations and lyrics and combine both elements as part of our training data set. The reason for representing vectors as lyrics was grounded in our belief that sentences would better capture an essence of semantic information of the words they contained. The beauty of the English language is that the meaning of words is largely dependent on the context the word occurs in. To 'vectorize' individual words would not be an accurate indicator of an artists' meaning, especially when rap lyrics are mostly taken out of context. Thus, our decision to go with such vector representations, in theory, dictates that words occurring in similar sentences and hence contexts will have similar vectors. The next part was to realize it in practice. 

We initially also planned on incorporating NLP (Natural Language Processing) to compress lyrics to only a summary (to reduce the word count and hence trim the overall dataset) using a <a href="https://medium.com/@mplaut929/smmry-the-algorithm-behind-reddits-tldr-bot-c268722a4c27">SMMRY algorithm</a>. But we quickly learned of some amusing patterns that rap songs displayed, most notably artists' usage of stop words - commonly used words that search engines are programmed to ignore (e.g "a", "an", "in" - convinced us otherwise. As such, we left all songs the way they were. Another observation we made, which should come as no surprise, was hip-hop culture's love for incessant profanity. We went through a lot of obscenity that day, but ultimately decided against censoring them. A standpoint one of my teammates vehemently defended - because it would be "a mockery of our rap godfathers' artistry and right to self-expression." His words, not mine. 

## Findings

Realizing a working model was difficult. We used unsupervised machine learning algorithms to explore the entire database of hip-hop songs we collected. We fed data to a <a href="https://radimrehurek.com/gensim/models/doc2vec.html">Doc2Vec</a> (a variant of Word2Vec oriented towards paragraphs/collections of words) based neural network that supported our mode of vectorization, as well as a KNN (K-Nearest Neighbours) cluster that used principal component analysis to reduce dimensionality (making our model classify things more accurately). On the neural network, we found that the accuracy and positioning of recommendations was highly dependent on the length of the query and word overlap. As for the KNN cluster, we observed that data separated into three visible clusters. Several anomalies were present in both forms of analysis, which we attributed to a subset of a) songs written in foreign languages, and b) unusually terse or short songs.

<p align="center">
    <img src="/assets/images/projects/run1.png" width="100%" />
    <img src="/assets/images/projects/run3.png" width="100%" />
    <img src="/assets/images/projects/run2.png" width="100%" />
</p>

<p align="center">
    <i style="font-size:90%;">Graphs of neural network training vector clusters produced during three different runs.
    </i>
</p>

## Wrapup 
It is difficult to verify our algorithm's success without performing some semantical analysis of two or more songs, which remains something that needs to be done in future (preferably, not by us). As it stands, the clusters demonstrate some success in our attempt to classify, and thus recommend, lyrically similar songs based on their surrounding adjacent nodes. Admittedly we could've have cleaned our data better, but were limited by: 

* some foreign language tracks 

* some junk data orphaned annotations/lyrics likely buried in other track data or standalone
