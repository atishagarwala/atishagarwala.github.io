---
layout: post
title:  "Paper project brainstorming"
date:   2017-07-26
categories: bio,evolution,ecology
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
the recombination event was thought to have occured,

### What fraction of recombination events are related to selection?

If there is a recombination event which happened in the first four timepoints, maybe we can see

Some technical challenges which will have to be overcome for some of these questions:

### How can we estimate relative abundances from the metagenomics data?

We need to figure out to what extend abundances in the short reads actually correspond to abundances of types. Would be
good if we can figure out checks on this - maybe by looking at the distribution of coverage with respect to the reference
genome? Could also look at specific regions which are thought to be either highly variable or not very variable.

### How can we error correct 16s etc to low distances?

Could be worth coding up a much simpler DADA/something like what Tikhonov did in his paper.

### What is the right null model for gaps/the distribution of gaps?

Two thoughts here: one to just think about the combinatorics. The other would be to 

* **What fraction of recombination events are homologous?** Getting quantitative estimates of this could be cool.
* **What does the diversity at finer scales look like in the flask/between flasks?** Would be interesting to look at
subspecies abundances, to see if there is a lot more diversity there as well.
*  **What does the ecological dynamics look like?** Would also be interesting to try to track the dynamics of different types
as the evolution proceeds.


## Thoughts about the sequencing

## Thoughts about other data analysis

## Proposed plan of attack
