---
layout: post
title:  "fastai POC"
date:   2021-08-12 12:32:32 -0700
categories: deep learning
---

<h1>Learning FastAI</h1>

I wanted to make a POC using streamlit.  Here it is, https://lynnaj-unicorn-versus-pegasus-app-gfm5y7.streamlitapp.com/

It's a simple data app that can take a jpg url (make sure it has suffix .jpg), and output a prediction based on a model training on 400 photos.

List of URLs you can use to try:
https://img.huffingtonpost.com/asset/5f4517881f00008b04aa9c4b.jpeg
https://img.freepik.com/premium-vector/unicorn-sticker_116089-146.jpg
https://static1.funidelia.com/56850-f6_big2/set-of-8-unicorn-party-bags.jpg

For the code references I used [Ha Nguyen's github demo of fastai version 1](https://github.com/trungha-ngx/mtp-vs-gd)

To get started with fastai version 2, I used this LinkedIn Article called, [Creating a machine learning image classifier in under 45 mins with FastAI](https://www.linkedin.com/pulse/creating-machine-learning-image-classifier-under-45-mins-cummaudo/)

My final quick & dirty code was a mishmash of the above 2 sources!
