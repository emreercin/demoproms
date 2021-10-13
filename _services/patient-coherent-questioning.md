---
title: "Patient Coherent Questioning"
date: 2021-10-12T15:15:34+10:00
featured: true
weight: 4
usemathjax: true
---

One of the important constraints against the widespread use of PROMs is the need to answer too many questions and the uselessness of PROMs with incomplete inputs.

Bayesian Networks and their probabilistic inference algorithms provide a suitable environment for solving these two problems. No matter how many questions are answered when the Bayesian Network is built for PROMs, the posterior distributions of the measured latent factors can be calculated using probabilistic inference algorithms such as a join tree. The posterior distributions can be updated as more questions are answered. PROMs usually has multiple questions related to the same latent factor. If the uncertainty regarding a latent factor is low, that is, if the BA is certain of the latent factor estimation, asking more questions about that latent factor may not change the results. In this case, asking about another factor with more uncertainty will give more information for estimates.

Using an adapted questionnaire, it aims to ask the question with the highest average information gain compared to the previous answers of the patient (Madigan & Almond, 1996; Plajner & Vomlel, 2016).In Bayesian Networks, this process can be thought of as performing a sensitivity analysis after each question and choosing the question with the highest sensitivity as the next question. In a PROM Bayesian Network, let __*C*__ be the latent factor it is intended to measure, __*x<sub>1</sub>,...,x<sub>a</sub>*__ be answers to previously answered questions __*X<sub>1</sub>,...,X<sub>a</sub>*__, and __*X<sub>a+1</sub>,...,X<sub>m</sub>*__ be questions yet to be answered. Finally, let __*I(C;X<sub>i</sub>&#124;x<sub>i</sub>,...,x<sub>a</sub>)*__ be the extra information provided by the answer to question __*X<sub>i</sub>*__ while the answers __*x<sub>1</sub>,..., x<sub>a</sub>*__ are known. In PROMs Bayesian Networks, the question that provides the most information about the latent factor will be chosen over the previous answers.

$$\underset{X{i} \in X}{\operatorname{argmax}}I(C;X{i}|x{1}...x{a})$$

To calculate this, a measure of information is needed. Entropy and the amount of shared information are appropriate measures for this job. Entropy measures the amount of uncertainty in a variable. The entropy of a discrete variable __*C*__ is calculated as follows.

$$H(C)=-\sum_{c}P(C)\log(P(C))$$

The shared amount of information for variables __*C*__ and __*X*__ represents the average information they provide about __*C*__ when __*X*__ is observed. This is the difference between the entropy of __*C*__ and the conditional entropy of __*C*__ to __*X*__.

$$MI(C;X) = H(C) - H(C|X) = -\sum_{C}P(C)\log(P(C)) + \sum_{C, X}P(C, X)\log(P(C|X))$$

If it is desired to calculate an information criterion about a group of multiple variables, the combined entropy of these variables can be used as follows.

$$MI(C{1},...,C{k};X) = -\sum_{C}P(C{1},...,C{k})\log(P(C{1},...,C{k})) + \sum_{C{1},C{2},...,C{k}, X}P(C{1},...,C{k}, X)\log(P(C{1},...,C{k}|X))$$

If the latent variable C is a binary variable, the expected strength of evidence may also be an appropriate measure of information (Madigan & Almond, 1996). The strength of evidence __*W(L;X)*__ between a latent factor C and a question item X is the logarithm of the Bayes factor.

$$ W(C;X) = \log(\frac{P(X|C)}{P(X|\bar{C})})$$

The expected strength of evidence __*EW(C;X)*__ is equal to C with the conditional mean strength of evidence. ü

$$ EW(C;X) = \sum_{X}W(C;X)P(X|C) $$

In PROM Bayesian Networks, patient coherent questioning can be implemented by using one of the measures of common information amount or expected strength of evidence, measuring the information provided by each unanswered question according to the questions that the patient has answered before, and choosing the question with the maximum information. For such an algorithm, the maximum number of questions, the common information amount threshold or the entropy threshold can be selected as the stopping condition.

__*Bu yazının Türkçe versiyonunu okumak için [tıklayınız](/services/hasta-uyumlu-soru-secme/).*__

# References

- Madigan, D., Almond, R. G. 1996. "On Test Selection Strategies for Belief Networks". Lecture Notes in Statistics, 112, 89–98.
