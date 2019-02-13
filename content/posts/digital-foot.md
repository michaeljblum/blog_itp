+++
title = "Digital Footprint"
date = 2019-02-10T23:24:16-05:00
tags = ["ROY"]
categories = [""]
draft = false
+++

![app-pic](/images/uploads/coordinates.png)

Some of our data we create without much conscious awareness of doing so (listening, searching, and clicking habits, for example, all of which are measured by the companies who own the platforms on which we perform these actions, and use this information to make decisions).

Other of our data we deliberately create—we're aware of the accumulation and storage of this data over time, and may even frequently consult with this accumulated data ourselves (Fitbit and similar self-quantification in the service of health and fitness).

When considering my "digital footprint," I thought it'd be interesting to take a dataset that is a little bit of both—data points that I've been accumulating deliberately, but without any conscious thought as to the "whole" that they comprise when taken together, that is, without really ever thinking about them as "data."

This dataset is my saved places in Google Maps, accumulated between 2013 and 2018. I typically "star" places—mostly restaurants, but also parks, venues, museums, and so on—when I really like them, intend to return, or want to remind myself to finally visit.

I was able to download the entirety of this dataset using the Google Takeout service.

After cleaning up the data in a script, I made a page that randomly outputs the coordinates of a given place at the press of a button, generating a new location out of the saved 580 spots every time. [Link to site](https://michaeljblum.github.io/Street-View/index). (Made with vanilla Javascript and D3.)

While I am working on hooking up this coordinate data to Google's Street View API, I thought it'd be kind of droll, in the mean time, to lean into the abstraction of a set of two coordinates standing in, nakedly, for places that to varying degrees hold significance for me. During our last class, this abstract characteristic of data came up—how it is in so many cases a shoddy compression of what we take to be reality. In this instance, the minimalist confrontation with hundreds of different sets of two floating point numbers, generated at random and one at a time, is an almost absurd (pleasantly so, in my opinion) demonstration of the cleavage between reality and datapoint. And yet, these coordinates can be argued to be, in their own way, more informative than a photograph might be.