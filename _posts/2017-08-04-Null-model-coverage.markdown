---
layout: post
title:  "Null model for gap finding algorithm"
date:   2017-08-04
tags: [kitpQBio2017,eco-evo]
comments: true
---

Today's post will be about a simple null model for the distribution of "gaps" in coverage when metagenomic reads are mapped
against a reference genome. We can use this null model to try to detect places in the genome where a lack of coverage is real
and due to that genetic element not being present (at least not at high abundance) in the gene pool.

## Model definition

Suppose we have a genome of length $$L$$. Suppose we have a sample of $$R$$ reads, each of length $$\ell$$, which map
onto the genome. Further suppose that these reads are distributed evenly across the genomes. We then define a _gap_ as a
continuous region on the genome that has no coverage - that is, a consecutive string of nucleotides which have no
reads mapping to them. Under this model, what is the empirical distribution $$\hat{\rho}(g)$$, where $$g$$ is the size of a
gap?

## Simplifying assumptions



## Relaxing model assumptions

This model makes some strong assumptions. First, it assumes uniform read length and coverage across the genome. Both of these
are expected to fail; reads will have some distribution (though this distribution will be quite narrow for Illumina reads),
and more importantly there will be areas of the genome which naturally have higher or lower coverage. One easy
way to extend the model would be to try to see the effects of different distributions of coverage and read sizes. A simple
approach would be to take these distributions from a dataset of interest to see if the data can inform the model.


