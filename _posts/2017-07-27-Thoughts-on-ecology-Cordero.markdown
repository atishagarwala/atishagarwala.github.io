---
layout: post
title:  "Thoughts on theoretical ecology"
date:   2017-07-27
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
granules from a bioreactor. They claimed that for the most abundant type, granule to granule there was little to no overlap 
in
what was there. This suggested that the species level classification was not useful, and/or that to understand ecology
maybe we need to understand genes/functions, or bacteria as pathways. This in general got me thinking about the overall
question of what ecological models should look like. Maybe for more realistic/useful/interesting ecological models, we should
try to think about things in terms of metabolic pathways? Not sure how this is changed by the fact that predation
type interactions seem to allow for new pathways (or if that gets incorporated into the framework).

I asked a question about whether or not one would need to consider a large number of types to understand any ecological
system. It seems most of the systems presented about here have a few key players (or that's what the belief is). He
suggested that low abundance guys may be important, but that if something like metabolic pathways are explanatory
for microbial ecology, the number of things to consider would be set by that rather than the actual
number of types in the population.

Overall I think I like Otto's work/philosophy. I think he has an interesting and useful viewpoint on many of the questions in
biology, especially with regards to ecology. The quantitative nature of his work sometimes feels incomplete/suspect/not well
presented, but the experiments/thoughts are usually sound enough that I can usually get something for it. Very glad
that he came out to KITP, and looking forward to his research talk on Monday.

I also had a nice chat with Matti today about how to analyze/think about ecological time series data. I'm still not sure
of the answer, but I proposed 3 things that someone might want to do with such data:
1. **Prediction/curve fitting.** Given one half of a time series of species/type/gene abundances, predict the second half.
This would then suggest that something about the ecological data has been captured by a hopefully low dimensional model.
2. **Extrapolation.** What would have happened if more of one type or another were present? What is the long term fate
of an ecosystem? Being able to do this would imply some general understanding of the system that is encoded in some useful
way.
3. **Extraction of interactions.** The word interactions is used loosely here; really, this is any scenario where one can
use model parameters to say something about biological processes. This could be as coarse as inferring a Lotka-Volterra
like predator prey interaction, or a model which spits out something about metabolic rates.

Still not really sure how to do any of these, but food for thought. Thinking about time series analysis and
thinking about what sorts of ecology models (toy or otherwise) one should be thinking about/playing around with
are the two overall questions which interest me in theoretical ecology. I hope I can get more of a sense of
the latter especially while I'm here; it would be great to come up with ideas for interaction schemes that "look like"
trophic levels/metabolic networks and have the right flavor about them, in order to start asking questions.

I'll
end with a quote today paraphrased from Boris Shraiman: _"Make sure your models are falsifiable, not just solutions
looking for problems."_
