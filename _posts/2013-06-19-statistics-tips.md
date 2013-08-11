---
layout: post
title: Some Tips About Statistics I
---

Recently, I read Part I of Song S. Qian's book - *Environmental and Ecological Statistics with R* and find some interesting tips about statistics in envrionmental science. Here I will choose some to share and I will share another post when I finish the next part.

The log transformation of concertration data
==================================

In this book, the author said that the statistical distribution of concertration data of certain compounds need a log transformation to show a bell curve. I don't know if this conclusion comes from certain theroy or just depends on the observation. But usually, when we sample from a certain place for the concertration of POPs, most of the sample will show n.d. and most of time we will use half of the MDL as the concertration in case the NA make some troubles. But in face this action will cause a large number of log transformation which may also cause a tilt of normal distribution. Then I try to find the reason to make such a transformation and I think the meaning of this transformation is the hypothesis that the amounts of the pollutants is usually with a large numbers of samll amounts and few large amounts but no negative value.
