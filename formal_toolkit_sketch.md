# Formal Specification: Philosophy of Science Concepts via Category Theory

We map philosophical notions into established categorical structures.

---

## 1. Instruments and POV-Dependence → Fibrations

Let $C$ be a category of instruments or perspectives.  
- Objects: experimental contexts $c$.  
- Morphisms: refinement or translation between instruments.

Define a fibration $p: E \to C$:  
- Fiber $E_c = p^{-1}(c)$: category of models as seen under instrument $c$.  
- Reindexing: for $f: c \to d$, a functor $f^*: E_d \to E_c$.  

**Interpretation**: changing instrument induces reducts/expansions of models.  
This encodes instrument-dependence of epistemic access.

---

## 2. Translability and Equivalence → Institutions

An institution $\mathcal{I} = (\text{Sign}, \text{Sen}, \text{Mod}, \models)$:  
- Sign: category of signatures.  
- Sen: signatures $\to$ sets of sentences.  
- Mod: signatures $\to$ categories of models.  
- Satisfaction: $\models \subseteq |Mod(\Sigma)| \times Sen(\Sigma)$.

For a signature $\Sigma$, we write $\mathbf{Mod}(\Sigma)$ for the category of models of that signature. Objects are models (structures satisfying the signature), and morphisms are homomorphisms between models.

A **morphism of institutions** $(\Phi, \alpha, \beta)$:  
- $\Phi: \text{Sign}_1 \to \text{Sign}_2$.  
- Sentence translation: $\alpha_\Sigma: Sen_1(\Sigma) \to Sen_2(\Phi\Sigma)$.  
- Model reduct: $\beta_\Sigma: Mod_2(\Phi\Sigma) \to Mod_1(\Sigma)$.  
- **Satisfaction condition**:  
  
$$M_2 \models_2 \alpha_\Sigma(\varphi) \iff \beta_\Sigma(M_2) \models_1 \varphi.$$

This encodes faithful theory translation.

---

## 3. Inter-Theory Reduction → Classifying Toposes

For a (geometric) theory $T$, the **classifying topos** $\mathcal{E}_T$ satisfies:  
- For any Grothendieck topos $\mathcal{F}$, models of $T$ in $\mathcal{F}$ correspond to geometric morphisms $\mathcal{F} \to \mathcal{E}_T$.

Reduction of $S$ to $T$:  
- A geometric morphism $\mathcal{E}_S \to \mathcal{E}_T$.  
- Conservative reduction: essential surjectivity or logical conservativity of the morphism.

---

## 4. Actual vs Potential Models

- **Potential models**: all objects of $\mathbf{Mod}(\Sigma)$.  
- **Actual models**: subcategory defined by axioms, often realized as a subobject classifier in $\mathcal{E}_T$.  
- **Intended models**: designated subcategory singled out by empirical interpretation functor $I: \mathbf{EmpiricalSystems} \to \mathbf{Mod}(\Sigma)$.

---

## 5. Morita Equivalence → Topos Equivalence

- Theories $T_1, T_2$ are **Morita-equivalent** if $\mathcal{E}_{T_1} \simeq \mathcal{E}_{T_2}$.  
- Implies: identical categories of models up to equivalence, hence empirically indistinguishable.  
- Categorical structure refines the structuralist "same theory, different syntax" view.

---

## 6. Summary Mapping Table

| Philosophy of Science Concept     | Category-Theory Construct                                    |
|----------------------------------|--------------------------------------------------------------|
| Instrument / POV dependence       | Fibration $p: E \to C$ with reindexing functors            |
| Observational equivalence         | Collapse under reduct functor $f^*$                        |
| Theory translation                | Institution morphism                                         |
| Inter-theory reduction            | Geometric morphism $\mathcal{E}_S \to \mathcal{E}_T$       |
| Actual vs potential models        | Subobjects/classifying subtopos of $\mathcal{E}_T$         |
| Intended models                   | Functor from empirical systems to $\mathbf{Mod}(\Sigma)$   |
| Morita equivalence                | Equivalence of classifying toposes                          |

---
