# Toy Example: Category-Theoretic Structuralism for Newtonian Collision

We illustrate how category-theoretic structuralism can encode differences between fine and coarse models of Newtonian-style collision, emphasizing the role of translation functors and observational equivalence.

---

## 1. Fine Sketch $\mathcal{S}$

We begin with a finite-product sketch $\mathcal{S}$ representing a simplified Newtonian setting.

- **Objects**:  
  - $P$: particles  
  - $T$: times  
  - $V$: values (for positions, velocities, forces)  
  - $PT$: product $P \times T$  
  - $1$: terminal object

- **Arrows**:  
  - Projections $\pi_1: PT \to P, \pi_2: PT \to T$  
  - Observables:  
    - $\mathrm{pos}: PT \to V$  
    - $\mathrm{vel}: PT \to V$  
    - $\mathrm{force}: PT \to V$  
  - Parameter: $\mathrm{mass}: P \to \mathbb{N}$

- **Constraints**:  
  We encode a toy version of Newton's second law:  

  $$
  \forall p \in P, \; m(p)\cdot \big( \mathrm{vel}(p,t_1)-\mathrm{vel}(p,t_0) \big) \;=\; \mathrm{force}(p,t_0).
  $$

This sketch determines the category $\mathbf{Mod}(\mathcal{S})$ of **fine models**: product-preserving functors $\mathcal{S}\to\mathbf{Set}$.

---

## 2. Fine Models

### Fine Model $M_1$ (external impulse)

- **Carriers**: $P=\{a,b\}$, $T=\{t_0,t_1\}$, $V=\{-1,0,+1\}$.
- **Assignments**:  
  - $\mathrm{mass}(a)=\mathrm{mass}(b)=1$.  
  - Positions:  
    $\mathrm{pos}(a,t_0)=0, \; \mathrm{pos}(a,t_1)=1$  
    $\mathrm{pos}(b,t_0)=2, \; \mathrm{pos}(b,t_1)=1$  
  - Velocities:  
    $\mathrm{vel}(a,t_0)=0, \; \mathrm{vel}(a,t_1)=+1$  
    $\mathrm{vel}(b,t_0)=0, \; \mathrm{vel}(b,t_1)=-1$  
  - Forces:  
    $\mathrm{force}(a,t_0)=+1, \; \mathrm{force}(b,t_0)=-1$

**Interpretation:** particles collide because each experiences an *external impulse* at $t_0$.

---

### Fine Model $M_2$ (internal hidden interaction)

- **Carriers**: same as $M_1$.  
- **Assignments**:  
  - Same positions and velocities as $M_1$.  
  - $\mathrm{force}(a,t_0)=\mathrm{force}(b,t_0)=0$.  
  - Newton’s law is satisfied because we **postulate an internal holonomic constraint** (a hidden potential linking $a$ and $b$).  
  - The kinematic evolution is "baked into" the constraint rather than explained by explicit external forces.

**Interpretation:** the observed positions and velocities are identical to $M_1$, but the dynamical explanation differs: no external impulse, only internal hidden structure.

---

## 3. Coarse Sketch $\mathcal{S}_{\text{coarse}}$

We now define a **coarse sketch** $\mathcal{S}_{\text{coarse}}$:

- Objects: $P,T,V,PT$  
- Observable: only $\mathrm{pos}: PT \to V$

No velocities, forces, or masses are represented. Thus, $\mathbf{Mod}(\mathcal{S}_{\text{coarse}})$ are models that describe **positions over time only**.

---

## 4. Reduct Functor

The forgetful sketch morphism $\sigma: \mathcal{S}_{\text{coarse}} \to \mathcal{S}$ induces a **reduct functor**:

$$
r^{*}: \mathbf{Mod}(\mathcal{S}) \;\to\; \mathbf{Mod}(\mathcal{S}_{\text{coarse}}).
$$

- For $M_1$ and $M_2$, we compute:

$$
r^{*}(M_1) = r^{*}(M_2) = N,
$$

where $N$ is the coarse model with:  
- $P=\{a,b\}, T=\{t_0,t_1\}$,  
- $\mathrm{pos}$ as in $M_1$ and $M_2$.  

**Observation:** Although $M_1 \neq M_2$ in $\mathbf{Mod}(\mathcal{S})$, their reducts are identical in $\mathbf{Mod}(\mathcal{S}_{\text{coarse}})$. This encodes **observational equivalence** at the coarse level.

$$
\begin{array}{ccc}
  & r^{*} & \\
M_1 & \longmapsto & N \\
M_2 & \longmapsto & N
\end{array}
$$

Or, as a commutative diagram:

$$
\begin{array}{ccc}
  & r^{*} & \\
M_1 \quad M_2 & \longrightarrow & N
\end{array}
$$

---

## 5. Relation Between Sketches and Models

- **Fine sketch $\mathcal{S}$**: allows us to distinguish between external-impulse dynamics ($M_1$) and hidden-constraint dynamics ($M_2$).  
- **Coarse sketch $\mathcal{S}_{\text{coarse}}$**: collapses this distinction, since both models yield the same position data.  
- **Translation**: $r^{*}$ formalizes the move from fine models to observationally coarser models.  

Thus, $\mathcal{S}$ vs. $\mathcal{S}_{\text{coarse}}$ defines *what aspects of the world can be distinguished*, and $M_1$ vs. $M_2$ are *different explanations that are observationally indistinguishable* once translated.

---

## 6. Institution Perspective

We can package this as an institution $\mathcal{I}=(\text{Sign},\text{Sen},\text{Mod},\models)$:

- $\text{Sign}$ = category of sketches.  
- $\text{Sen}(\mathcal{S})$ = diagrammatic constraints.  
- $\text{Mod}(\mathcal{S})$ = product-preserving functors.  
- Satisfaction $M \models_\mathcal{S} \varphi$ = usual categorical satisfaction.

The signature morphism $\sigma: \mathcal{S}_{\text{coarse}}\to\mathcal{S}$ induces:

- Sentence translation $\sigma^{*}$,  
- Model reduct $r^{*}$.

**Satisfaction condition:**  

$$
M \models_\mathcal{S} \varphi \;\;\iff\;\; r^{*}(M) \models_{\mathcal{S}_{\text{coarse}}} \sigma^{*}(\varphi).
$$

This expresses that **truth of coarse-level statements is invariant under reduct**, i.e. independent of which fine model we choose.

---

Diagrammatic relationship between sketches:

$$
\begin{array}{ccc}
\mathcal{S} & \xleftarrow{\sigma} & \mathcal{S}_{\text{coarse}} \\
\downarrow r^{*} & & \downarrow \\
\mathbf{Mod}(\mathcal{S}) & \xrightarrow{r^{*}} & \mathbf{Mod}(\mathcal{S}_{\text{coarse}})
\end{array}
$$
