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

## Computing expectations

As posed, we want to find a distribution of distributions - the probability distribution over empirical distributions.
In general, this is a complicated problem. However, we can show that
computing $$n(g)\equiv{\rm E}[\hat{\rho}(g)]$$, the expected number of gaps of size $$g$$, is a far more tractable task.

There are $$L-g$$ potential gaps of size exactly $$g$$. Suppose that $$g\ll L$$, so this number is well approximated
by $$L$$. (We will later see that this is a reasonable assumption for large $$L$$.) If we can compute the probability
that any of these individual blocks is a gap, we can compute the expectation exactly.

For a region of length $$g$$ to be a gap, and not be contained in any other gap, there must be no reads
in the block, and at least one read flanking each side of the gap. We can compute the probability
of such an event directly. We label the gap by the integers $$0$$ to $$g-1$$, inclusive.
We adopt the convention that a read starts at the lowest included 
number and ends at the highest. Our condition
then amounts to:
* No reads which start from $$-(\ell-1)$$ to $$g-1$$ inclusive.
* At least one read which starts at $$-\ell$$ and at least one which starts at $$g$$.

We start with the computation of the probability of the first event. There are $$g+\ell-1$$ positions
which can't have a read start; this gives us

$$P(\text{no gap reads}) = \left(1-\frac{g+\ell-1}{L}\right)^{R}$$

If $g-\ell-1\ll L$, we have

$$P(\text{no gap reads}) \approx e^{-(g+\ell-1)R/L}$$

We now need to calculate the probability that there is at least one read flanking either side of the
gap, given that there are no reads in the gap. Let $F_{1}$ and $F_{2}$ be the events that there
are reads flanking the left and right sides of the gap respectively. We have

$$P(F_{1}\text{ AND }F_{2}|\text{no gap reads}) = 1-P(\text{NOT }(F_{1}\text{ AND }F_{2})|\text{no gap reads})$$

which we can write in terms of the individual flanking probabilities as

$$P(F_{1}\text{ AND }F_{2}|\text{no gap reads}) = 1-P(\text{NOT }F_{1}|\text{no gap reads})-P(\text{NOT }F_{2}|\text{no gap reads})+P(\text{NOT }F_{1}\text{ AND }F_{2}|\text{no gap reads})$$

These probabilities can be computed as:

$$P(F_{1}\text{ AND }F_{2}|\text{no gap reads}) = 1-2\left(\frac{L-g-\ell-2}{L-g-\ell-1}\right)^{R} +\left(\frac{L-g-\ell-3}{L-g-\ell-1}\right)^{R} $$

We can rewrite and use the large $L$ approximation again:

$$P(\text{flanking}|\text{no gap reads}) = 1-2\left(1-\frac{1}{L}\right)^{R} +\left(1-\frac{2}{L}\right)^{R} \approx (1-e^{-\frac{R}{L}})^{2}$$

We can factor out the genome length $$L$$ by defining the per nucleotide coverage $$C\equiv \frac{\ell R}{L}$$.
The expected number of gaps $$n(g)$$ is given by

$$n(g) = L P(\text{no gap reads})P(\text{flanking}|\text{no gap reads}) \approx L(1-e^{-C/\ell})^{2}e^{-Cg/\ell}e^{-C(1-1/\ell)}$$

If $$\ell\gg1$$ as well, we have

$$n(g) \approx L(1-e^{-C/\ell})^{2}e^{-C}e^{-Cg/\ell}$$

We have a roughly exponential distribution, with scale $\ell/C$ and total number of gaps given by
$$ \frac{\ell L}{C}(1-e^{-C/\ell})^{2}e^{-C}$$. The "typical" largest gap approximately occurs when
$$\sum_{g = g_{max}}^{\infty}n(g) = 1$$, which occurs at

$$g_{max} = \frac{\ell}{C}\ln(\ell L/C(1-e^{-C/\ell})^{2}e^{-C}) = \frac{\ell}{C}\ln( L^{2}R^{-1}(1-e^{-C/\ell})^{2}e^{-C})$$

For low coverage ($$C\ll\ell$$), the total number of gaps is roughly $$\frac{CL}{\ell}e^{-C} = Re^{-C}$$ and 
$$g_{max}\approx \frac{\ell}{C}\ln(L^{2}C^{2}/R\ell^{2}e^{-C})$$, or $$g_{max}\approx \frac{\ell}{C}\ln(Re^{-C})$$.
This makes sense; as $$C$$ goes to zero there are $$R$$ total gaps, which corresponds to the space between adjacent
reads, which are all non-intersecting.

The cumulative distribution functions are often useful, as they transform nicely
under rescalings. Additionally, if we are using the null distribution to filter out spurious gaps, we can
use the CDF to define a cutoff. Let $$N(g)$$ be the number of gaps with length greater than $$g$$. We have

$$ N(g) = \frac{\ell L}{C}(1-e^{-C/\ell})^{2}e^{-C} e^{-Cg/\ell}$$

or, in the low coverage case,

$$ N(g) = Re^{-C} e^{-Cg/\ell}$$

## Model validity and relaxations

The expectation function $$n(g)$$ will be a good approximation of the empirical distribution when the genome is 
long
compared to the read lengths and the 
typical (or perhaps somewhat) block lengths. In this case, we can think of dividing the genome into sublocks
which are each statistically independent in terms of gap distributions. This is true up to the block-spanning
gaps, which may contribute to the tail of the distribution. One can compare the tails of the blocked and full
expectation distributions to try to understand when there are many such roughly independent blocks, and 
therefore
when the empirical distribution is close to the expectation. Furthermore, the fact that the distribution does
not have heavy tails suggests that the expectation function will well characterize the 



This model makes some strong assumptions. First, it assumes uniform read length and coverage across the genome. Both of these
are expected to fail; reads will have some distribution (though this distribution will be quite narrow for Illumina reads),
and more importantly there will be areas of the genome which naturally have higher or lower coverage. One easy
way to extend the model would be to try to see the effects of different distributions of coverage and read sizes. A simple
approach would be to take these distributions from a dataset of interest to see if the data can inform the model.


