+++
title = "RWET Final"
date = 2019-05-10T14:29:06-04:00
tags = ["rwet"]
categories = [""]
draft = false
+++

For me final, I wanted work more with OpenAI's GPT-2, as further experimentation with it had begun to shift my thinking about natural language generation, particularly in the realm of *pre-trained models,* which don't merely reflect the source text back onto itself in a novel and occassionally surprising configuration, as is the case with older methods of generating text, but importantly do so inflected by gigabytes and gigabytes of worldly, extraneous stuff. It has a model of the world, and though miniature,stunted, and wildly limited, compared to something like human or animal intelligence, it's a model of the world nevertheless. (This line of thinking of mine was motivated by moments such as though encountered in my previous blog post, where the model, fine-tuned on Beckett's poetry, had introduced a tangent on Epimetheus, mention of whom didn't exist in the source, among other moments.)

Heretofore I'd only been either prompting the model or engaging in a slightly more involved task of fine-tuning its weights (transfer learning). I wanted to get into the guts of it, and so begun my work on my final by adjusting various things in the scripts that handle the various steps of generation. This was really messy work, and after a while I got a few things to work a little differently, but ultimately the effect just wasn't worth the newly introduced bugs and here-and-there incoherences. What I was basically trying to do was superimpose the generations of generations - by which I mean, I wanted one step of generation to be dictated by the weights saved at step 60 (for example), another to be dictated by the weights saved at step 200, and so on. It was to be a palimpsest of the different moments of training. And I was trying this with two different approaches with regards to source text: one, with training on the same text the whole time, and the other, with training a motley of different texts in sequence, swapping out texts every time the weights would be saved.

This was fine, but I wasn't reaching the effect I was aiming for. 

So I decided instead to aim for this same or similar effect manually, in Python. [I put together a script](https://github.com/michaeljblum/rwet-final/blob/master/Make-Mixture.ipynb) that read in four text files - one consisting of Beckett's Molloy, another consisting of Beckett's poems, a third consisting of scraped BBC sports articles, and a fourth consisting of a slurry of text generated from a variety of sources (Beckett, Gertrude Stein, Scott Walker, sports, one introduced after the other not dissimilar to the method I mention above). The script include several pre-processing steps, removal of various things from the sports corpus (sentences shorter than 5 character, sentences longer than 80 characters, punctuation, numbers), and then a function that interleaves the four different sources. The goal here was to attenuate the texts self-similarity: to make it *less alike* itself, and insodoing, to some extent befuddle and sabotage the training process, while still achieving some regularity and coherence, which in part is taken care of by the multi-head attention in the Transformer's decoder in GPT-2. 

I then trained GPT-2 on this mixture.

I generated text from weights taken from this trained at many different times steps and at different "temperatures". 

You can find [my favorite generation in this link here](https://github.com/michaeljblum/rwet-final/blob/master/Formatting.ipynb).

The script simply wraps and centers it. 

I haven't read it all, or even close really, and from a quick scroll-through, I can see that there are a couple moments of breakdown and glitching (model tumbles on a word for a bit). But overall, I quite like what I've read. 


