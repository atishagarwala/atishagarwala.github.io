---
layout: post
title:  "Project assignments and random thoughts"
date:   2017-07-25
categories: bio,evolution,ecology
tags: [kitpQBio2017,eco-evo]
comments: true
---

Another day of talks, and we got our project assignments. Also I pipetted for the first time!

## Talks

Bruce Levine gave a really nice talk about various topics in microbiology. He went through the history of things like
the nature of mutations, bacteriophage, and more and gave his thoughts on interesting directions (spatial structure
and phage interaction). Favorite quote: "Evolution is about dN/dt and not dN/dS."

Erdal Toprak talked about his work with the morbidostat and evolution of antibiotic resistance. Cool dataset, but was
left a bit unsatisfied. He presented fitness landscapes based on minimum inhibitory concentration, but I would have
really liked to see some estimation of what the selective effect for each mutation was when it arose. Something similar
to this was shown with some work estimating the yield of the reaction catalyzed by the resistance encoding proteins, would
have been cool to see if that changed the predictability of evolution.

Also as always there was the question of how to talk about epistasis. Epistasis was described here again with pairwise
interactions, with the magnitude/sign epistasis language which I really abhor. I guess that sort of description is not
too bad when the number of mutations is small, but even here with 5 mutations higher order epistasis definitely mattered.
Wonder how best to talk about epistasis with a small number of mutations - I still think the pairwise epistasis inspired
language is not great, but maybe the way I talk about things is a bit too broad.

It was interesting to think about/see
a scenario where under strong selective pressure only a few mutations seemed to matter. I wonder what it's like during an
actual infection where there are more cells/the selective pressure (antibiotic concentration) has a different temporal
profile. Also, apparently a lot of the protocols used for administering antibiotics seem somewhat arbitrary - someone
set them up at some point, they seem to work ok, but haven't really been tested.

Relatedly, talked to Portia about her project studying a fitness landscape of a few mutations which confer antibiotic
resistance. Here she generated landscapes with respect to a whole bunch of drugs, and actually measured growth rates - 
that is, things that are in the right units to understand evolution! The idea was to predict cycles of drugs
which would lead to reversion to the wild type. Definitely a cool idea, to try to understand something about
the fitness landscape and take advantage of dynamics to prevent strains with multiple resistances from arising.
Still, I wonder about two things: one, will there be other sites on the genome which will give benefits? Once we get to
high dimensions, this kind of manipulation may become harder. Secondly, how long do non-optimal genotypes
last in these populations?

For example, if a strain was resistant to drug A, but in the presence of drug B reverting
to the ancestral phenotype was beneficial and it began to do so, how long to the strains resistant to A persist? If it's
long enough, they may rise up again when A comes back. If they are still at some non-trivial number, they may cause
resistance to flare up again faster than it would if resistance to A established via mutation alone. Would be good
to get some of the numbers to play around with to try and get at the plausibility of different scenarios. 
I guess a related question would be, how often does resistance arise from standing variation rather than de novo mutation?

Also had a good chat with Otto Cordero about various topics. He mentioned that phage may attack mobile genetic elements
in bacteria more than other ones - which may mean that I should think about recombination in my bacteria-phage
coevolution stuff. I think a postdoc from his lab is going to talk about this at some point, and he's giving a talk
later in the week, so hope to learn some more about the actual biology of the problem I'm thinking about!

## The project

Looks like we'll work on 2 projects, one for the first two weeks, and another for the second two weeks. The first two
weeks I'll be working on the ecology of cellulose eating bacteria with (Steven Quistad)[http://www.stevenquistad.com/].
In short, they passaged 10 different communities sampled form compost in minimal media with cellulose (ie a piece of
paper) as a carbon source. They transferred the microbes once every two weeks for a year. Each community was
passaged in one of two ways: first, there was the *Vertical* group, which was passaged normally. Second, there
was a *Horizontal* group which, every time it was passaged, also got some "phage juice".

This phage juice consisted of a sample from all 10 horizontal groups, mixed together, and filtered of all particles larger
than 2 microns. This means that the juice should just consist of chemicals, DNA, and possibly bacteriophage. The idea
is that the horizontal group is getting some genetic elements shared across all the communities, and there is possibility
of horizontal gene transfer. If some useful gene gets to high frequency in one population, it may be transferred to the
other vials and uptaken there.

I think this is a pretty cool experiment, because it has the possibility of both having interesitng community dynamics
(with the vertical alone), and says something about migration/horizontal gene transfer (with the horizontal treatment).
It would be cool if both inter and intra line information could be combined to do things like assess community
evolution and stability, new genes sweeping through the population, and the rate of recombination events. Stay tuned
for what direction me (and the other students) will take this in! Really excited to work on this, was my first choice
of all the projects. I'll be working on a project with millifluidics in weeks 3 and 4, and will talk more about that
when I get there.
