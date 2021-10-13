---
title: "Object Oriented BNs for PROM"
date: 2018-11-28T15:15:26+10:00
featured: true
weight: 3
---

For PROMs, BN will be defined as BN, which consists of two discrete variable sets _X_ and _C_. _X_ represents the set of question items in the PROM, and _C_ the set of hidden factors that the PROM aims to measure.

PROM BNs do not have a fixed structure. The model can be learned from PROM data or expert knowledge according to available resources. For example, a knowledge-based PROM structure based on the assessment and evaluation BN structure in education is given in Figure 2. In this structure, the question items are the children of the latent factors. Based on expert knowledge, this structure can be modified. For example, if there are direct relationships between latent factors, they can be added to the model. Besides, score-based, constraint-based or hybrid BN learning algorithms can be used to learn the PROM structure entirely from the data.

<figure>
<img src="/images/oobn.png" alt="Trulli" style="width:100%">
<figcaption align = "center"><b>Figure 2. Example of Knowledge-Based BN Structure for PROM</b></figcaption>
</figure>

Generally, the contribution of a single PROM to decision making is limited. A physician considers multiple PROMs as well as other clinical variables and patient preferences when making a decision. PROM BNs also need to be modularly integrated into larger probabilistic models in order to provide useful decision support.

Object Oriented Bayesian Networks (OOBN) provide PROMs with a suitable structure to provide this modularity. An OOBN object consists of three discrete sets of variables: output variables O, input variables I, and encapsulated variables E (Koller and Pfeffer, 1997). Parent and child variables of encapsulated variables within the object can only be other variables within the object; encapsulated variables cannot have parents or children outside the object. Output variables can have child variables outside the object. Input variables are placeholders for variables that are themselves outside the object and have child variables inside the object. Input variables can have child variables from within the object, but cannot themselves be children of another variable within the object. Input and output variables form the interface of the BN object. Only input and output variables can have parents and children other than BN (for more detailed information on OOBN, see Koller and Pfeffer (1997)).

PROM BN output variables hidden factors O := C, encapsulated variables E := X with question items is an OOBN object. Latent factors and non-object parents of question items are also input variables. Input variables can be patient information such as age, gender, or causal factors. Input variables are important when connecting PROM BNs to larger and larger BNs.

Figure 3A shows two PROM BN objects made for different PROMs integrated into a larger model. OOBN allows us to abstract the properties of their internal structures while combining these BNs with the large model. OOBN enables BNs to be integrated into large models in a modular manner, without making any changes to their internal structure and without being too dependent on their internal structures. Figure 3B shows the internal structures of these objects.

<figure>
<img src="/images/ndba.png" alt="Trulli" style="width:100%">
<figcaption align = "center"><b>Figure 3. A - PROM BN Objects integrated into another BN model, B - Internal parts of PROM objects </b></figcaption>
</figure>

__*Bu yazının Türkçe versiyonunu okumak için [tıklayınız](/services/HSBO-icin-nesneye-dayali-BAlar/).*__

# References

Koller, D., Pfeffer, A. 1997. "Object-Oriented Bayesian Networks". Içinde Proceedings of the 13th Conference on Uncertainty in Artificial Intelligence (ss. 302–313). Providence, RI.
