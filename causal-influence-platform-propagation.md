A cursory informal outline of a project I am working on related to tech policy.
# Introduction
This project aims to measure the effect of an adversary on an election. The main dynamic of concern is that of a consensus: if everyone gets a vote and the winner of the count takes all.

## Want to study
We aim to bring clarity to a class of causal questions over sparse graphs.

A socially relevant curiosity is to quantify the effect of social media influence, and how much power an adversary would have on election outcomes.

There are many subquestions associated with this train of thought, in relation to real questions in technical policy:

1. Should we ban subcommunities that encourage self-harm on Twitter as to reduce self-harm in teens?
2. Are there effective tests to see if a platform, or a new social media feature will cause outsized influence?
3. Does the bidding algorithm in ad-targeting over a social network behave degernerately for a subpopulation over time?
4. Is setting a proper size limit of facebook group useful for limiting adversarial manipulation?
5. Is it appropriate to punish those who spread "fake news"? If so, how do we quantify harm?

## The eventual goal
Policy recommendation with regards to emerging technology for the integrity of social systems.

## Contributions
Novel modeling approach to complement existing techniques in political science on the effect of emerging technology.

* Theorectical results to intuit platform amplification dynamics.
* Theorectical bounds for deriving the impact of potential adversaries and practical ramifications.
* A set of simulation tools to test out effects of real world graphs and different treatments.

# Approach

The approach is interdiscinplinary, borrowed from economics, social dynamics, data science, with consultation with political scientist. This section is broken down into causal models, dynamical systems, network modelling, belief modelling, and a summary of comparative advantage.

## Causal Models

Causal modeling is used as an alternative to direct experiments. Given that performing trials as adversaries to societal integrity is generally considered unethical, we need some other way to model the effect of potential adversaries. Causality is a strong part of this picture. For clarity, this section is divided between a "zoomed-out" and a "zoomed-in" perspectives.

### Aggregate Question
Given that information and platform amplification on a population, how does the resulting consensus result get affected?

**Passive**
Platform Amplification-?-> Election Swing <-{ Network Topology, Initial Condition, New Information}

Note that in causal modelling, this graph "includes" the interactions between causes such as new information X platform amplification.

**Adversarial**
We add adversary to this model.

Platform Amplification -> Election Swing <-{ Network Topology, Initial Condition, New Information}

### Individual Influences
Only starring at the aggregate graphs, there are some unanswered questions, so we zoom in on an individual at a particular moment. This involves heavy handed "belief modeling", but clarifies time and graph dependencies on the way platform amplification acts on an individual's decision to participate (i.e. Turnout).

(Prev.) Turnout -> Future Turnout <- Received Information
(Prev.) Belief -> Future Belief <- Received Information

The explicit interaction between belief and turnout are not needed (flexible within model capacity), thus omitted here.

## Network Modeling
For a population of N agents and M broadcasters form graph G of (N+M) nodes, with binary belief and turnout probability, information flows passively along the edges. This is the basis where platform amplification and adversarial activities are added.

Empirically, individual experiences over the same network may see their experiences differ dramatically due to locality.

Platform amplification effects are highly related to network topology, as information flows along the edges of the graph. In addition, altering the underlying recommendation algorithms along the graphs can mediate the effects of platform amplification.

**Note** Influences along graphs can be calculated in many ways. In social media platforms, however, the ranking among people is often centrality-based.

## Dynamical System
The change of belief and turout under varied influences is characterized by a discrete time simulation. This simulation is a relaxation of continuous-time changes.

Per individual, belief is a unitary vector over various "issues" i.e. the dictionary, while turnout is a probability.

Per time, platform amplification re-normalizes turnout probability along the graph through two forms
1. Enhancing well-connected agents
2. Promoting certain broadcasters at random

## Belief Modeling
Belief is a high dimensional vector over various "issues". The parametrization of belief satisfies some nice properties, such as flexibility to model through a survey with non-orthogonal basis, stability over time, etc.

### Turnout vs. Belief vs. New info
Belief is a transformation acting on Turnout, whereas new information is normalized to act on both belief and turnout. Note that belief is considered stable. Empirically, this means regardless how much beliefs on various issues change, where the voter lies on a fundamental (low dimensional) political spectrum does not over a short period of time.

### Confirmation bias
Belief itself is important to keep track of because people are subjected to confirmation bias i.e. misplaced causal attribution that causes change of belief *only* when the new information has sufficient alignment with current belief.

## Pitfalls of existing techniques
Here are some of the issues I saw that the current model addresses.

* Aggregate population-level regression ignores individual choices and their connective peroperties.
* Conflating turnout and belief changes. (Belief modeling is a big one.)
* Ignores turnout in modeling consensus-crucial consequences.
* Measures aimed at predicting expected election outcome, rather than the distribution of outcome.
* (*) In inference on real data, too few parameters are provided, often making the set of reachable models restricted, so the fit actually tends to be an *overfit*.
* (*) In inference on real data, the model is very sensitive to the selection bias of data, as it is treated as ground truth.
* Ignores graph structure.
