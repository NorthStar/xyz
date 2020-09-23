A cursory, informal outline of a tech policy project I am working on. (*) means nuanced claims that deserve more real estate than what I provide.

# Introduction
This project aims to measure the effect of an adversary on an election. The main dynamic of concern is that of a consensus: everyone gets a vote and the winner of the count takes all.

## WTS
We aim to bring clarity to a class of causal questions over sparse graphs.

A socially relevant curiosity is to quantify the effect of social media influence, and how much power an adversary would have on election outcomes.

Many subquestions follow this train of thought, in relation to real concerns in technical policy:

1. Should we ban all sub-communities that encourage self-harm on Twitter as to reduce self-harm in teens?
2. Are there effective tests to see if a platform or a new social media feature will cause outsized influence?
3. Does the bidding algorithm in ad-targeting over a social network behave degenerately for some subpopulation over time?
4. Is setting a proper size limit of Facebook groups useful for limiting adversarial manipulation?
5. Is it appropriate to punish those who spread "fake news"? If so, how do we quantify harm?

## (eventual) Goal
Practical policy recommendations with regards to emerging technology for the integrity of social systems.

## Contributions
A novel modeling approach to complement existing techniques in political science on the effect of emerging technology.

* Theoretical results to intuit platform amplification dynamics.
* Theoretical bounds for deriving the impact of potential adversaries and practical ramifications.
* A set of simulation tools to test out effects of real world graphs and different treatments.

# Approach
To answer the interdisciplinary problem, we take an eclectic approach, borrowed from economics, social dynamics, data science, with consultation w/ political scientists. This section is broken down into causal models, dynamical systems, network model, belief model, and a summary of its comparative advantage.

## Causal Models

Causal modeling is used as an alternative to direct experimentation -- after all, performing trials as adversaries to societal integrity is generally considered unethical (*). Given that, we need some other way to model the effect of potential adversaries. Causality is thus a major part of this picture. For clarity, this section is divided between "zoomed-out" and "zoomed-in" perspectives.

### Aggregate Question
Given that information flows through platform amplification over a population, how does the resulting consensus result get affected?

Notably, this question becomes relevant after 2016. There the election result was surprising to many statisticians.

**Passive** For a sufficiently surprising election result, baselined against Initial Condition e.g. expected, projected, polled result, it is commonly known as a 'swing'.

This model is the base of further interactions. 

```Election Swing <-{ Network Topology, Initial Condition, New Information}```

**Amplified** Simply add amplification.

```Platform Amplification-?-> Election Swing <-{ Network Topology, Initial Condition, New Information}```

Note that in causal modeling, this graph "includes" the interactions between causes such as new information X platform amplification.

**Adversarial**
We add adversary to this model.

```Platform Amplification -> Election Swing <-{ Network Topology, Initial Condition, New Information, Adversary}```

### Individual Influences
Only starring at the aggregate graphs, there are some unanswered questions, so we zoom in on an individual at a particular moment. This involves heavy handed "belief modeling", but clarifies time and graph dependencies on the way platform amplification acts on an individual's decision to participate (i.e. Turnout).

(Prev.) Turnout -> Future Turnout <- Received Information

(Prev.) Belief -> Future Belief <- Received Information

{::nomarkdown}
<?xml version="1.0" standalone="no"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">

<svg width="600" height="215" version="1.1" xmlns="http://www.w3.org/2000/svg">
	<ellipse stroke="black" stroke-width="1" fill="none" cx="64.5" cy="45.5" rx="30" ry="30"/>
	<text x="53.5" y="51.5" font-family="Times New Roman" font-size="20">&#914;&#8320;</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="238.5" cy="45.5" rx="30" ry="30"/>
	<text x="227.5" y="51.5" font-family="Times New Roman" font-size="20">B&#8321;</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="64.5" cy="157.5" rx="30" ry="30"/>
	<text x="55.5" y="163.5" font-family="Times New Roman" font-size="20">&#964;&#8320;</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="232.5" cy="157.5" rx="30" ry="30"/>
	<text x="223.5" y="163.5" font-family="Times New Roman" font-size="20">&#964;&#8321;</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="404.5" cy="157.5" rx="30" ry="30"/>
	<text x="395.5" y="163.5" font-family="Times New Roman" font-size="20">&#964;&#8323;</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="404.5" cy="45.5" rx="30" ry="30"/>
	<text x="393.5" y="51.5" font-family="Times New Roman" font-size="20">&#914;&#8322;</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="115.5" cy="102.5" rx="30" ry="30"/>
	<text x="105.5" y="108.5" font-family="Times New Roman" font-size="20">&#948;&#8320;</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="281.5" cy="102.5" rx="30" ry="30"/>
	<text x="271.5" y="108.5" font-family="Times New Roman" font-size="20">&#948;&#8321;</text>
	<polygon stroke="black" stroke-width="1" points="308.887,114.746 377.113,145.254"/>
	<polygon fill="black" stroke-width="1" points="377.113,145.254 371.851,137.424 367.769,146.553"/>
	<polygon stroke="black" stroke-width="1" points="308.719,89.886 377.281,58.114"/>
	<polygon fill="black" stroke-width="1" points="377.281,58.114 367.92,56.941 372.125,66.014"/>
	<polygon stroke="black" stroke-width="1" points="142.719,89.886 211.281,58.114"/>
	<polygon fill="black" stroke-width="1" points="211.281,58.114 201.92,56.941 206.125,66.014"/>
	<polygon stroke="black" stroke-width="1" points="94.5,45.5 208.5,45.5"/>
	<polygon fill="black" stroke-width="1" points="208.5,45.5 200.5,40.5 200.5,50.5"/>
	<text x="128.5" y="66.5" font-family="Times New Roman" font-size="20">belief</text>
	<polygon stroke="black" stroke-width="1" points="94.5,157.5 202.5,157.5"/>
	<polygon fill="black" stroke-width="1" points="202.5,157.5 194.5,152.5 194.5,162.5"/>
	<text x="119.5" y="178.5" font-family="Times New Roman" font-size="20">turnout</text>
	<polygon stroke="black" stroke-width="1" points="262.5,157.5 374.5,157.5"/>
	<polygon fill="black" stroke-width="1" points="374.5,157.5 366.5,152.5 366.5,162.5"/>
	<polygon stroke="black" stroke-width="1" points="142.65,115.263 205.35,144.737"/>
	<polygon fill="black" stroke-width="1" points="205.35,144.737 200.237,136.809 195.983,145.859"/>
	<polygon stroke="black" stroke-width="1" points="268.5,45.5 374.5,45.5"/>
	<polygon fill="black" stroke-width="1" points="374.5,45.5 366.5,40.5 366.5,50.5"/>
</svg>
{:/}
The explicit interaction between belief and turnout are not needed (flexible within model capacity), thus omitted here.

## Network Modeling
For a population of N agents and M broadcasters that form graph G of (N+M) nodes, with belief and turnout probability, information flows passively along the edges. This is the setup upon which platform amplification and adversarial activities are added.

Empirically, individuals over the same network may see dramatically differing experiences due to locality in the network.

Platform amplification effects are highly related to network topology, as information flows along the edges of the graph. In addition, altering the underlying recommendation algorithms along the graphs can mediate the effects of platform amplification.

**Note** Influences along graphs can be calculated in many ways. In social media platforms, however, the ranking among people is often centrality-based.

## Dynamical System
The change of belief and turnout under varied influences is characterized by a discrete time simulation. This simulation is a relaxation of continuous-time changes.

Per individual, belief is a unitary vector over various "issues" i.e. the dictionary, while turnout is a probability.

Per time step, platform amplification effect re-normalizes turnout probability along the graph through two forms
1. Enhancing well-connected agents
2. Promoting certain broadcasters at random

## Belief
Belief is a high dimensional vector over various "issues". The parametrization of belief satisfies some nice properties, such as flexibility to model through a survey with non-orthogonal basis, stability over time, etc.

### Turnout vs. Belief vs. New info
Belief is a transformation acting on Turnout, whereas new information is normalized to act on both belief and turnout. Note that belief is considered stable. Empirically, this means regardless how much beliefs on various issues change, where the voter lies on a fundamental (low dimensional) political spectrum does not over a short period of time.

### Confirmation bias
Belief itself, though usually hidden, is important to characterize, because people are subjected to confirmation bias i.e. misplaced causal attribution that causes change of belief *only* when the new information has sufficient alignment with current belief.

## Pitfalls of existing techniques
Here are some of the issues I saw that the current model addresses.

* Aggregate population-level regression ignores individual choices and their connective properties.
* Conflating turnout and belief changes. (Belief modeling is a big one.)
* Ignores turnout in modeling consensus-crucial consequences.
* Measures aimed at predicting expected election outcome, rather than the distribution of outcome.
* (*) In inference, too few parameters are provided, over-restricting the set of reachable models, so the fit actually tends to be an *overfit*.
* (*) In inference, the model is very sensitive to the selection bias of data, as it is treated as ground truth.
* Ignores graph structure.
