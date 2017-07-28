---
layout: post
title:  "Paper project brainstorming"
date:   2017-07-26
tags: [kitpQBio2017,eco-evo,paperproject]
comments: true
---

Had our first meeting with the "Paper project" group, looking into the ecology of a community degrading cellulose (with
possible induced HGT). Right now we're trying to figure out what we want to do for a project. Figured I'd write down some
ideas I've had here, in order to organize thoughts.

## Data and experiments

The data we have are:
* Metagenomic short reads from T0 (before splitting into vertical and horizontal treatments), T 1-4, T10, T16, and T24.
* 20 whole genomes from T24 and from T16 (one for each flask). One set of genomes is from pseudomonas, the other are from
random individuals.

In addition, we have samples from T0, T16, and T24. We have the capability to do the following experiments:
* Cellulose degradation assays.
* Plating/colony growth
* Illumina sequencing
* 24 nanopore sequence runs

The latter will ostensibly be used to assemble some more whole genomes.

We need to figure out what to do with the data/experiments. The main thing that needs to be decided on as a group is the whole
genome sequencing; the rest may require some coordination/working together, but if people have different ideas/directions they
want to go in those all can probably be pursued.

## Specific questions

Some scientific questions I think would be fun to answer are:


### What is the rate of recombination in the population?

Could we use the recombination sites inferred by the gaps
(and maybe checked by other methods) to try to estimate the level of recombination in the population? This may require
either additional genomes at the final timepoint, and/or access to the ancestral strain. At the very least,
recombination induced by the "phage juice" could be estimated. Here, in order to not get tripped up by
amplification by selection/hitchiking, we may want to find "neutral" recombinations (either by looking in specific
genes, or by finding recombination events which can be traced to the original flask). One big confounding factor
of course will be the composition of the phage juice.


### Can we find additional evidence that the gaps are due to recombination?

Would like to try to find breakpoints, to rule
out the possibility that adaptive bacteria are the only ones who got transferred. Could also see if putative phage
sequences are in the recombining gaps.

### What fraction of recombination events are homologous?

Getting quantitative estimates of this could be cool. One thought I had was to find the timepoint before
the recombination event was thought to have occured, and then try to match things into the gap allowing more
and more error. Then you'll have a curve of coverage vs. allowable error, which will be increasing; if the derivative
of this curve is high at a low error rate, then perhaps homologous recombination has occured. As a control, one could do
the same for some region which is spanned.

### What fraction of recombination events are related to selection?

If there is a recombination event which happened in the first four timepoints, maybe we can see the selective
effects of these recombinants. Could give some indication of the evolutionary value of the recombinations, and
as to how much recombination is enriched by selective recombinants.


### What does the diversity at finer scales look like in the flask/between flasks?

Would be interesting to look at
subspecies abundances, to see if there is a lot more diversity there as well. Could take 16s or something and try to use
a minimal clustering/cluster free approach. Would need some checks here like distance from large types, and correlation
across timepoints.


### What does the ecological dynamics look like?

Once we have something that looks like abundances of types, we could try to look at the dynamics. Could do so on multiple
scales of clustering, to see how much substructure there is in the population. Things to look at would include correlations 
between relative abundances.

We could also possibly try to indirectly figure out how the gene content of different types has changed by the end of the
evolution. We could take the first few timepoints and see what reads that map to genes are correlated with what OTUs.
If there are some OTUs which have the same ratio with hits to a gene consistently over a few timepoints, then we can say
that the gene is probably only present in the OTU. We can then 


Some technical challenges which will have to be overcome for some of these questions:

### How can we estimate relative abundances from the metagenomics data?

We need to figure out to what extend abundances in the short reads actually correspond to abundances of types. Would be
good if we can figure out checks on this - maybe by looking at the distribution of coverage with respect to the reference
genome? Could also look at specific regions which are thought to be either highly variable or not very variable.

### How can we error correct 16s etc to low distances?

Could be worth coding up a much simpler DADA/something like what Tikhonov did in his paper.

### What is the right null model for gaps/the distribution of gaps?

Two thoughts here: one to just think about the combinatorics. The other would be to assume that any gaps in the vertical
transmission are spurious, and to look at their distribution.

## Thoughts about the sequencing

There is also the question of what should be whole genome sequenced. Paul suggested one approach would be to look at the
early times and try to track down the ancestors of some of the later time guys. Rachel suggested just sequencing random guys
at late times would be good just to see what's in the population.

I think it would be good to spend some (maybe half?) of our sequences on the late timepoint, to get a sense of the
diversity of types/shared or unshared nature of gaps which may indicate horizontal gene transfer. For this reason I think
going for the pseudomonas in particular would be good, just to reduce the search space. Perhaps at the same time,
we can spend some Illumina sequencing to try and see if there are types which look like the ancestors of sequenced guys.
If so, then we can try to sequence them; otherwise, just sequence more guys at late timepoints.
Also, I think we should sequence in lines which contributed a lot to horizontal gene transfer (by the gaps)

## Proposed plan of attack

For the questions I'm interested in, I think what I'd want to do would be:

* Try to see if there is breakpoint signal.
* Try to understand how read abundance relates to actual abundance.
* See if my method of finding homologous recombination would make any sense.
* Try to get out the (corrected) 16S abundances.
* Track 16S dynamics over time.
* See if any genes correlate with specific 16S subtypes.
* Look at late time whole genomes, find recombinations which occured early, and try to estimate their fitnesses.

Probably more than 2 weeks of work, especially if I'm just learning the tools, but I think if I get started, I'll be
able to complete at least one of the directions. At any rate excited for the next 1.5 weeks!
