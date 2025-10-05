# Galilean → Newtonian Mechanics  
### Fully Formalized 2-Categorical, Yoneda / Probing Representation (Extended Version)

This version unifies the full **2-categorical**, **fibered**, **Yoneda-probe**, and **limit-based** account of the Galilean → Newtonian relation, integrating both **empirical adequacy** and **limiting behavior** (colimits of diagrams) into a single coherent framework.

---

## 0. Architecture Overview

We construct the following system of categories, fibrations, functors, and 2-cells:

1. **Instrument fibrations**
   \[
   \mathcal{I}_{\mathrm{New}} 
   \xrightarrow{\;\pi_{\mathcal{I}}\;}
   \mathcal{I}_{\mathrm{Gal}}
   \]

2. **Model fibrations**
   \[
   p_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\mathcal{I}_{\mathrm{New}}, 
   \qquad
   p_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\mathcal{I}_{\mathrm{Gal}}
   \]
   with a **cartesian functor**
   \[
   \Phi:\mathrm{Mod}_{\mathrm{New}}\to\mathrm{Mod}_{\mathrm{Gal}}
   \quad\text{covering}\quad
   \pi_{\mathcal{I}}
   \]
   and coherence isomorphism
   \[
   \kappa:\;p_{\mathrm{Gal}}\circ \Phi \;\xRightarrow{\cong}\; \pi_{\mathcal{I}}\circ p_{\mathrm{New}}.
   \]

3. **Probe categories and embeddings**
   \[
   \mathcal{P}_{\mathrm{New}} \xrightarrow{r} \mathcal{P}_{\mathrm{Gal}},
   \qquad
   i_{\mathrm{New}}:\mathcal{P}_{\mathrm{New}}\hookrightarrow\mathrm{Mod}_{\mathrm{New}},
   \quad
   i_{\mathrm{Gal}}:\mathcal{P}_{\mathrm{Gal}}\hookrightarrow\mathrm{Mod}_{\mathrm{Gal}}.
   \]

4. **Presheaf representations (Yoneda probes)**
   \[
   \widehat{\mathrm{Mod}}_{\mathrm{New}} = [\mathcal{P}_{\mathrm{New}}^{\mathrm{op}},\mathbf{Set}],
   \quad
   \widehat{\mathrm{Mod}}_{\mathrm{Gal}} = [\mathcal{P}_{\mathrm{Gal}}^{\mathrm{op}},\mathbf{Set}],
   \]
   with Yoneda embeddings
   \[
   y_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\widehat{\mathrm{Mod}}_{\mathrm{New}},
   \quad
   y_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\widehat{\mathrm{Mod}}_{\mathrm{Gal}}.
   \]

5. **Empirical interpretation**
   \[
   J_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\mathcal{Emp}_{\mathrm{New}},
   \quad
   J_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\mathcal{Emp}_{\mathrm{Gal}},
   \]
   with empirical translation
   \[
   H:\mathcal{Emp}_{\mathrm{New}}\to\mathcal{Emp}_{\mathrm{Gal}},
   \quad
   \eta:\;J_{\mathrm{Gal}}\circ\Phi \Rightarrow H\circ J_{\mathrm{New}}.
   \]

---

## 1. Instrument Fibrations

### 1.1 Galilean Instruments  $\mathcal{I}_{\mathrm{Gal}}$
- **Objects:** $(F, R, C)$ = frame, ruler, clock.  
- **Morphisms:** Galilean isometries $(\phi_F,\phi_R,\phi_C)$ preserving unit scales.  
- **Composition:** componentwise.

### 1.2 Newtonian Instruments  $\mathcal{I}_{\mathrm{New}}$
- **Objects:** $(F, R, C, S)$ with $S$ a force/acceleration sensor.  
- **Morphisms:** $(\psi_F,\psi_R,\psi_C,\psi_S)$ preserving sensor calibration.

### 1.3 Projection Functor
\[
\pi_{\mathcal{I}}(F,R,C,S)=(F,R,C),
\quad
\pi_{\mathcal{I}}(\psi_F,\psi_R,\psi_C,\psi_S)=(\psi_F,\psi_R,\psi_C).
\]
This forgets the force-sensor component, aligning Newtonian instruments with their Galilean bases.

---

## 2. Model Fibrations and the Fibered Functor

### 2.1 Model Categories
- $\mathrm{Mod}_{\mathrm{Gal}}$: Galilean models of free motion $(x,v)$ with $v=\mathrm{const}$.  
- $\mathrm{Mod}_{\mathrm{New}}$: Newtonian models $(x,v,a,F)$ with $F=ma$.

### 2.2 Fibrations
Each model is indexed by its instrument:
\[
p_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\mathcal{I}_{\mathrm{Gal}},
\quad
p_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\mathcal{I}_{\mathrm{New}}.
\]
Fibers $p^{-1}(I)$ represent models *as seen through a given instrument* $I$.

### 2.3 Covering Functor Between Models
\[
\Phi:\mathrm{Mod}_{\mathrm{New}}\to\mathrm{Mod}_{\mathrm{Gal}},
\]
with coherence 2-cell
\[
\kappa:\;p_{\mathrm{Gal}}\circ \Phi \xRightarrow{\cong}\pi_{\mathcal{I}}\circ p_{\mathrm{New}}.
\]
Intuitively, $\Phi$ “forgets” acceleration and force, or equivalently, maps each Newtonian model to its *Galilean limit form*.

---

## 3. Probe Categories and Yoneda Representation

### 3.1 Probe Categories
- $\mathcal{P}_{\mathrm{New}}$: controllable measuring configurations for position, velocity, acceleration, and force.
- $\mathcal{P}_{\mathrm{Gal}}$: configurations for position and velocity only.

Each probe represents a *representable* experimental setup.

### 3.2 Embedding of Probes in Models
\[
i_{\mathrm{New}}:\mathcal{P}_{\mathrm{New}}\hookrightarrow\mathrm{Mod}_{\mathrm{New}},
\quad
i_{\mathrm{Gal}}:\mathcal{P}_{\mathrm{Gal}}\hookrightarrow\mathrm{Mod}_{\mathrm{Gal}}.
\]
These are **fully faithful** embeddings:
\[
\mathrm{Hom}_{\mathcal{P}}(P,Q)\;\cong\;\mathrm{Hom}_{\mathrm{Mod}}(i(P),i(Q)),
\]
identifying probes as representable “measurement-models”.

### 3.3 Presheaf Categories (Yoneda Layer)
\[
\widehat{\mathrm{Mod}}_{\mathrm{New}} = [\mathcal{P}_{\mathrm{New}}^{\mathrm{op}},\mathbf{Set}],
\qquad
\widehat{\mathrm{Mod}}_{\mathrm{Gal}} = [\mathcal{P}_{\mathrm{Gal}}^{\mathrm{op}},\mathbf{Set}].
\]
Each model $M$ defines its **probe-response presheaf**:
\[
y_{\mathrm{New}}(M)(P) = \mathrm{Hom}_{\mathrm{Mod}_{\mathrm{New}}}(i_{\mathrm{New}}(P),M),
\]
and analogously for $y_{\mathrm{Gal}}$.

A general model is thus *known only via its functor of responses to probes*; probes themselves correspond to representable presheaves.

### 3.4 Restriction on Probes
The functor $r:\mathcal{P}_{\mathrm{New}}\to\mathcal{P}_{\mathrm{Gal}}$ induces
\[
R = r^{*}:[\mathcal{P}_{\mathrm{Gal}}^{\mathrm{op}},\mathbf{Set}]
   \longrightarrow [\mathcal{P}_{\mathrm{New}}^{\mathrm{op}},\mathbf{Set}],
\]
linking the two levels of probe representation.

---

## 4. 2-Categorical Representation and Limit Behavior

We obtain a **pseudocommutative diagram in $\mathbf{Fib}$**:
\[
\begin{array}{ccccc}
\mathrm{Mod}_{\mathrm{New}} 
& \xrightarrow{\;\Phi\;} 
& \mathrm{Mod}_{\mathrm{Gal}} \\[0.5em]
\Big\downarrow{p_{\mathrm{New}}} 
& \;\overset{\kappa}{\Rightarrow}\;
& \Big\downarrow{p_{\mathrm{Gal}}} \\[0.5em]
\mathcal{I}_{\mathrm{New}} 
& \xrightarrow{\;\pi_{\mathcal{I}}\;}
& \mathcal{I}_{\mathrm{Gal}}
\end{array}
\]

Passing to presheaves yields a 2-cell in $\mathbf{Cat}$:
\[
y_{\mathrm{Gal}}\circ \Phi 
\xRightarrow{\;\Theta\;}
R\circ y_{\mathrm{New}},
\]
where $\Theta$ expresses the *convergence of probe-responses* under the limit $a\to 0$.

### 4.1 Colimit Construction (Galilean Limit)

Let $\Lambda$ be a filtering category indexing decreasing accelerations.  
A diagram
\[
D_{\mathrm{New}} : \Lambda \to \mathrm{Mod}_{\mathrm{New}}, 
\quad
D_{\mathrm{New}}(\lambda) = M_{a(\lambda)}
\]
describes models with acceleration parameter $a(\lambda)$.

Then the **Galilean model** is the colimit:
\[
\mathrm{colim}_\Lambda \Phi(D_{\mathrm{New}}) \in \mathrm{Mod}_{\mathrm{Gal}}.
\]
Empirically, this captures the limit of Newtonian trajectories as forces vanish.

### 4.2 Compatibility with Empirical Interpretation
\[
\eta_{\mathrm{colim}}:\;
J_{\mathrm{Gal}}\Big(\mathrm{colim}_\Lambda \Phi(D_{\mathrm{New}})\Big)
\longrightarrow
H\Big(\mathrm{colim}_\Lambda J_{\mathrm{New}}(D_{\mathrm{New}})\Big),
\]
ensuring the colimit commutes with interpretation up to the natural 2-cell $\eta$.

---

## 5. Empirical Layer and Adequacy

### 5.1 Empirical Categories
\[
\mathcal{Emp}_{\mathrm{New}}, \qquad \mathcal{Emp}_{\mathrm{Gal}}
\]
contain measured data and symmetries (time shifts, rescalings).

### 5.2 Interpretation and Translation
\[
J_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\mathcal{Emp}_{\mathrm{New}},
\quad
J_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\mathcal{Emp}_{\mathrm{Gal}},
\quad
H:\mathcal{Emp}_{\mathrm{New}}\to\mathcal{Emp}_{\mathrm{Gal}}.
\]

### 5.3 Empirical Adequacy
\[
\eta:\;
J_{\mathrm{Gal}}\circ\Phi
\Rightarrow
H\circ J_{\mathrm{New}}.
\]
This 2-cell guarantees that, when restricted to Galilean regimes, Newtonian predictions are empirically indistinguishable from Galilean ones — ensuring **empirical adequacy** of the reduction.

---

## 6. Full 2-Categorical Summary Diagram

\[
\begin{array}{ccccc}
\mathcal{I}_{\mathrm{New}}
& \xrightarrow{\;\pi_{\mathcal{I}}\;}
& \mathcal{I}_{\mathrm{Gal}} \\[1em]
\Big\downarrow{p_{\mathrm{New}}}
& \;\overset{\kappa}{\Rightarrow}\;
& \Big\downarrow{p_{\mathrm{Gal}}} \\[1em]
\mathrm{Mod}_{\mathrm{New}}
& \xrightarrow{\;\Phi\;}
& \mathrm{Mod}_{\mathrm{Gal}} \\[1em]
\Big\downarrow{y_{\mathrm{New}}}
& \;\overset{\Theta}{\Rightarrow}\;
& \Big\downarrow{y_{\mathrm{Gal}}} \\[1em]
\widehat{\mathrm{Mod}}_{\mathrm{New}}
& \xrightarrow{R}
& \widehat{\mathrm{Mod}}_{\mathrm{Gal}} \\[1em]
\Big\downarrow{J_{\mathrm{New}}}
& \;\overset{\eta}{\Rightarrow}\;
& \Big\downarrow{J_{\mathrm{Gal}}} \\[1em]
\mathcal{Emp}_{\mathrm{New}}
& \xrightarrow{H}
& \mathcal{Emp}_{\mathrm{Gal}}
\end{array}
\]
All squares commute up to the indicated 2-cells, capturing structural, representational, and empirical correspondences.

---

## 7. Explicit Example: Free Particle

### 7.1 Newtonian Model
\[
M_{\mathrm{New}} = (x(t),v(t),a(t),F(t)),\quad F(t)=0,\; a(t)=0.
\]
Probes $P_a$ measure acceleration; maps $i_{\mathrm{New}}(P_a)\to M_{\mathrm{New}}$ are trivial.

### 7.2 Galilean Model
\[
M_{\mathrm{Gal}} = (x(t),v(t)),\quad v(t)=v_0.
\]
Velocity probes $P_v$ satisfy
\[
\Theta_{M}: y_{\mathrm{Gal}}(\Phi(M_{\mathrm{New}})) \cong R(y_{\mathrm{New}}(M_{\mathrm{New}})),
\]
showing identical probe-responses in the $a\to 0$ limit.

### 7.3 Empirical Correspondence
\[
\eta_{M_{\mathrm{New}}}: J_{\mathrm{Gal}}(\Phi(M_{\mathrm{New}})) \to H(J_{\mathrm{New}}(M_{\mathrm{New}}))
\]
is the identity transformation on measured velocity signals.

---

## 8. Philosophical and Structuralist Interpretation

1. **Embedding of Probes.**  
   The inclusions
   \[
   i:\mathcal{P}\hookrightarrow\mathrm{Mod}
   \]
   identify probes as **representable submodels**.  
   Their Yoneda images generate all presheaves, so general models are *known through the network of probe-responses* \(y(M)\).

2. **Representability and Empirical Access.**  
   Probes correspond to systems we can directly construct or measure.  
   Non-probe models correspond to *presheaves* encoding hypothetical total responses — epistemically mediated, not directly observable.

3. **Relational Identity (Yoneda Principle).**  
   The “identity” of a model is exhausted by its morphisms from all probes:
   \[
   M \cong N \iff y(M) \cong y(N).
   \]
   Scientific understanding is thus functorial: *to know a system is to know how every probe behaves in it.*

4. **Colimit and Approximation.**  
   The Galilean limit as a filtered colimit expresses a universal property of approximation: Galilean behavior is the *initial universal response pattern* among vanishing-force Newtonian systems.

5. **Empirical Adequacy and Structural Continuity.**  
   The 2-cell $\eta$ witnesses that empirical content is preserved across the theory transition, ensuring that the structural (Yoneda) and empirical (interpretational) layers align coherently.

---

## 9. Summary Schema

\[
\begin{array}{ccccc}
\text{Probes} & \hookrightarrow & \text{Models} & \xrightarrow{y} & \text{Probe-Responses (Presheaves)} \\
 & & \Big\downarrow{J} & \searrow & \Big\downarrow{H} \\
 & & \text{Empirical World} & \xrightarrow{} & \text{Empirical Coarse Layer}
\end{array}
\]

The **probing-Yoneda** layer formalizes epistemic access, while the **colimit** construction formalizes theoretical approximation.  
Together they yield a complete structuralist model of scientific theory change — *reduction as representable limit*, *empirical continuity as naturality*.

---
