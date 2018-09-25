+++
title = "Data (Self-)Portrait"
date = 2018-09-25T16:11:35-04:00
tags = ["Data Art"]
categories = [""]
draft = false
+++

![pic](/images/uploads/selfGif.gif)


Before this assignment, I'd never really deliberately sought out datasets that pertain personally and exclusively to me. So searching, mining, extracting, analyzing, organizing, filtering, cleaning, and, of course, visualizing this data was very much a new exercise for me.

The data I was most interested in for the purposes of this project were the relatively large stores of personal data available on the [Google Takeout](https://en.wikipedia.org/wiki/Google_Takeout) service. The two datasets in my profile that were both most plentiful and most amenable to visualization were my email records and my map records (basically, all the places I've saved or starred on Google Maps over the years). I was intiially interested in creating some kind of comparative visualization of my old email's activity (~2006-2010, and only sporadically used since) and my newer, more professional email's activity (~2010-present). As this data, cumulatively, was pretty gigantic (I'd like to work with larger datasets a little later on in the semester) I decided to work with my Google Maps data. 

This data ranges from the summer of 2013 to the present. Its keys include date and time, address, latitude and longitude coordinates, as well as the titles of tagged estashliments if applicable (restaurants, museums, parks, etc.), country code, and even a maps.google.com link. While I am interested in place-names and country, these data were either incomplete (place-names) or severely imbalanced (US-based locations represented the far majority of my places). 

I decided to work with date and lat/long coordinates as my primary data. So I converted all the coordinates from strings to numbers, filtered out elements with empty or missing coordinates, and converted the ...

Inspo's:

https://bl.ocks.org/mbostock/6dcc9a177065881b1bc4

https://bl.ocks.org/pstuffa/1f2b6eeacd8500c2728a50872ba86b6f

https://beta.observablehq.com/@mbostock/d3-ridgeline-plot

Default viz: https://michaeljblum.github.io/SelfPortrait/

Alt viz: https://michaeljblum.github.io/BandingPortrait/index.html


