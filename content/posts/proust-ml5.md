+++
title = "Deploying (and Designing) Machine Learning Models on the Web"
date = 2018-10-30T20:22:45-04:00
tags = ["Data Art"]
categories = [""]
draft = false
+++

For the second section's assignment of Data Art, we were tasked with working with text and other similarly unstructured data. The aim was to create an archive or accomplish something that had, thematically speaking, some kind of archival significance, be it in the final product or in its working process. 

For my project, I created [this](https://michaeljblum.github.io/MachineProust/), a generator of original machine memories, built with a deep LSTM neural network trained on the works of early 20th century French writer Marcel Proust.

In a sense, it is a more developed and fully realized version of a project I begun for my Neural Aesthetic class, but in practice and execution, it has very little in common with it. My previous work for Neural Aesthetic——also involving work on a deep LSTM neural network trained on Proust——utilized a different machine learning framework, Keras, and had no web (javascript and CSS) interface. 

The project linked above, on the other hand, involves a machine learning model trained in Tensorflow, as well as an interface built for the web, using the ml5 library to enable and refine browser interaction with the model. 

The project linked above, hosted online with Github Pages, has some shortcomings compared to my offline work I tested on localhost with Live Server. I am as of yet uncertain why this is. The text I retrieved from the offline versions seems to me both more cogent and creative than the text the online, hosted version is generating. 

Compare, for example,

*still feel the truth of the people who had not been able to find in the most amorous spectrally attractions of the distinction of the beautiful land. And so the day was still at the day, for whose wealth of politeness is silent, one in a spark outline can alter it, it is betrayal. And then the scale of contempt for me the stage of fashion and must confine ourselves time in the street for the surface of the faces, the intellectual creatures who seem to them the acquaintance of the little body and the services of other people's witticisms and signs which I had formerly announced the exaltery of*

with 

*feed estitute to me we see tears it were tendencies to tea on we are and she such as ten year on to tear tease to address to her as to tease to see her to bed and were remedient to hear it it went on take people were shewn to me to tear easies an admontus seem taste, a qeasuary tendencies at waiting and teasing her feet a certain part on the point on ten years at Balbec at Comparishible and to teem a decistent antipathate or to tear tea. I can see he went on feint on a certain desire take out on ten time to tea tea tendences at heat. I remendered he went to recent as many desire to meet to m*

One thing that perplexes me is the Github Pages hosted version's obsession with words like "tea" or "tears" or "tendences." 

Another thing I must address is the delay that occurs when the user prompts the model for text. Text generation causes a page-wide lag during which the page essentially freezes (no input or output is allowed or occurs). This issue is currently being resolved by the people who are working on the ml5 library, but until this is resolved, I will likely have to research web workers and having the text generation work done on a server or something like that, rather than right there on the web page. 

As far as the process goes, my steps were as follows:

1. Use a command line script to convert PDFs to .txt files, including arguments in the script to encode the text properly and format it to my liking.
2. In a text editor, use regex to remove all page numbers and other extraneous or irrelevant textual matter. This process also included manual removal or front- and backmatter. 
3. Use another script to bind all the .txt files into one input.txt file.
4. Modify the Tensorflow script with the deep LSTM networks, adjusting hyperparameters, and begin training.
5. Repeat step #4 over and over, adjusting hyperparameters a little each time, until the results are to my liking. 
6. Saving and exporting the model when I'm satisfied with the results.
7. Writing the website using Javascript, CSS, and ml5 to host the model online and allow interaction with it. 
