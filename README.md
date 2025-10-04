# Research Materials - Categorical Structuralism for Philosophy of Science

## Purpose

This repository contains research-materials and drafts for proposed publications related to a research-programme where category- and topos-theoretical resources shall be used to reformulate a meta-theoretical structuralism akin to that developed by Sneed, Suppe and Munich Structuralism, using tools developed e.g. by O. Caramello, J.A. Goguen &amp; R. Burstall. The working title is **"Probing Reality - Categorical Structuralism for Philosophy of Science"**.


## Outlining Ideas

The following analogies / translations should be investigated:


* **Theory** (Sneed: set-theoretic predicate / family of models)
↦ Category / Theory-object / Classifying topos / Institution.
Options: present a theory as a category (syntactic category), as a geometric theory with a classifying topos, or as an institution (Goguen–Burstall) which abstracts syntax/semantics/satisfaction in a categorical way. 


* **Potential models / actual models** 
↦ Models = functors / geometric morphisms into a semantic topos (e.g. Set or another topos); potential models = all such functors satisfying signature constraints; actual models = those satisfying the theory's axioms (i.e. subcategory determined by axioms).
Classifying toposes make this neat: models in any topos correspond to geometric morphisms into the classifying topos. 


* **Intended models / applications**
↦ Selection of models via chosen semantic target (Set, sheaf topos for locality/space/time), or via additional structure (a functor into a category of empirical systems).
The choice of semantic codomain (which topos you map into) formalizes the epistemic/observational constraints.

* **Objects as “black boxes” and Yoneda** 
↦ Yoneda lemma: an object is determined by its incoming/outgoing morphisms (probes/experiments). This supplies a precise mathematical expression of “you know an object only by how it relates.” Use the Yoneda embedding to treat empirical probes as presheaves of observations.


* **Abstraction / forgetting** 
↦ Forgetful functors and adjoints: abstraction = left/right adjoint factorization (forgetful functor from rich structure to bare carriers); reconstruction/constraints via adjoints or monads. Fibrations / indexed categories encode varying contexts/perspectives. 


* **Inter-theory relations (reduction, equivalence, change of perspective)** 
↦ Morita-equivalence, equivalence of classifying toposes, functorial translations, and institution morphisms. Caramello’s “toposes as bridges” program is especially relevant for transferring information between different presentations of the same semantic content.


## Conceptual Toolkit
* **Yoneda embedding / presheaf categories** — formalize “probing by relations/experiments”.

* **Functors as models**: models = functors from a syntactic category into a semantic category (often Set), or models in an arbitrary topos = geometric morphisms into a classifying topos. 
ncatlab.org

* **Classifying topos** — encapsulates the universal model and gives a uniform way to talk about models in different semantic contexts; Morita-equivalence = equivalence of classifying toposes. Caramello’s methods exploit this. 

* **Institutions / indexed categories / fibrations** — capture families of theories, varying signatures, context-dependent semantics (good for formalizing “perspective matters”). 


* **Forgetful functors, adjoints, monads** — capture abstraction, quotienting, adding/forgetting observational resources; monads encode additional structure/constraints.

* **Natural transformations / 2-categorical structure** — represent theory translations, refinements, interpretation morphisms.

* **Sheaves / local toposes** — model locality, context dependence, partial observability (e.g. measurements that only give local data).

* **Morita or ‘presentation’ equivalence** — different syntactic presentations that give the same classifying topos correspond to the same “semantic content” (useful to formalize theory change where content is preserved).

## Potential Advantages

* Yoneda gives a precise expression of "objects are determined by all probes".

* The choice of codomain topos (or semantic category) encodes epistemic/observational limitations. E.g. mapping into Set vs. sheaves over spacetime yields radically different models you can realistically access.

* Fibrations/indexed categories formalize that "how you can probe depends on your own structure" (i.e. the measuring apparatus/context is itself a categorical object).

* Institutions and morphisms between institutions formalize inter-theory translations (Sneed’s intertheoretic relations have a categorical analogue).

## Reading List

Study and evaluate concretely the following resources:

### Basics
* Mac Lane: Category Theory for the Working Mathematician
* Johnstone: Sketches of an Elephant
* Riehl: Category Theory in Context
* Goldblatt: Topoi

### Contemporary Toolkit
* Goguen, J. A. & Burstall, R. — Institutions: Abstract model theory for specification and programming. J. ACM (1992) — introduces categorical metatheory of theories/models/satisfaction. 


* Olivia Caramello — Theories, Sites, Toposes: Relating and studying mathematical theories through topos-theoretic ‘bridges’ (OUP, 2017) — classifying toposes and transferring information between presentations. 


* David I. Spivak — Category Theory for the Sciences (MIT Press, 2014) — applied categorical modelling and many examples that make the ideas concrete.

* Steve Awodey — papers on categorical structuralism (e.g. "An answer to Hellman’s question" and related work). Good philosophical framing.

* Jonathan Bain (2013), Category-Theoretic Structure and Radical Ontic Structural Realism (Synthese) — a focused philosophy-of-science case study using category theory; plus the Lam & Wüthrich critique (2013/2015). 

* Fong & Spivak — Seven Sketches in Compositionality — modern, compositional modelling approaches.