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

## Definitions

Suppose we have a genome of length $$L$$, 
