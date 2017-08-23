---
layout: post
title:  "KITP Qbio recap and thoughts"
date:   2017-08-22
tags: [kitpQBio2017,eco-evo]
comments: true
---

This post will be a place for me to dump my thoughts about things I did/learned
at the KITP 2017 Qbio course, especially as it relates to my research.

## Ecological data analysis

One specific theme that kept arising in the talks, especially those about real
microbial systems was the difficulty in analyzing ecological data. It seems to
be hard to infer things from these metagenomic datasets.

There were a couple of talks which touched on this; Otto Cordero's work[^otto]
seems to
use a lot of analyses of entropy. Joshua Weitz had some stuff on trying to
explicitly model time series data with short sampling[^weitz]; however, I think
this is
similar to stuff already done on the microbiome which usually ends up
uncompelling. Aleksandra Walczak has some new stuff[^walczak] on analyzing things
for
similar habitat dependence which I haven't read yet but looks interesting.

Overall, I'm still not convinced that we can tease apart interaction in complex
ecosystems where a bunch of guys are going to matter. We may be able to do so
when a lot of types have similar interactions (eg when we can tease apart coarse
metabolic pathways). I think getting some kind of sense of similarities between
different guys (like in the Tikhonov sub-OTU paper) could be a way to proceed;
maybe doing some sort of clustering/PCA type thing on the time series? Another
thought would be to analyze time series like people analyze natural language
data - give two types a similarity score based on whether or not they are
associated with the same sets of other types. Still a lot to think about here.

I also befriended a marine virologist, Gur Hevronig, who is a grad student at
the Technion. He's working on a project to understand the dynamics of bacteria
and phages in the ocean. He has a really cool dataset with bacterial and phage
abundances for 2 hour intervals in the ocean at different times of year. I may
try to do a group meeting presenting his data to try to brainstorm different
approaches to understanding that type of data.

## Ecology theory

There were a couple of talks on theoretical ecology, both of them focusing
on resource-consumer models. Pankaj Mehta talked a bit about some cavity
method calculations in MacArthur resource models[^mehta], is working
on a model with cross-feeding. Ned Wingreen talked about a model with tradeoffs
which lets an arbitrary number of guys survive on a fixed number of
resources[^wingreen]. However this model requires some strong linearity
assumptions, which in general should not be true. Might be interesting to think
about perturbations of that model which have long decay timescales. There
was also some talk that ecological systems could self organize to that
sort of state but I don't really understand those things to be honest.

I think the main takeway I came with from talks on the actual biology
with regards to directions for theory was the importnace of metabolism.
There were quite a few talks about metabolism, and many people working
in the field seem to think that this will be the only reasonable way to
understand the complexity in nature. Alfred Spormann gave a couple of lectures
on this in simple systems, and Otto Cordero espoused this view in both of his
talks.

It seems that for the systems presented (eg Rachel Dutton's cheese model
community), the first steps to understanding will be based on the large abundance
taxa which are doing things like adjusting pH, breaking down complex
carbohydrates, and producing antibiotics. The "physicists view" of analyzing
a large number of types may not be a useful idea here, where the particulars
of the environment tell us a lot about what may or may not happen. This
does need to be taken with a bit of a grain of salt though; right now people
are trying to work on communities chosen for their apparent simplicity.
Not sure if one needs to think about a bunch of different simple communities
or one complex one. The truth is both approaches are going to be useful for
different things.

It might be useful to think about metabolism and tradeoffs, and see if there
are some ways of getting the flavors of these processes into models. Not sure
how to do this - maybe with some resource model that has a cascade of energy
scales, and seeing what can evolve on top of that? Another thought would be to
try to see what metabolic relationships/tradeoffs would say about the statistics
of interactions.

The question of diversity may almost be something done on a "background"
of metabolism/trophic levels/etc. There is certainly some structure coming
from these different metabolic pathways, and the presence/absence of
different species set the availability (and sometimes the existence)
of different resources. However the diversity seen in nature seems to be
beyond this, so while understanding the metabolic flows might be enough
for a coarse understanding the finer scale details may be independent
(or at least less determined by) the broader metabolic flows. An interesting
question would be how this fine scale diversity feeds back into the
coarser structure as it's shaped by evolutionary dynamics.


## Bacteria-phage dynamics

There were a few talks on bacteria-phage dynamics, a model of which I've been
thinking about recently. Bruce Levin talked about some of the specifics of
viral biology, going into the differences between lytic phage (those that
just reproduce and burst the bacteria right away) and lysogenic phage
(which incorporate themselves into DNA, and bide their time before inducing
replication). He also talked about some experiments in chemostats where
bacteria evolve phage resistance pretty quickly. Paul Turner talked about
the use of phage in therepeutics, where they might be easier to "design"
against bacteria (ie by isolation and experimental evolution), and can be
used to both directly reduce bacterial number and more importantly
induce tradeoffs that make them less harmful/easier to hit with antibiotics.

Joshua Weitz talked a bit about analyzing data from ocean phage[^phageabundance]
and
modelling bacterial-phage coevolution. Some
papers of his are in the reading list below. There is some claim that stability
in these models is helped by having some sort of block structure to the
interactions; I need to go through and look at the modelling in more detail
to figure out what is going on there.

Overall the basic facts about bacteria-phage systems, things like
$$P<B<P+R$$ (where $$P$$ is phage, $$B$$ is bacteria, and $$R$$ is resources),
the fact that phage generally cause oscillations/etc,
seem to be well known; however, considering what happens when you have lots of
phage and bacteria has not really been done, nor have questions about
co-evolution been satisfactorily been answered.

While it isn't about bacteria-phage coevolution, Aleksandra Walczak has some
work on immune system coevolution[^immunocoevo]. Might be worth looking at
for inspiration.

## Random tidbits

There were a lot of other random talks not fitting into the above themes
that I thought were interesting. A non-comprehensive list:

* Phillip Messer gave a great talk on trying to understand the evolutionary
dynamics of CRISPR based gene drive technologies. A cool look into "applied"
pop gen.
* Terry Hwa talked about some work to understand motility in E. Coli, and had
some cool data/modeling showing some traveling waves of bacteria spreading
on plates through a combination of growth and gradient generated motility.
He also had a great lunchtime talk about his stuff on proteom allocation, which
had some good philosophical thoughts about research in quantitative biology.
* Paul Rainey had kind of a cool talk on REPINs, these really small genetic
elements which may be selfish elements which nonetheless may act as a sort of
primitive CRISPR system.
* There were a couple of talks on ideas of group selection and the evolution
of altruism, though I didn't find any particular one compelling in terms of the
modeling. Still was good to be exposed to thoughts in that area, and it might be
a fun thing to study sometime.
* Aleksandra Walczak talked about some immunology stuff, and I think she gave
a second talk the week after the course. Haven't seen the second one but the
first one was quite nice.

## Genomics - data analysis and genome structure

I'll conclude with some thoughts on technical things I learned during
the course. My main goal was to get more familiar with analyzing genomics data,
which I did get to do to some degree.

Got some exposure to doing bioinformatics type things. Did simple things like
mapping reads to contigs, making pileups, etc. Gives me more confidence in
doing some of the basics of analyzing sequencing data.

I also got some more exposure to various properties of genome structure. Things
like plasmids, transposable elements, codon bias, distributions of genetic
elements. May
be worth sitting down and learning some genomics properly sometime, though
not sure if it would be better to read some sort of papers/reviews, or read
through a textbook.

I think I still don't have enough of a sense of the properties of genomic data
analysis/genomes themselves. For many of these things I don't have a good
quantitative sense about when certain things matter, or what their significance
is.

Things I should try to learn at some point:

**Details about sequencing.** I learned a bit about the format of files coming
out of sequencing, and some basics about tools used to map/annotate.
I still don't have a good sense of some of the numbers involved, and what
the properties of the different technologies are.

**Facts about genome structure.** Even things like GC bias were new to me; I
think there are quite a few things I should know about analyzing sequencing data.
Things like frequency of different types of errors, probabilities of spurious
matches given fragment lengths, etc. Should maybe talk to Mike or Lily about
this sort of thing at some point. Specific questions:
* What sort of codon bias/GC content bias is observed across different types?
When is a differnece in GC content actually significant of something?
* What kinds of error rates are typical in various sequencing technologies? What
kind of forms do those errors take?
* How easy/hard is it to get DNA from one organism to map onto that of another?
How closely related do they have to be? Is there some way to get a sense of false
positives?
* What does coverage bias across a genome look like? What sorts of regions are
conserved enough to give lots of spurious hits? How can those regions be
identified/filtered out?
* How much can contigs from assemblies be trusted? How different is this for
metagenomic samples versus ones from clones?
* How good are abundance estimations from metagenomic samples? How does this
depend on what sorts of databases get mapped to? How does it depend on
which genes are actually being picked up?

**Knowledge of bioinformatics tools.** Ended up getting some exposure to things
like assembly (spades), mapping (bwa and fr-hit), annotation
(mg-rast,diamond), and data analysis/visualization (MEGAN). Might want to
get a sense of what other major players there are out there, so I don't
constantly reinvent the wheel.

**Better understanding of bioinformatics algorithms.** I learned a bit about the
various algorithms, such as the k-mer search approach that seems to be popular.
Even then, it seems that things like assembly involve some fiddling around with
different parameters to get things to work out. Some thinking about these issues
would be good, as would getting a handle on some of how different properties
of analyses scale with parameters/change with algorithms.


## Reading list

### Bacteria-phage

[Structure of interactions](http://www.pnas.org/content/108/28/E288.abstract)

[Multiple infections and spatial structure](http://iopscience.iop.org/article/10.1088/1478-3975/13/6/066014/meta)

[Phage-bacteria interaction networks](http://www.sciencedirect.com/science/article/pii/S0966842X12002004)

[Trophic levels and viruses](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4438322/)

[Inferring interactions from time series](http://rsos.royalsocietypublishing.org/content/3/11/160654)

[Nested infection network model](http://www.sciencedirect.com/science/article/pii/S0022519313001641)

[Viral abundance data](https://www.nature.com/articles/nmicrobiol201524)

[HIV analysis](https://elifesciences.org/articles/11282)

[Old E. Coli phage modeling paper](http://www.journals.uchicago.edu/doi/abs/10.1086/283134)


### Genome structure

[Model of metabolic network evolution](http://www.pnas.org/content/106/24/9743.short)

[Early paper on clustering (not sure if good)](http://rstb.royalsocietypublishing.org/content/361/1475/1917.short)

[Scaling laws in genomes](https://link.springer.com/content/pdf/10.1007/0-387-33916-7_14.pdf)


### Microbial ecology

[Review of community interactions](http://www.sciencedirect.com/science/article/pii/S1369527416300340)

[Succession on microparticles](https://www.nature.com/articles/ncomms11965)

[Species variance driven by habitat in microbiome](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005435)


### Ecology modeling

[Tradeoffs and diversity](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.028103)

[Cavity method in resource models](https://arxiv.org/abs/1707.03957)

[Tikhonov resource model](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.048103)

[Bunin community assembly](https://journals.aps.org/pre/abstract/10.1103/PhysRevE.95.042414)

[Renyi entropy as diversity measure](https://journals.aps.org/pre/abstract/10.1103/PhysRevE.93.052418)

### Immunology
[Well adapted immune organization](http://www.pnas.org/content/112/19/5950.short)

[Evolutionary dynamics of immune system](https://arxiv.org/abs/1703.00226)

### Cell biophysics

Terry Hwa proteom allocation work:

http://msb.embopress.org/content/10/8/747.long

https://thefauve.hwa.ucsd.edu/~thwa/pub/GrowthLaws-CurrOp.pdf

### Fun

[Crispr pop-gen model](http://www.genetics.org/content/205/2/827)

[REPINs (small transposable elements)](http://www.genetics.org/content/early/2017/06/19/genetics.117.201160)

[Minimum entropy production principle](http://bayes.wustl.edu/etj/articles/min.ent.prod.pdf)

## References

[^otto]: [Chitin community succession](https://www.nature.com/articles/ncomms11965)

[^weitz]: [Ecological interactions from time series](http://rsos.royalsocietypublishing.org/content/3/11/160654)

[^walczak]: [Habitat driven variation in microbiome](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005435)

[^metha]: [Cavity method in resource models](https://arxiv.org/abs/1707.03957)

[^wingreen]: [Tradeoffs and diversity](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.028103)

[^phageabundance]: [Viral abundance data](https://www.nature.com/articles/nmicrobiol201524)

[^immunecoevo]: [Evolutionary dynamics of immune system](https://arxiv.org/abs/1703.00226)
