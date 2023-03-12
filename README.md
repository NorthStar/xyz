I work on the joint topic of privacy (and security) and machine learning.

In 2023, I am developing my PhD thesis on data economy towards machine learning and AI governance, in the computer science department of NYU's Courant Institute of Mathematics.

I worked as an engineer at Google Chrome, Baidu Silicon Valley AI Lab, and UnifyID. I PhD-interned at Facebook AI Research, and TikTok Recommendations.

----
## Machine Learning for Systems
Over the past 5 years I have been involved in fostering an interdiscplinary research community on machine learning and systems at NeurIPS.
<details>
<summary>
NeurIPS Workshop on <b>Machine Learning for Systems</b> .
</summary>
<p> We are looking for papers on applying ML to computational systems, such as
- Supercomputing
- Hardware optimization
- ML-driven compiling
- Smart optimization across stacks
- Open source hardware
</p>

<p>We are especially interested in submissions that move beyond using machine learning to replace numerical heuristics. We hope to see novel system designs, streamlined cross-platform optimization, and new benchmarks for ML for Systems.
</p>

[**🔗CALL FOR PAPERS🔗**](http://mlforsystems.org/call_for_papers.html)
[**🔗ACCEPTED PAPERS🔗**](https://mlforsystems.org/accepted_papers.html)

</details></br>

----
## PhD Research

<p>My work on the Right To Be Forgotten for bi-linear recommendations is on arXiv.

**Netflix and Forget** Efficient and Exact Machine Unlearning from Bi-linear Recommendations (with ByteDance) [🔗🔗](https://arxiv.org/abs/2302.06676)
</p>

<p>
My work on data appraisal using secure multi-party computation is published at AISTATS 2022 (with Facebook AI Research).

**Data Appraisal Without Data Sharing** [🔗🔗](https://proceedings.mlr.press/v151/xu22e/xu22e.pdf)
</p>

----
## Past Projects
<details>
<summary>
I am broadly interested in the intersection of <b>machine learning</b> and <b>security</b> for socially-relevant applications.
</summary>

1. [🔗⬇️🔗](#network) Mean-field analysis for causality in social media amplification.
This abstracts social media recommenders to an influence on election outcomes.

2. [🔗⬇️🔗](#secure-data) Towards secure transaction and fair pricing of training data.
There are four parts to this work .

3. Learned containment: generated sandbox by repeated fuzzing and patching.
</details>

Besides these, I enjoy thinking about systems and design problems in technology.
I would also love to [hear your practical privacy challenges](#contact-me) that relate to managing data and models.

---
## <a name="network"></a> A Model for Network Influence
- as part of the coursework on Applied Causality (a seminar with Prof. David Blei, Columbia University).

**Abstract** In November 2016, when all the polls predicted a Clinton presidency, America got Trump. Assuming that the pollsters had sampled real sentiments from real voters, what could be the *cause* for the shift in election result? This is rather hard to untangle, since very few entities have the data on social networks' topology. There is also the challenge of assessing cyclic causes over time, akin to studying a network influence question: does the eating disorder community on the internet *cause* eating disorder? This work explores different high level aspects of network influence via a mean-field approach across average networks, controlling for variance of election outcomes away from the fundamentals. The goal of this exploration is to offer a simulation and theoretic model, a combination that clarifies qualitative phenomena and evaluates potential policy interventions with impact. [🔗Project intro page.🔗](causal-influence-platform-propagation)

----
## <a name="secure-data"></a> Towards Fair Pricing and Secure Transaction of Training data.
This project has the broad goal of streamlinining the incentives problems with data markets. There are three endeavers so far on trackling the challenge:

### Data Appraisal without Data Sharing

- as part of an internship at Facebook AI Research.

The goal is to evaluate the effect training data will have on a pre-trained model without retraining, implemented as a secure multi-party computation in [CrypTen](https://crypten.ai).

**Main insight** One single step of natural gradient descent may be more desirable than one (Euclidean) gradient descent step, when used to evaluate the relative effect of various batches of data. If the ranking information between datasets correlates with the test loss resulted from add-one-on training, this information can be used to approximate the price of data without training on it. An application of that is private pricing before transaction. If this model is small enough, it can be done in private without much numerical imprecision. (to appear)


### Data Efficacy

- work before FAIR internship, poster presented at NeurIPS workshops 2017/2018.

Implementing smart contracts for the effect of training data is extremely expensive.

1. Studied the extracted models as a potential auxiliary function for enabling encrypted transactions, because they are not as secretive as the original models due to poor accuracy, yet may be used to evaluate data acquisition, enabling smart contracts.
2. Studied the effect of the gradients of compressed models used in private to gauge data value.

### Mechanism design for acquiring and deleting training data (w/ Qingyun Sun)

Data markets are crucial part of the future of our economy. Traditional market practices tend to be inefficient when applied to data as a commodity. Because 1. data can be replicated at low cost, and 2. information contained in data can be privacy-relevant.

On the other hand, the rise of AI application whose utility depend on data quantity and quality means that privately-held quality data becomes apparently valuable. This gives rise to a data market where acquisitions and ownership disputes will be frequent.

We envison new mechanisms that allows model owners to acquire data of appropriate utility, while allowing data owner to manage, edit, and delete their data.

This work is ongoing.

---

## Survey on Mean Field Methods In Deep Learning
- w/ Mudit Pandey as part of math in deep learning coursework (Prof. Joan Bruna, New York University).

I wrote a [🔗survey paper🔗](/meanfield.pdf) that helps me understand 1) Mean Field Methods as applied to the theory of deep learning, and 2) a physicist-style modeling, which I applied to qualitative political science.

----
## A Worry-free Encryption Plan for Healthcare Data

[🔗HEalth: Privately Computing on Shared Healthcare Data🔗](https://link.springer.com/chapter/10.1007/978-3-030-77287-1_12)
- w/ Leo de Castro, Rami el Khatib, and Erin Hales at [🔗Microsoft Research Private AI Bootcamp🔗](https://www.microsoft.com/en-us/research/event/private-ai-bootcamp/), part of a book chapter on [Protecting Privacy through Homomorphic Encryption](https://link.springer.com/book/10.1007/978-3-030-77287-1)


**Abstract** Healthcare in the US is notoriously expensive and unsustainable. Many machine learning startups aim to simplify the process by bringing in automated expertise to hospitals on radiology, brain imaging, or cancer detection. On the other hand, it is well-known that hospitals cannot easily share data. Existing machine learning solutions tend to focus on training with data obtained through long-term collaboration because the private computation requires that the clients have done appropriate pre-processing. Effectively, they work *around* the data-sharing challenge in training rather than tackling it. As a result, their inference model is typically static, and does not adapt to changes continuously.
<details><summary>...</summary>

On the other hand, regulatory agencies need to uphold the ethics standards for healthcare professionals, but can only access hospital records in a delayed fashion. Despite their mandate to audit individual doctors, assess response rates across the nation, and manage epidemics, regulatory bodies lack the reach to access critical information needed to learn real-time decision-making. In these scenarios, training privately from the get-go is the desirable outcome. This is where homomorphic encryption advances are used. We present an actualized scenario with hospitals sharing records to compute anomalies and audit fairness with incentive-compatible deployment and operations. Three main contributions: 1. fairness auditing at scale without the need to approximate nonlinearity, 2. enabling continuous sharing of data without key refresh, which undercuts the need for pairwise contracts out of privacy concerns, even if new models are developed and applied, and 3. an instance of anomaly detection in security management is applied to finding causes and correlations that aide medical research, particularly for rare diseases, epidemic management, and chronic illness research. We simulate such system using Microsoft's SEAL library and argue that our system of novel key-sharing scheme and anomaly detection algorithms is well-suited for applying homomorphic encryption at scale.
</br>
</details></br>

---
## Private ML Demo

A “magic mirror” made with two-way mirrors using purely on-device computations, allowing deployment into the most private spaces (e.g. as a bathroom mirror). It monitors skin conditions, and counts your morning jumping jacks.

- initial demo done with Devin C-R and Steven Tang at YCombinator Hackathon ⬇️

NeurIPS Private and On-Device AI workshop 2018 [report](https://drive.google.com/file/d/0B7Kbbgt_5BtfcWN0T2t1bERuaGx5enZjT1JNX284M0F2TkVV/view?usp=drivesdk) and  [demo videos](https://drive.google.com/drive/folders/1CmLBK_e-zGD13KRrp-pCRcHLne7xcaXN).

----
##  <a name="contact-me"></a> About Me

I work on the intersection of machine learning and security.

So far, this includes 1. applying machine learning to practical security and privacy problems, which I witnessed in industry and 2. security management insights to similar challenges in deploying machine learning models, but I am open to other approaches.



<details>
    <summary> Contact info.</summary>

For inquiries, suggestions, and threats, please email to mimee _AT_ nyu.edu.

</details>

<details>
  <summary>"Where are you really from?" and other questions.</summary>

<p>I studied math and computer science at Harvey Mudd College in Claremont, CA. </p>

<p>I worked on a variety of challenges on machine learning and security in Silicon Valley.

* managed stability with data for Google's Chrome Browser
* deployed and monitored Baidu's speech recognition research, and
* R&D for UnifyID's password-replacing products.

</p>

<p>
I moved to New York in 2019.
</p>

<p>
I was born and raised in Beijing, China, where I was introduced to the wonderful worlds of mathematics and the Chinese language. I moved to Vancouver, Canada to have an art education for a good portion of high school. Sometime around then, I changed my mind.
</p>

</details>