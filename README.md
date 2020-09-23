@ Mimee Xu
# Bio
PhD student in New York. mimee AT nyu.edu

I work on machine learning and security.

**"Where are you really from?" and other questions.**
I was born and raised in Beijing, China, where I was introduced to the wonderful worlds of mathematics and the Chinese language. I moved to Vancouver, Canada for a good portion of high school to have an art education. Sometime during then, I changed my mind and studied math and computer science at Harvey Mudd College in Claremont, CA. I worked in the tech industry in Silicon Valley: Google's Chrome Browser, Baidu's speech recognition research, and UnifyID's password-replacing products. I moved to New York in 2019.

### ML for systems workshop (NeurIPS 2020, 2019)
[**Workshop CFP is up!**](http://mlforsystems.org)
As part of the organizing committee, I am soliciting submissions that apply machine learning to systems, such as

- Supercomputing
- Hardware optimization
- ML-driven compiling
- Smart optimization across stacks
- Open source hardware


# Resrach Ideas
My work falls under three rough categories
1. Mean-field analysis for causality in social media amplification.
This abstracts social media recommenders to an influence on election outcomes. [Project intro page.](causal-influence-platform-propagation)

2. Towards secure transaction and fair pricing of training data.
There are four parts to this work ⬇️.

3. Learned containment: generated sandbox by repeated fuzzing and patching.
Seeking collaborators.


## A Model for Network Influence
- work done as part of the coursework on Applied Causality (a seminar with David Blei @ Columbia University).
**Abstract** In November 2016, when all the polls predicted a Clinton presidency, America got Trump. Assuming that the pollsters had sampled real sentiments from real voters, what could be the *cause* for the shift in election result? This is rather hard to untangle, since very few entities have the data on social networks' topology. There is also the challenge of assessing cyclic causes over time, akin to studying a network influence question: does the eating disorder community on the internet *cause* eating disorder? This work explores different high level aspects of network influence via a mean-field approach across average networks, controlling for variance of election outcomes away from the fundamentals. The goal of this exploration is to offer a simulation and theoretic model, a combination that clarifies qualitative phenomena and evaluates potential policy interventions with impact.

### Survey on Mean Field Methods In Deep Learning
- done through math in deep learning coursework (with Joan Bruna @ New York University).

I wrote a [survey paper](https://www.notion.so/Survey-Paper-f26b8ea46bf34da1858f819c5d7e58dd) that helps me understand 1) Mean-field methods, and 2) a physicist-style modeling, which I applied to qualitative political science.

### A worry-free encryption plan for healthcare

- Work done at Microsoft Research Private AI Bootcamp
w/ Leo de Castro, Rami el Khatib, and Erin Hales

**Abstract** Healthcare in the US is notoriously expensive and unsustainable. Many machine learning startups aim to simplify the process by bringing in automated expertise to hospitals on radiology, brain imaging, or cancer detection. On the other hand, it is well-known that hospitals cannot easily share data. Existing machine learning solutions tend to focus on training with data obtained through long-term collaboration because the private computation requires that the clients have done appropriate pre-processing. Effectively, they work *around* the data-sharing challenge in training rather than tackling it. As a result, their inference model is typically static, and does not adapt to changes continuously.

On the other hand, regulatory agencies need to uphold the ethics standards for healthcare professionals, but can only access hospital records in a delayed fashion. Despite their mandate to audit individual doctors, assess response rates across the nation, and manage epidemics, regulatory bodies lack the reach to access critical information needed to learn real-time decision-making. In these scenarios, training privately from the get-go is the desirable outcome. This is where homomorphic encryption advances are used. We present an actualized scenario with hospitals sharing records to compute anomalies and audit fairness with incentive-compatible deployment and operations. Three main contributions: 1. fairness auditing at scale without the need to approximate nonlinearity, 2. enabling continuous sharing of data without key refresh, which undercuts the need for pairwise contracts out of privacy concerns, even if new models are developed and applied, and 3. an instance of anomaly detection in security management is applied to finding causes and correlations that aide medical research, particularly for rare diseases, epidemic management, and chronic illness research. We simulate such system using Microsoft's SEAL library and argue that our system of novel key-sharing scheme and anomaly detection algorithms is well-suited for applying homomorphic encryption at scale.

## Towards Fair Pricing and Secure Transaction of Training data.
Smart contracts for data transaction are non-trivial. There are three projects so far on trackling the challenge.

### FAIR Internship w/CrypTen
The goal is to evaluate the effect training data will have on a pre-trained model without retraining.

**Main idea** One single step of natural gradient descent may be more desirable than one (Euclidean) gradient descent step in evaluating the relative effect of various batches of data. If the ranking information between datasets correlates with the test loss resulted from add-one-on training, this information can be used to approximate the price of data without training on it. An application of that is private pricing before transaction. If this model is small enough, it can be done in private without much numerical imprecision. (to appear)

### Private ML Demo (NeurIPS Private and On-Device AI workshop)

A “magic mirror” made with two-way mirrors using purely on-device computations, allowing deployment into the most private spaces (e.g. as a bathroom mirror). It monitors skin conditions, and counts your morning jumping jacks.

- initial demo done with Devin C-R and Steven Tang at YCombinator Hackathon ⬇️

[Report (.pdf), ](https://drive.google.com/file/d/0B7Kbbgt_5BtfcWN0T2t1bERuaGx5enZjT1JNX284M0F2TkVV/view?usp=drivesdk) and  [demo videos](https://drive.google.com/drive/folders/1CmLBK_e-zGD13KRrp-pCRcHLne7xcaXN)

### Data Efficacy

(work before FAIR internship, poster presented at NeurIPS workshops 2018/2019)

Implementing smart contracts for the effect of training data is extremely expensive.

1. Studied the extracted models as a potential auxiliary function for enabling encrypted transactions, because they are not as secretive as the original models due to poor accuracy, yet may be used to evaluate data acquisition, enabling smart contracts.
2. Studied the effect of the gradients of compressed models used in private to gauge data value. (work done with Abhi V@MIT)

### Mechanism design for acquiring and deleting training data (w/ Qingyun Sun)

Ongoing



