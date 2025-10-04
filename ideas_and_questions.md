

## 1 — Modeling instrument / context dependence by a fibration

### 1.1 Basic idea (intuitively)

* Base category $C$: objects are **contexts*
So: **signature morphisms or syntactic functors $u$** often induce geometric morphisms **between presheaf topoi**, via precomposition and Kan extensions. When your theories are geometric and the syntactic functor is geometric (preserves the relevant structure), these induced morphisms align with Caramello's geometric morphisms between classifying toposes.

### 3.4 Affordances and limits for natural-science theories
struments, observational languages, POVs). Morphisms $f:c\to d$ are **refinements**, calibrations, or translations from context $c$ into a finer (or at least different) context $d$.
* Total category $E$: objects are **(context, model-like) pairs** — think of them as models *together with the context in which they are described or observed*. The projection $p:E\to C$ forgets the model and keeps the context.

The fibration $p:E\to C$ organizes models by the context in which they are available/readable; moving along morphisms in $C$ induces **reindexing** (restriction/coarsening or expansion) between the corresponding categories of models.

### 1.2 Formal definition (fibration)

A functor $p:E\to C$ is a **fibration** if for every arrow $f:c'\to c$ in $C$ and every object $X\in E$ with $p(X)=c$, there exists a **cartesian lift** $\bar f: f^{*}X \to X$ in $E$ with $p(\bar f)=f$, satisfying the universal property:

for any $g:d\to c'$ and any $h:Y\to X$ in $E$ with $p(h)=f\circ g$, there exists a unique $k:Y\to f^{*}X$ in $E$ with $p(k)=g$ and $\bar f\circ k = h$.

* The object $f^{*}X$ sits in the **fiber** $E_{c'} = p^{-1}(c')$.
* The arrow $\bar f: f^{*}X \to X$ is **cartesian** and encodes the minimal way to view $X$ from $c'$ (pullback/restriction along $f$).

A choice of cartesian lifts for every $f$ and $X$ is a **cleavage**; if the choice is functorial (composition-respecting) we have a **split fibration**, which is convenient for formal calculations.

### 1.3 Fibers and reindexing functors

For each $c\in C$ the **fiber** $E_c$ is the category of objects of $E$ lying over $c$ and arrows over $\mathrm{id}_c$. Intuitively:

* $E_c$ = models *as seen/represented in context $c$* (their syntax/observable vocabulary is the one provided by $c$).

Given $f:c'\to c$, choice of cartesian lifts produces a **reindexing functor**

$$f^{*} : E_c \longrightarrow E_{c'}.$$

This is the functor that takes a model described in context $c$ and returns its *reduct* as seen from the perspective $c'$; equivalently, it tells you how a model in a finer context appears in a coarser one (or vice-versa depending on how you order "refinement").

Important categorical properties:

* If $p$ is a **Grothendieck fibration**, the assignment $c\mapsto E_c$ plus $f\mapsto f^{*}$ yields a pseudofunctor $C^{\mathrm{op}}\to \mathbf{Cat}$. The total category $E$ is equivalent to the **Grothendieck construction** applied to this pseudofunctor.

### 1.4 What is the full total category $E$?

Concretely, one way to construct $E$ is:

* Pick a family of semantic target categories (topoi) $\\{\mathcal{F}_c\\}_{c\in C}$. Each $\mathcal{F}_c$ captures the mathematical environment appropriate to context $c$ (e.g. Set for standard lab instruments, a sheaf topos for spatially-distributed instruments, or enriched categories for noisy/probabilistic instruments).
* For a fixed formal theory $T$ (or a family of theories), define $E_c = \mathrm{Mod}_T(\mathcal{F}_c)$ (the category of models of $T$ in the topos $\mathcal{F}_c$).
* Let $E$ be the category whose objects are pairs $(c, M)$ with $c\in C$ and $M\in E_c$; a morphism $(c',M')\to (c,M)$ is a pair $(f:c'\to c,\ \alpha: M' \to f^{*} M)$ where $\alpha$ is a morphism in $E_{c'}$. Composition uses reindexing.

This is exactly the **Grothendieck construction** of the pseudofunctor $c\mapsto E_c$ and gives a canonical fibration $p:E\to C$.

### 1.5 Operational meaning of cartesian morphisms and reindexing

* Suppose $c$ is the language/instrument of classical thermometry (reading mean kinetic energy) and $c'$ is the language/instrument of calorimetry (measures heat quantity caloric-style). A map $f:c' \to c$ could be thought of as a translation from caloric observables to kinetic observables (or a calibration procedure).

* A cartesian lift $\bar f : f^{*}M \to M$ expresses: given a model $M$ described via kinetic observables, what is the *best possible description* of this same system in caloric terms? $f^{*}M$ is the **reduct** of $M$ to the caloric language (it might forget some structural distinctions of the kinetic theory or reinterpret them as calibrations/parameters).

* The universal property of cartesian morphisms formalizes minimality: any other way of interpreting $M$ in caloric terms factors uniquely through $f^{*}M$.

---

## 2 — Caloric ↔ Kinetic example inside the fibration picture

This is the canonical domain example you asked about: **caloric theory of heat** vs. **kinetic theory**.

### 2.1 Rough outline of ingredients

* Let $T_{\mathrm{cal}}$ be the caloric-theory presentation (signature $\Sigma_{\mathrm{cal}}$ with sorts and observables appropriate to caloric law: "quantity of caloric" $Q$, caloric flow etc.).
* Let $T_{\mathrm{kin}}$ be the kinetic-theory presentation (signature $\Sigma_{\mathrm{kin}}$ with variables for particle velocities, kinetic energy, temperature as mean molecular kinetic energy).
* There is a **translation** (institution morphism / signature mapping) between $\Sigma_{\mathrm{cal}}$ and $\Sigma_{\mathrm{kin}}$ *on the restricted domain* where caloric theory made accurate predictions: it maps caloric measurable quantities to averaged kinetic quantities in an approximate/effective way. Call this $\sigma:\Sigma_{\mathrm{cal}}\to\Sigma_{\mathrm{kin}}$. This translation is not global (it fails outside the relevant regime) and may be approximate.

### 2.2 Contexts / instruments $C$

Define contexts reflecting observational regimes:

* $c_{\text{lab}}$: simple lab calorimeter (measures heat as caloric transfer), coarse.
* $c_{\text{thermo}}$: classical thermometer measuring temperature (interpreted kinetically as mean kinetic energy), coarser/finer depending on calibration.
* $c_{\text{molecular}}$: microscopy/velocity-resolving instruments (fine, kinetic-specific).

Morphisms in $C$ encode calibrations/translation relationships. For example, we might have $f: c_{\text{lab}} \to c_{\text{thermo}}$ capturing the operational procedure that maps calorimeter readings to thermometer temperatures (via a calibration law).

### 2.3 Fibers $E_c$

* $E_{c_{\text{lab}}}$: models presented in caloric vocabulary (e.g. $M_{cal}$ with a caloric content function $Q: \text{body}\to\mathbb{R}$).
* $E_{c_{\text{thermo}}}$: models presented in thermometric vocabulary (temperature functions).
* $E_{c_{\text{molecular}}}$: kinetic models (velocity distributions, kinetic energies).

### 2.4 Translation / reducts and empirical equivalence

* The signature morphism $\sigma$ induces a model-reduct functor $r^{*} : \mathrm{Mod}_{T_{\mathrm{kin}}} \to \mathrm{Mod}_{T_{\mathrm{cal}}}$ (coarsening kinetic models to caloric descriptions) — or more generally, given an instrument morphism $f:c_{\mathrm{cal}}\to c_{\mathrm{kin}}$, a reindexing functor $f^{*} : E_{c_{\mathrm{kin}}}\to E_{c_{\mathrm{cal}}}$.

* **Empirical equivalence** in the restricted domain occurs when for a class of kinetic models $M_{\mathrm{kin}}$ and corresponding caloric models $M_{\mathrm{cal}}$ we have:
  $$
  r^{*}(M_{\mathrm{kin}}) \cong M_{\mathrm{cal}},
  $$
  i.e. the kinetic model, when viewed through the caloric language/instrument, yields the same observational data as the caloric model. Multiple kinetically distinct models may reduce to the same caloric model (underdetermination).

* The fibration makes precise: the *fiber* over the caloric context $c_{\mathrm{cal}}$ contains all caloric descriptions; the **preimage** $p^{-1}(c_{\mathrm{cal}})$ captures all kinetic models that, when reindexed along the instrument morphism, land on the same caloric representation. Thus underdetermination is literally the nontrivial fibre of $p$.

### 2.5 Ontology difference & instrument-dependence

* In the caloric fiber, the ontology is caloric substance; in the kinetic fiber, the ontology is molecules and velocities. They are different objects in different fibers; the instrument morphisms and reducts mediate between them. The meta-theory keeps both ontologies in the total category $E$ and relates them functorially.

* Crucially: *empirical equivalence is a relation in $E$ mediated by $p$*; it is not absolute but **context-relative**: two theories/models are equivalent relative to a particular instrument $c$ if they map to the same object in $E_c$ (i.e. are indistinguishable by the probes that context affords).

---

## 3 — Non-geometric theories, presheaf topoi, and geometric morphisms

You asked for (a) formal detail on presheaf topoi for non-geometric theories; (b) what it means that signature morphisms often induce geometric morphisms $\mathcal{E}_S\to \mathcal{E}_T$; and (c) affordances and limits for natural-science theories.

### 3.1 Geometric vs non-geometric theories — reminder

* **Geometric logic**: allows finite conjunctions, arbitrary disjunctions, and existential quantification; geometric theories have classifying toposes with the universal property linking models in any topos to geometric morphisms into the classifying topos. Caramello’s machinery lives here.

* Many natural-science theories (e.g. first-order theories with universal quantification and implication, or theories using numeric analysis/differential equations) are **not** strictly geometric. For such theories we cannot always guarantee an honest classifying topos with the same universal property.

### 3.2 Presheaf topoi as a general fallback

Given an arbitrary syntactic category $\mathcal{C}$ (e.g. the category of formulae up to provable equivalence, or a small presentation of signature+terms), one can always form the presheaf topos
$$
[\mathcal{C}^{\mathrm{op}},\mathbf{Set}].
$$
Properties:

* It is a Grothendieck topos (elementary topos) even if the original theory is not geometric.
* Objects are set-valued presheaves on the syntactic category; these can be read as generalised “parameterized families of partial models / probes”.
* It lacks, in general, the **classifying universal property** enjoyed by classifying toposes of geometric theories; but it *does* serve as a semantic universe where you can interpret syntactic objects and reason internally using Goldblatt’s internal logic.

So presheaf topoi are a **useful semantic surrogate**: they provide a topos-level environment even for non-geometric theories. They permit use of Yoneda, sheafification, and geometric morphism machinery.

### 3.3 How signature/syntactic functors induce geometric morphisms between presheaf toposes

Let $u:\mathcal{C}\to \mathcal{D}$ be a functor between small categories (e.g. a mapping of syntactic categories induced by a signature morphism or theory interpretation). Then there is a standard string of adjoints between presheaf categories:

* **Precomposition (inverse image):**
  $$
  u^{*} : [\mathcal{D}^{\mathrm{op}},\mathbf{Set}] \longrightarrow [\mathcal{C}^{\mathrm{op}},\mathbf{Set}],\qquad u^{*}(F)=F\circ u.
  $$

* $u^{*}$ has both a **left adjoint** (left Kan extension) $\operatorname{Lan}_u$ and a **right adjoint** (right Kan extension) $\operatorname{Ran}_u$, so we have
  $$
  \operatorname{Lan}_u \dashv u^{*} \dashv \operatorname{Ran}_u .
  $$
  Hence $(\operatorname{Lan}_u, u^{*})$ is a **geometric morphism** between presheaf toposes (where $\operatorname{Lan}_u$ is left exact under mild conditions) or at least forms an adjoint pair suitable for topos morphism considerations. More precisely:

* In topos theory, a **geometric morphism** $f:\mathcal{F}\to\mathcal{E}$ is a pair $f^{*}:\mathcal{E}\to\mathcal{F}$ (left exact, left adjoint to $f_*$). If $u$ preserves finite limits (or if one restricts to appropriate subcategories), $\operatorname{Lan}_u$ will be left exact and $(\operatorname{Lan}_u, u^{*})$ gives a geometric morphism.

So: **signature morphisms or syntactic functors (u)** often induce geometric morphisms **between presheaf topoi**, via precomposition and Kan extensions. When your theories are geometric and the syntactic functor is geometric (preserves the relevant structure), these induced morphisms align with Caramello’s geometric morphisms between classifying toposes.

### 3.4 Affordances and limits for natural-science theories

Affordances:

* Presheaf topoi give an explicit categorical universe even when the theory is not geometric — enabling Yoneda, sheafification, internal logic, and definition of models as geometric morphisms when possible.
* Functor-induced geometric morphisms give a mechanistic way to compare presentations, push forward/pull back models, and study how syntactic translations reflect semantically.

Limits / cautions:

* **Loss of the universal classifying property.** For non-geometric theories the presheaf topos is not necessarily the classifying topos; you lose the tight model↔geometric-morphism correspondence. Interpretations at the topos level must be treated carefully.
* **Analytic/numeric apparatus.** Many natural-science theories involve analysis, PDEs, continuity, measure theory — requiring enriched semantics (toposes of sheaves over analytic sites, or constructive/realizability toposes). Naïve presheaf on a syntactic category may not capture these features without additional structure.
* **Empirical content caveat (Weatherall).** Even when two theories have equivalent presheaf topoi, empirical distinctions may depend on extra structure (how the theory is *applied* to the world, i.e., interpretation functor $I:Emp\to \mathrm{Mod}$). So presheaf/topos equivalence is a necessary *formal* condition but not automatically sufficient for empirical equivalence.

---

## 4 — Adjoints $F \dashv U \dashv G$: canonical lifts, coarsenings, and underdetermination

Let $U : \mathrm{Mod}_{\text{fine}} \to \mathrm{Mod}_{\text{coarse}}$ be the forgetful/reduct functor that maps a fine (rich-structure) model to its coarse (observational) content.

### 4.1 Three cases and their meanings

1. **Left adjoint $F \dashv U$**

  * If $F$ exists, then for each coarse model $N$ there is a **canonical free fine model** $F(N)$ and a universal arrow $\eta_N: N \to U(F(N))$.
  * $F$ constructs the minimally structured fine model that extends the coarse data, i.e. **adds structure freely** consistent with the coarse observations.
  * Philosophically: $F(N)$ is a *canonical reconstruction* of a fine theory from coarse evidence — a best-effort “lifting” with no extra constraints beyond those necessary. If $F$ exists and is unique, the coarse data determine a unique canonical fine candidate.

2. **Right adjoint $U \dashv G$**

  * If $G$ exists, then for each coarse model $N$ there is a **cofree fine model** $G(N)$ and a counit $\epsilon_N: U(G(N)) \to N$.
  * $G(N)$ is a maximally structured fine model compatible with the coarse data (it contains all possible compatible fine distinctions in a canonical way).
  * Philosophically: $G$ gives a canonical maximal refinement consistent with evidence—perhaps modeling a closure under potential elaborations.

3. **No adjoints / multiple adjoints / nonunique lifts**

  * If neither adjoint exists, the coarse model $N$ may have **zero**, **multiple**, or **a proper class** of inequivalent fine models $M$ with $U(M) \cong N$. This is the **structure of underdetermination**: the coarse evidence does not lift uniquely to a fine description.

### 4.2 How this relates to philosophical underdetermination (evidence ↔ theory)

* In standard philosophy of science: evidence $E$ underdetermines theory $T$ when multiple incompatible theories are empirically equivalent with respect to $E$. In categorical terms:

  * Take **evidence** to be the coarse observational object $N \in \mathrm{Mod}_{\mathrm{coarse}}$ (a model of coarse data).
  * **Theories** are (isomorphism classes of) fine models $M$ with $U(M) \cong N$. The **preimage** $U^{-1}(N)$ is the class of theories consistent with evidence $N$.
  * Underdetermination is precisely the statement that $U^{-1}(N)$ contains multiple non-isomorphic models.

Thus, underdetermination is captured **structurally** as the fiber $U^{-1}(N)$ over the evidence $N$. Existence of adjoints corresponds to canonical ways of resolving underdetermination:

* $F$ gives a canonical *preferred* lifting (a particular theory chosen by a principle of parsimony or free completion).
* $G$ gives another canonical *maximal* lift (a conservative completion or maximal elaboration).
* When neither exists, the meta-theory must either accept **genuine underdetermination** (multiple inequivalent lifts) or impose extra constraints (e.g., pragmatic, experimental, pragmatic ceteris paribus) to choose among lifts.

**Note on degrees of underdetermination:** this framework also lets you quantify/structure underdetermination:

* The **size**/structure of the fiber $U^{-1}(N)$ (a discrete set, a poset with refinement relations, a category with morphisms between fine models) encodes richness of underdetermination. For example, sometimes there is a partial order of refinements among fine models; sometimes entirely unrelated models share the same reduct.

### 4.3 Underdetermination vs. epistemic uncertainty

* **Epistemic underdetermination** typically concerns *which theory we ought rationally to accept given evidence*. Our categorical picture is neutral: it tells you *how many* and *which* fine models fit the evidence and what canonical constructions exist, but it does not by itself decide which lift is epistemically preferred. That requires additional selection principles (simplicity, explanatory scope, entrenchment) which can be modeled as extra structure (a preference functor, weighted monad, or ordering) in the meta-theory.

* **Approximate / probabilistic underdetermination**: if evidence is noisy, replace Set-models by metric/probabilistic models; fibers become metric/enriched categories and you can talk about near-equality, most-likely lifts, Bayesian priors etc. That brings statistical/model-selection tools into the categorical scaffold.

---

## 5 — Efficient, targeted study plan (what to read & exercises next)

You asked to focus on presheaves, fibrations, Yoneda, adjoints, and their relation to local/global perspectives — with minimal time overhead, given your background.

### 5.1 Priority topics & why

1. **Fibrations & Grothendieck construction** — because instrument/context dependence is exactly a fibration story.
2. **Yoneda & presheaves** — probes/observations are presheaves; important for the “objects-as-black-boxes” thesis.
3. **Adjoints (left/right) and Kan extensions** — because canonical lifts/coarsenings and induced geometric morphisms use these.
4. **Presheaf toposes & geometric morphisms induced by functors** — to handle non-geometric theories.
5. **Applied examples & institutions** — connect theory to syntax/translation machinery.

### 5.2 Recommended short reading list (minimal & efficient)

(Assume you’ll do ~5–7 hours/week; this is a 2–3 month focused core followed by applied reading.)

**Week 1–2 (Fibrations & reindexing)**

* **Riehl — *Category Theory in Context***: Ch.6 (Fibrations).
  *Exercises:* construct the Grothendieck construction for a simple pseudofunctor $C^{\mathrm{op}} \to \mathbf{Cat}$ (e.g., $c \mapsto \mathbf{Set}^{I_c}$ for small index sets). Explicitly compute cartesian lifts.
* **Borceux (vol. 2)**: skimming on fibrations if you want extra examples (optional).

**Week 3 (Yoneda & presheaves)**

* **Riehl**: Ch.7 (Yoneda). *Exercises:* compute representables and show Yoneda embedding for small categories.
* **Mac Lane**: Section on presheaf categories and Yoneda (refresh basics).

**Week 4 (Presheaf toposes & geometric morphisms)**

* **Goldblatt — *Topoi***: ch.4–5 (presheaves, sheaves, subobject classifier). *Exercises:* build presheaf topos $[\mathcal{C}^{op}, \mathbf{Set}]$ for a small syntactic $\mathcal{C}$. Compute precomposition functor for a simple functor $u: \mathcal{C} \to \mathcal{D}$ and the two Kan extensions ($\operatorname{Lan}$, $\operatorname{Ran}$) in a concrete example. Show the adjoint triple.

**Week 5 (Adjoints & Kan extensions)**

* **Mac Lane**: Ch. IV (Adjoints). *Exercises:* check existence of left/right adjoints in simple forgetful contexts and compute Lan/Ran formulas in small examples.
* **Riehl**: the sections on Kan extensions if needed.

**Week 6 (Putting it together; toy caloric/kinetic example)**

* Implement the caloric/kinetic toy as:

  * signatures $\Sigma_{\mathrm{cal}}, \Sigma_{\mathrm{kin}}$ (finite sketches),
  * coarse-to-fine signature morphism $\sigma$,
  * construct fibers $E_{c}$ as $\mathrm{Mod}_T(\mathbf{Set})$ for simple $T$,
  * compute reduct functor and check fiber preimages.
* *Tooling:* do this as small Python scripts or small Haskell programs (your software background helps).

**Weeks 7–8 (Institutions and Caramello overview)**

* **Goguen & Burstall**: read the accessible introduction to institutions; implement simple institution morphism for your toy.
* **Caramello**: read introductory chapters (theory→site→topos idea). Understand at a high level when she uses geometric logic and when presheaf surrogates are needed.

**Optional/Advanced**

* **Johnstone**: selected sections on classifying toposes (if you plan to go deep).
* **Weatherall/Halvorson/Barrett**: read their analyses of equivalence and translatability to understand pitfalls and refine choice of invariants.

### 5.3 Concrete exercises to make the ideas stick

1. **Small pseudofunctor → Grothendieck construction**: pick $C$ with 2 objects and one nontrivial arrow. Assign small categories to each object. Build total category and check cartesian lifts.
2. **Toy caloric/kine**: give explicit finite tables for models $M_{\mathrm{kin}}$, compute $r^*(M_{\mathrm{kin}})$, find two different $M_{\mathrm{kin}} \neq M'_{\mathrm{kin}}$ mapping to same caloric model.
3. **Presheaf push/pull**: pick $u: \mathcal{C} \to \mathcal{D}$ very small, compute $u^*$, $\operatorname{Lan}_u$ and $\operatorname{Ran}_u$ on simple representable presheaves. Verify adjunction equations.
4. **Adjoint existence example**: present a forgetful functor $U$ (e.g., groups→sets with extra data) and check whether left/right adjoints exist; interpret this in the lifting-coarsening sense.

---

## 6 — Closing remarks and recommended immediate next steps

1. **Immediate implementable task (2–5 hours):** construct a tiny fibration in code/pen-and-paper: base $C = \{c_{\mathrm{cal}}, c_{\mathrm{kin}}\}$ with one arrow $f: c_{\mathrm{cal}} \to c_{\mathrm{kin}}$. Let $E_{c_{\mathrm{kin}}}$ be (a) a category with two distinct kinetic models and $E_{c_{\mathrm{cal}}}$ a category with one caloric model. Build $E$ as the Grothendieck construction and compute cartesian lift of the caloric model(s). This will immediately show the fiber structure and underdetermination.

2. **Read Riehl Ch.6 and Riehl Ch.7** (two short chapters) next — you’ll get most of what you need for fibrations and Yoneda. Then do Goldblatt Ch.4–5 for the presheaf topos machinery.

3. **Document every construction** in your repo README/notebook — these are both exercises and the beginnings of publishable worked examples.

---
