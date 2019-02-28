+++
title = "Digital Cut-Ups and Data Structures in Python"
date = 2019-02-28T01:30:05-05:00
tags = ["rwet"]
categories = [""]
draft = false
+++

[Link to Jupyter Notebook.](https://github.com/michaeljblum/rwet/blob/master/Assignment_3.ipynb)

The prompt for this week's assignment was to create a program/notebook that reads in text from two or more sources, stores this text in data structures with whatever creative manipulations we choose, and programatically arranges these structures into something resembling a poem. 

The two sources I chose were various sections from the Wikipedia entry for the "Emu" and "Composition as Explanation," an essay of sorts by Gertrud Stein.

I read in the Wikipedia sections using the wikipedia module. For the Stein, I used BeautifulSoup's html parser in tandem with the requests library's fetching functionality.

The wikipedia textual matter underwent a decent amount of transformation. I used regex to split three sections (History, Behavior and ecology, and Diet) along various delimiters. Each of the sections then underwent several unique transformations, from removal of all sentences including digits to removing all words shorter than 10 characters, removal of stopwords, and removal of duplicates. In the process of the above, I used list comprehensions to fit everything into lists. 

I ran the Stein essay through a generator function which helped me create a list of randomly sized sentence fragments (between 4 and 14 words). No surprisingly, the output of this generator function was pretty excellent on its own. 

After cleaning some things up, I printed out random selections from each of the above mentioned lists, looping these print statements six times.

All in all, I'm a lot more pleased with the output of this generator than I was with that of the last one.

Here's an example (formatting is a little better in the output that can be found at the bottom of the Jupyter Notebook linked above):

***

![poem](/images/uploads/poem.png)

<!-- <pre>
it has been these thirty
 the emu's cold nasal turbinates condense moisture back out of the air and absorb it for reuse

cassia
description:
more exciting and satisfactory for everybody if one
 they have large

ants
distinguished
is denied and then all the beauty of it is accepted. If
 extracting heat from the nasal region

charcoal
distinguished
been made. Composition is not there, it is going to be
 extracting heat from the nasal region

wait
carunculated
and romanticism. Then for four years this was more and more different even though this
 both sexes sometimes boom or grunt during threat displays or on encountering strange objects

cassia
ornithologist
is not the same as the time when of the
 unlike some other species

acacia
fast-footed
</pre> -->
***