+++
title = "Fake Beckett with GPT-2 Fine-Tuning"
date = 2019-04-04T14:33:31-04:00
tags = ["rwet"]
categories = [""]
draft = false
+++

For this week, I employed OpenAI's recently release GPT-2 language model to generate lines of poetry in the style of Samuel Beckett.

This was accomplished by way of a process called fine-tuning, which is different and a little more involved than the default, provided method of generating text with GPT-2, which entails running the interactive_conditional_samples.py script, and prompting the model with anything from a character, word, line, or several lines of text (the model then generates an output roughly inflected or motivated by your prompt, but only in a weak or oftentimes superficial sense — outputs will oftentimes reflect the slurry of cultural and political associations contained in GPT-2's training dataset, WebText).

Fine-tuning allows us to achieve a greater stylistic and structural integrity, pretty much throughout the entire output, with only a line here or there seriously looking out of place. The vocabulary, style, and even fine, more structural things like Beckett's enjambment are reflected in the output achieved via fine-tuning. 

The process, while more complicated than default prompting, is still relatively easy: it involves some pre-processing of the source text (which are Beckett's collected poems), running a new round of training with the GPT-2 model using a [fork](https://github.com/nshepperd/gpt-2) of OpenAI's repo expressly intended for fine-tuning, copying the new weights from this training and adding them to the directory containing the original weights for the trained GPT-2 model, and then running generated_unconditional_samples.py to generate output. 

The remarkable thing about this training and this model is its efficiency. The size of my source text was 32kb, which is ridiculously small considering it takes upwards of 7 to 10mb of text data to begin to generate quality results with an LSTM neural network architecture. Not only are the size requirements of the model so impressive, but it also trains extremely quickly (mere minutes compared to hours and hours for LSTMs).

The only real downside to training with input text this small was that overfitting becomes a lot earier. While I could have tweaks some parameters, such as learning rate, to attenuate overfitting or slow it down, I didn't feel this was totally necessary, as a rough glance over my output showed that, while there was definitely some *actual* Beckett in my fake Beckett output, there was a whole lot of novel content as well. So my next step was to put together a Python script to do a few things, chief among them checking for lines of *actual* Beckett in the fake Beckett file, and removing them. 

This script and the cleaned up output it produces can be seen in this [notebook](https://nbviewer.jupyter.org/github/michaeljblum/GPT-Beckett/blob/master/fake_beckett.ipynb). 

One sort of has to handpick and apply some degree of prejudice when reading over this output, discarding those lines that err a litle too far past the threshold of non-sensicalness that we somewhat arbitrarily set for ourselves when reading poetry that is so abstract in the first place. 

Still, there are definite gems to be found here, and there are choice segments — several lines at a time, here and there, practically enough to comprise a poem of themselves — that really stand out and hold their own.

In some of my other output, even, my bare output, before I ran the script that surgically removed the real Beckett from the fake, there are some moments that really impressed me, where I found it very truly difficult to distinguish where the real ended and the fake began. Here is one such:

>grave suave singing silk<br>stoop to the black firmament of areca<br>rain circus foot traffic<br>for all the world that dusts the sand<br>and the crystal clear seas<br>and the eyes by its shining mechanisms<br>communicating by heart<br>that which is free<br>and that is not free

"Grave suave singing silk," and "stoop to the black firmament of areca" are both Beckett; the rest is not. What really gets me is GPT-2's ability to ouput a line, consistent with Beckett's structure, in which is likens eyes to "shining mechanisms." There are similarly (dare I say it) poetic phrases elsewhere. What I'd like to do next is attempt fine-tuning with a larger corpus, or maybe employ another algorithm to better refine the organization or collocation of the output of this fine-tuning process. 
