---
layout: post
title:  "Paper project brainstorming"
date:   2017-07-26
categories: bio,evolution,ecology
tags: [kitpQBio2017,eco-evo]
comments: true
---

Short post today. Started work on the project, more on that when we actually get things done. Will just talk about some
thoughts on the talks/discussions from today.

Otto Cordero gave a talk today on genome evolution. He presented some evidence that genome size is shrinking in the absence of
any selection for bacteria, and that genome size and number of genes is linear in bacteria. The claim was that this disproves
the neutral theory of gene duplication; I still find the fetish for neutral theories to be a bit odd.
He also presented his vision for
clustering/grouping things in bacterial systems: trying to find the genetic resolution at which there are individuals who
are separated because they recombine homologously with each other much more than with others (in a way where there is some
separation of scales). It's an attractive thought, especially because it gives a definition which seems more
functional/biological in nature.

Seppe Kuehn then talked a bit about his work with the 3 species closed ecosystem. Was pretty interesting, not sure what to
make of it though. They tried to analyze "ecomodes" of dynamics (aka just doing PCA on replicate trajectories). Ended up with
some modes which were kind of coherent, but with 3 species kind of hard to know what to make of it. I feel like you want to
be able to do something better than PCA, since PCA depends on the numbers of types you have and how you've grouped them.
Not sure about what an alternative is, but things to think about.

We then had a student's only session with Otto in the evening, where he talked about some work looking at communities on
granules from a bioreactor. They claimed that for the most abundant type, granule to granule there was little to no overlap in
what was there. This suggested that the species level classification was not useful, and/or that to understand ecology
maybe we need to understand genes/functions, or bacteria as pathways. This in general got me thinking about the overall
question of what ecological models should look like. Maybe for more realistic/useful/interesting ecological models, we should
try to think about things in terms of metabolic pathways? Not sure how this is changed by the fact that predation
type interactions seem to allow for new pathways (or if that gets incorporated into the framework).

Overall I think I like Otto's work/philosophy. I think he has an interesting and useful viewpoint on many of the questions in
biology, especially with regards to ecology. The quantitative nature of his work sometimes feels incomplete/suspect/not well
presented, but the experiments/thoughts are usually sound enough that I can usually get something for it. Very glad
that he came out to KITP, and looking forward to his research talk on Monday.

I also had a nice chat with Matti today about how to analyze/think about ecological time series data. I'm still not sure
of the answer, but I proposed 3 things that someone might want to do with such data:
1. **Prediction/curve fitting.** Given one half of a time series of species/type/gene abundances, predict the 
