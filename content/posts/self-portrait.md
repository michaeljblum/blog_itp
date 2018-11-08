+++
title = "Data Self-Portrait"
date = 2018-09-25T16:11:35-04:00
tags = ["Data Art"]
categories = [""]
draft = false
+++

![pic](/images/uploads/selfGif.gif)


Before this assignment, I'd never really deliberately sought out datasets that pertain personally and exclusively to me. So collecting, analyzing, organizing, filtering, preparing, and, of course, visualizing this data was very much a new exercise for me.

The data I was most interested in for the purposes of this project were the relatively large stores of personal data available on the [Google Takeout](https://en.wikipedia.org/wiki/Google_Takeout) service. The two datasets in my profile that were both most plentiful and most amenable to visualization were my email records and my map records (basically, all the places I've saved or starred on Google Maps over the years). Initially, I was most interested in creating some kind of comparative visualization between my old email account's activity (~2006-2010, and only sporadically used since) and the activity of my newer, more professional email account (~2010-present). As this data, cumulatively, was pretty gigantic (over ~10 gigabytes) I decided to work with my Google Maps data instead. 

This data ranges from the summer of 2013 to the present. Its keys include date and time, address, latitude and longitude coordinates, as well as the titles of tagged estashliments if applicable (restaurants, museums, parks, etc.), country code, and even a maps.google.com link. While I am interested in place-names and country, these data were either incomplete (place-names) or severely imbalanced (US-based locations represented the far majority of my places). 

So I decided to work with date and lat/long coordinates as my primary data. So I converted all the coordinates from strings to numbers, filtered out elements with empty or missing coordinates, converted the string dates into Javascript Date objects, and did a few other things to prepare the data for visualization.

My primary inspiration for this visualization are what are called "ridgeline plots" (similar in style to the famous album art of Joy Division's 1979 album Unknown Pleasures). In ridgeline plots, a horizontal line is drawn for each element in the data. Each line has striations and bumps that represent some feature of the data. See, for example, [this visualization](https://bl.ocks.org/pstuffa/1f2b6eeacd8500c2728a50872ba86b6f) of a runner's training data.

I was also inspired by visualizations that are not only highly vertical, but also almost clumsily tall, such as [this visualization](https://bl.ocks.org/mbostock/6dcc9a177065881b1bc4), which majestically represents an advanced sorting algorithm. 

Ridgeline visualizations are essentially a hybrid comprising of a line and area visaulization, and as such are relatively complex. I am planning on fitting my data into a ridgeline plot-style visualization in the coming days or weeks, but in the meantime decided to produce a simiular effect using a stack plot, which basically draws rectangles for each element of the data instead of lines. In these kinds of visualizations, the thickness and height of the rectangles are what chiefly convey values.

<!-- ![FullPic](/images/uploads/selfPortraitscreenShot.png) -->

In my stack plot, each rectangle, or bar, represents a single "saved place," that I'ved logged since I started making use of this feature on Google Maps in 2013. The height of each bar represents the combined latitude and longitude of the place the bar represents. Basically, the skinnier the bar is, the further away the place is from the mean latitude and longitude in my dataset (which is essentially the New York City area). European places, for example, have a bar that is half the height of New York City place bars, while bars representing places I saved while in Japan are an even bigger deviation from the height of the New York City places.

The color of the bars, meanwhile, represents time. I applied an interpolation method for blender colors using the "Plasma" color scale, so the earliest values are a vibrant yellow, while the most recent values are a deep blue, with various other colors in between these two. Additionally, I also applied a special kind of Gaussian SVG filter to the visualization, which gives it a feint, somewhat blurred glow.

Here is [a link](https://michaeljblum.github.io/SelfPortrait/) to my visualization, which is quite tall at ~9000 pixels high, and compells the user to slowly scroll to see the entire visualization. This approach is interesting because I feel the scrolling gives the piece an almost durational aspect, which is appropriate for conveying that this highly personal data was accumulated over the course of five years.

And here is [a link](https://michaeljblum.github.io/BandingPortrait/index.html) to an alternate version of visualization, which packs the rectangles more closely together, allowing them to be seen without much scrolling at all. In this visualization, the differentation of bar height and coloration can be seen in starker relief. 

