---
layout: post
title:  "APS March meeting 2019 recap"
date:   2019-03-08
tags: [APS,eco-evo]
comments: true
---

Below are some thoughts on my experience at APS March meeting. Ended up missing about a day of it due to my
hurt ankle, but hopefully I'll cover most of the relevant things that happened.

## Eco-evo theory

Most of the eco-evo theory work was on consumer resource models.
There were a couple of talks on spatial structure stuff that I missed,
but they were mostly involving pushed vs. pulled waves with one type (modeling density dependent effects).
As a side note, a couple of the talks used (explicitly or just in a cartoon sense) the idea that
interactions in the consumer resource model can be thought of as an outer product of matrices
involving how resources affect types and how types affect resources.

### Cooperation and symbiosis

There were a couple of talks trying to understand how cooperation/symbiosis/cross-feeding could be
evolutionarily stable. Unfortunately most of them were very mathematical - trying to construct
complicated game-theoretic models and doing even more complicated analysis.

There were two intriguing talks: the first was by Simone Pigolotti talking about bet-hedging strategies.
He claimed that his modeling suggests that spatial structure is necessary for bet-hedging to evolve,
might be worth taking a look. The other one was trying to look at cross-feeding; they had a simple
toy model in which one resource could be broken down into a secondary resource, which could again be
broken down for energy. They looked at types which could breakdown both as well as types that could
only break down one, and tried to study their coexistence. The claim was that a community of two cross-feeders
was stable to invasion from a "generalist" who broke down both.

Seems that there
are a lot of common threads in a lot of these "cooperativity" models; I wonder if there are general principles
that would be worth writing down.

**Papers**

* Simone Pigolotti on bet hedging: [ref 1](https://arxiv.org/abs/1810.01142),
[ref 2](https://link.springer.com/article/10.1007/s10955-017-1926-4),
[ref 3](https://groups.oist.jp/bcu/research)
* No paper yet on cross-feeding model,
[motivating experiment](http://science.sciencemag.org/content/361/6401/469) (personally don't think it's too
deep?)

### Consumer resource models

The main eco-evo theory stuff that got talked about was consumer resource models. There was one talk
on trying to understand the spectrum of the interaction matrix around the fixed point; was hard to follow
details in the talk so I included references below. Ned Wingreen talked about his work on the linear
tradeoffs model that has the degenerate subspace (missed the talk unfortunately), but didn't really
have many new results (main thing is that they are now trying to understand spatial structure).

Pankaj Mehta and associates had a few talks; probably worth reading their latest papers just to
get a sense of what their models are. My impression is that their results are similar to
Mikhail Tikhonov's work, but would be good to figure out in detail - especially as there may be subtle,
strong assumptions used.

**Papers**

* Ned Wingreen papers on
[linear resource model](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.028103)
as well as a [followup with spatial structure](https://arxiv.org/abs/1902.09039)

* Pankaj Mehta and co papers on
[fluxes and diversity](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006793) and
[niche theory](https://arxiv.org/abs/1901.09673)


* [Ecological dynamics and quadratic programming](https://arxiv.org/abs/1809.04221)

### Ecology data

Missed a few of the experimental talks due to my foot injury, but judging from abstracts/references, most
were older ones that I've heard about/read about/talked to the authors about. One of the talks had some
references to some work looking at abundances in an ecological system (fish) over long periods of time - which
could be of interest as references for any ecology theory work on dynamical diversity.

**Papers**

* [Fish ecology over decade timescale](https://www.nature.com/articles/nature25504)

### Evolving generalists vs. specialists

One theme that came up in a couple of talks was the idea that in order to evolve generalists, you need to
be presented with environments (either in time series or via spatial structure) that are different but not
too different. This came up in Mikhail Tikhonov's talk (on the model that he's writing up right now), as
well as Vedant Sachdeva's. Something that I hadn't thought too much about, but seems like a good fundamental 
idea.




### Phenotype models

There was one talk dealing with evolution on phenotypic landscapes, in the context of the immune system.
The model was similar to mine, so will be worth thinking about how the existence of this work might affect
how I develop mine.

The [talk](http://meetings.aps.org/Meeting/MAR19/Session/S66.13), by Jiming Sheng, was trying to model the
co-evolutionary dynamics of antigens and antibodies in the immune system. There was some phenotype space, where
again some sort of distance measure was related to fitness. The model was meant to study co-evolutionary
dynamics in the presence of broadly neutralizing antibodies. I think it had both dynamics and mutations,
but not sure of their timescales. The main result was that depending on how broad the distribution of initial
antibodies was, and the dimensionality of the phenotype space, one would either get the antigens "escaping"
or being quickly neutralized.


For most of the talk, it seemed that the antibodies were not mutating (or mutating slowly), and most of their
influence was via their intial distribution. However towards the end, there was a brief discussion of how the
antibodies could start out in a non-broadly neutralizing state, and go to a broadly neutralizing state,
but I need to get some more details about the model to figure it out.

In terms of what they _haven't_ done, I think one of the main things is that they don't really have any
analytical results. They haven't thought about scaling with any sets of parameters in quantitative detail.
It's also unclear in what sort of dynamical regime they are working - there may have been a separation
of timescales between the dynamics and mutations, but it was unclear from the talk.
Also, there was not much discussion
of the diversity of either population.

Wasn't able to catch up with the speaker in person, unfortunately; plan on following up via email to get a better
sense of the questions/model/results. No papers/pre-prints as of yet, but I'll update this when I get more
information.

There was also some talk that mentioned some work involving evolution in a phenotype landscape giving phase
transitions. Aboslutely no detail in the talk, so will have to look at the papers to see if the modeling
is interesting/relevant.

**Papers**

* Phase transition in [phenotype model](https://scholarsmine.mst.edu/doctoral_dissertations/2270/),
[followup work](https://royalsocietypublishing.org/doi/full/10.1098/rsos.170005)

## Immunology

There were a few talks on immunology; however, most were about modeling specific biophysical situations
involved in adaptive immunity. On the evolutionary theory side, there was the above mentioned phenotype
modeling talk. There was also a talk by Andreas Mayer (working with Bialek et. al.) to try to model the
genetic diversity of human antibodies as compared to the DNA of pathogens, specifically by looking
at the distribution of $$k$$-mers (usually for $$k = 9$$). The idea was to see if there was signal that
the immune system could theoretically use to distinguish self from non-self. They used a simple
pairwise interaction energy model which seemed to work ok.

There were differences between human and non-human; however, it was not clear how important those differences
should be. For example, things like GC content different gave very strong signal, but pathogens could
ostensibly modulate GC content in proteins that interact with antibodies. It is also unclear what
sorts of "discrimination technology" the body has access too - ostensibly, there are types of difference that
are hard to measure via antibody interactions. The basic idea is interesting though; I wonder if
machine learning methods (or at least, machine learning ways of asking questions) might be relevant/important
here, since what really might matter is the discriminability of a small number of proteins/parts of
proteins, and the pathogens have the capability to make at least small changes to avoid detection.

## Miscellaneous talks

Caught the tail end of a talk that was about trying to understand instabilities in reaction-diffusion type
systems using tools from standard non-linear dynamics theory (including phase portraits and nullclines).
There are [two](https://www.nature.com/articles/s41567-017-0040-5) [papers](https://arxiv.org/abs/1812.08684)
that might be worth looking at, especially in the context of the dynamical systems class.

Edo Kussell had some interesting [work](https://www.nature.com/articles/s41592-018-0293-7) about trying to
infer recombination rates in regimes where the recombination rate is similar to the mutation rate. They
tried to do this by constructing a model which had coalescent times both for each pair of individuals in
a sample, as well as an overall coalescent time. They then tried to measure the lengths of blocks that
were identical (or near identical) between individuals, and use the distribution of those blocks
in order to fit the timescales/rates. Seems like a nice choice for a journal club article.

Nicholas Noll (formerly with Boris Shraiman, now a post-doc with Richard Neher) had a nice talk about
trying to measure the rates of different recombination events in bacteria. I thought the framing of his talk
was really good - trying to motivate the question of what the "atom" of genomic analysis in the presence of
high recombination should be - in the same way that a tree is the right structure in the low recombination,
low diversity regime. Had some results as well, but I think the motivation was the star of this talk.

There were also a few talks on epistasis, which all gave the low dimensional, low order epistasis,
rugged landscape picture. Hopefully my paper comes out soon because there are a lot of lessons there
for people to internalize!

## Overall impressions

It seems that the eco-evolutionary dynamics subfield is gaining a lot of steam (at least among physicists).
Some of the high presence at the meeting was due to Jeff Gore organizing a bunch of sessions, but seems
to be of broad interest. Theoretically, still feels as if there is some separation between the ecological
aspects of the modeling, and the evolutionary aspects. The consumer resource models are very popular on
the theory end; I think I need to do a bit more to catch up but as far as I can tell. I think trying to add in
evolution and think of evolution-conditioning of things is a very open area.

Experimentally, it's still not yet clear to me what the good systems are. Most of the experimental talks I was
able to make it to seemed very limited in scope - mostly focussing on some particular phenomenology
of interest. Unfortunately missed some more of the ecological ones so can't comment too closely on this point.

Overall, I'm not a big fan of the statistics of APS - because there are so many short talks, it's hard to
get a good sense of any one thing. It's also hard to discern which work is deep and careful, and which work
is hiding serious flaws and limitations. Also, the sessions seemed too broad at times - for example, my talk
followed one about the mechanics of parasitic worms.

Still, was nice to give a talk that I thought was pretty good, both on its own merits and relative to the
surroundings. Feels good to have projects that I think are interesting scientifically!
