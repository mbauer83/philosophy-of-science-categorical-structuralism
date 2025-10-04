# Toy Example: Category-Theoretic Structuralism for Newtonian Collision

We illustrate how category-theoretic structuralism can encode differences between fine and coarse models of Newtonian-style collision.

---

## 1. The Finite-Product Sketch

Define a finite-product sketch $\mathcal{S}$ consisting of:

- **Objects**:  
  $P$ (particles),  
  $T$ (times),  
  $V$ (values, e.g. $\\{-1,0,+1\\}$),  
  $PT$ (product $P \times T$),  
  $1$ (terminal object).

- **Arrows**:  
  - Projections: $\pi_1: PT \to P, \pi_2: PT \to T$.  
  - Observables:  
    $\mathrm{pos}: PT \to V$,  
    $\mathrm{vel}: PT \to V$,  
    $\mathrm{force}: PT \to V$.  
  - Parameters: $\mathrm{mass}: P \to \mathbb{N}$.

- **Commutativities/Constraints** (expressed as diagrams or equations):  
  For Newton's law (toy form):  
  
$$\forall p \in P:\; m(p)\cdot(\mathrm{vel}(p,t_1)-\mathrm{vel}(p,t_0)) = \mathrm{force}(p,t_0).$$

This sketch $\mathcal{S}$ determines a category of models $\mathbf{Mod}(\mathcal{S})$: product-preserving functors $\mathcal{S} \to \mathbf{Set}$.

---

## 2. Models

### Fine model $M_1$ (external impulse)

- Carrier sets: $P = \\{a,b\\}, T = \\{t_0,t_1\\}, V=\\{-1,0,+1\\}$.
- Assignments:  
  $\mathrm{mass}(a)=\mathrm{mass}(b)=1$.  
  $\mathrm{pos}(a,t_0)=0, \mathrm{pos}(b,t_0)=2, \mathrm{pos}(a,t_1)=1, \mathrm{pos}(b,t_1)=1$.  
  $\mathrm{vel}(a,t_0)=0, \mathrm{vel}(a,t_1)=+1$.  
  $\mathrm{vel}(b,t_0)=0, \mathrm{vel}(b,t_1)=-1$.  
  $\mathrm{force}(a,t_0)=+1, \mathrm{force}(b,t_0)=-1$.

### Fine model $M_2$ (internal hidden interaction)

- Same $P,T,V$.  
- Same positions and velocities.  
- Forces are zero at all times. The observed kinematics arise from an internal constraint.

---

## 3. Coarse Signature and Reduct Functor

Define a coarse sketch $\mathcal{S}_{\text{coarse}}$ with objects $P,T,V,PT$, and only the observable $\mathrm{pos}: PT \to V$.

The **reduct functor**:

$$r^*: \mathbf{Mod}(\mathcal{S}) \to \mathbf{Mod}(\mathcal{S}_{\text{coarse}})$$

is induced by the forgetful sketch morphism $\mathcal{S}_{\text{coarse}} \to \mathcal{S}$.

- $r^*(M_1) = r^*(M_2) = N$.

Thus, distinct fine models collapse to the same coarse model:  

$$M_1 \neq M_2 \quad \text{but} \quad r^*(M_1) = r^*(M_2).$$

This encodes **observational equivalence**.

---

## 4. Institution Perspective

An **institution** $\mathcal{I} = (\text{Sign}, \text{Sen}, \text{Mod}, \models)$:  

- Signatures: sketches $\mathcal{S}$.  
- Sentences: diagrammatic constraints.  
- Models: functors preserving products.  
- Satisfaction: usual functorial satisfaction.  

A signature morphism $\sigma: \mathcal{S}_{\text{coarse}} \to \mathcal{S}$ induces reduct/translation functors.  

**Satisfaction condition**: for any coarse sentence $\varphi$,

$$M \models_\mathcal{S} \varphi \;\; \iff \;\; r^*(M) \models_{\mathcal{S}_{\text{coarse}}} \varphi.$$

This formally captures the semantic invariance of observational statements.

---
