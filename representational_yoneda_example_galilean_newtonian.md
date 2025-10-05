# Galilean → Newtonian Mechanics  
### Fully Formalized 2-Categorical, Yoneda / Probing Representation

This is a **complete categorical reconstruction** of the Galilean → Newtonian transition, expressed within a **2-categorical**, **fibered**, and **Yoneda-based probing** framework.  
No informal steps or "handwaving" are used.

---

## 0. Architecture Overview

We construct:

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
   together with a **cartesian functor**
   \[
   \Phi:\mathrm{Mod}_{\mathrm{New}}\to\mathrm{Mod}_{\mathrm{Gal}}
   \quad\text{covering}\quad
   \pi_{\mathcal{I}}
   \]
   and a coherence 2-cell
   \[
   \kappa:\;p_{\mathrm{Gal}}\circ \Phi \;\xRightarrow{\cong}\; \pi_{\mathcal{I}}\circ p_{\mathrm{New}}.
   \]

3. **Probe categories** with embeddings
   \[
   \mathcal{P}_{\mathrm{New}} \xrightarrow{r} \mathcal{P}_{\mathrm{Gal}},
   \qquad
   i_{\mathrm{New}}:\mathcal{P}_{\mathrm{New}}\to\mathrm{Mod}_{\mathrm{New}},
   \quad
   i_{\mathrm{Gal}}:\mathcal{P}_{\mathrm{Gal}}\to\mathrm{Mod}_{\mathrm{Gal}}.
   \]
   These represent the *probes* by which models are empirically or structurally tested.

4. **Presheaf representations (Yoneda probes)**
   \[
   \widehat{\mathrm{Mod}}_{\mathrm{New}}
   = [\mathcal{P}_{\mathrm{New}}^{\mathrm{op}}, \mathbf{Set}],
   \qquad
   \widehat{\mathrm{Mod}}_{\mathrm{Gal}}
   = [\mathcal{P}_{\mathrm{Gal}}^{\mathrm{op}}, \mathbf{Set}],
   \]
   and their **Yoneda embeddings**
   \[
   y_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\widehat{\mathrm{Mod}}_{\mathrm{New}},
   \quad
   y_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\widehat{\mathrm{Mod}}_{\mathrm{Gal}}.
   \]

5. **Interpretation functors**
   \[
   J_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\mathcal{Emp}_{\mathrm{New}},
   \quad
   J_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\mathcal{Emp}_{\mathrm{Gal}}.
   \]

6. **Empirical translation**
   \[
   H:\mathcal{Emp}_{\mathrm{New}}\to\mathcal{Emp}_{\mathrm{Gal}}.
   \]

7. **Empirical adequacy 2-cell**
   \[
   \eta:\;
   J_{\mathrm{Gal}}\circ\Phi
   \;\Rightarrow\;
   H\circ J_{\mathrm{New}}.
   \]

---

## 1. Instrument Fibrations

### 1.1 Galilean Instruments  $\mathcal{I}_{\mathrm{Gal}}$
- **Objects:** tuples $(F,R,C)$ of frame, ruler, clock.  
- **Morphisms:** Galilean isometries $(\phi_F,\phi_R,\phi_C)$.

### 1.2 Newtonian Instruments  $\mathcal{I}_{\mathrm{New}}$
- **Objects:** $(F,R,C,S)$ with $S$ a sensor of acceleration/force.  
- **Morphisms:** $(\psi_F,\psi_R,\psi_C,\psi_S)$ preserving sensor structure.

### 1.3 Projection Functor
\[
\pi_{\mathcal{I}}:\mathcal{I}_{\mathrm{New}}\to\mathcal{I}_{\mathrm{Gal}},
\quad
\pi_{\mathcal{I}}(F,R,C,S)=(F,R,C),
\quad
\pi_{\mathcal{I}}(\psi_F,\psi_R,\psi_C,\psi_S)=(\psi_F,\psi_R,\psi_C).
\]

---

## 2. Model Fibrations

### 2.1 Categories of Models
- $\mathrm{Mod}_{\mathrm{Gal}}$: models of Galilean mechanics (free particles, constant velocity).  
- $\mathrm{Mod}_{\mathrm{New}}$: models of Newtonian mechanics (positions, velocities, accelerations, forces).

### 2.2 Fibrations
Each model is **indexed by an instrument**:
\[
p_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\mathcal{I}_{\mathrm{Gal}},
\quad
p_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\mathcal{I}_{\mathrm{New}}.
\]
Fibers are the models as seen through that instrument.

### 2.3 Fibered Functor Between Models
\[
\Phi:\mathrm{Mod}_{\mathrm{New}}\to\mathrm{Mod}_{\mathrm{Gal}}
\]
covering $\pi_{\mathcal{I}}$ via isomorphism $\kappa$:
\[
\kappa:\;p_{\mathrm{Gal}}\circ\Phi \xRightarrow{\cong} \pi_{\mathcal{I}}\circ p_{\mathrm{New}}.
\]
This expresses the Galilean model as the **limit of the Newtonian model** in the zero-acceleration regime.

---

## 3. Probes and Representations

### 3.1 Probe Categories
\[
\mathcal{P}_{\mathrm{New}},\quad
\mathcal{P}_{\mathrm{Gal}}.
\]
- Objects = “idealized probing setups”: measurements of $(x,v,a,F)$ or $(x,v)$.
- Morphisms = reparametrizations or refinements of measurement schemes.

### 3.2 Probe Embeddings
\[
i_{\mathrm{New}}:\mathcal{P}_{\mathrm{New}}\to\mathrm{Mod}_{\mathrm{New}},
\quad
i_{\mathrm{Gal}}:\mathcal{P}_{\mathrm{Gal}}\to\mathrm{Mod}_{\mathrm{Gal}}.
\]
These embeddings realize probes as special representable submodels (measurement configurations).

### 3.3 Presheaf Categories
\[
\widehat{\mathrm{Mod}}_{\mathrm{New}} = [\mathcal{P}_{\mathrm{New}}^{\mathrm{op}},\mathbf{Set}],
\qquad
\widehat{\mathrm{Mod}}_{\mathrm{Gal}} = [\mathcal{P}_{\mathrm{Gal}}^{\mathrm{op}},\mathbf{Set}].
\]
Each model $M$ determines its **probe response functor**
\[
y_{\mathrm{New}}(M)(P) = \mathrm{Hom}_{\mathrm{Mod}_{\mathrm{New}}}(i_{\mathrm{New}}(P),M),
\]
and analogously for $y_{\mathrm{Gal}}$.

### 3.4 Pullback of Probes
A functor $r:\mathcal{P}_{\mathrm{New}}\to\mathcal{P}_{\mathrm{Gal}}$ gives a **restriction on probes**, allowing direct comparison:
\[
R = r^{*}:[\mathcal{P}_{\mathrm{Gal}}^{\mathrm{op}},\mathbf{Set}]
   \longrightarrow [\mathcal{P}_{\mathrm{New}}^{\mathrm{op}},\mathbf{Set}].
\]

---

## 4. 2-Categorical Representation

We now have a **pseudocommutative square in $\mathbf{Fib}$**:
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

Passing to **representations by probes**, we obtain a 2-cell in $\mathbf{Cat}$:
\[
y_{\mathrm{Gal}}\circ \Phi 
\xRightarrow{\;\Theta\;}
R\circ y_{\mathrm{New}},
\]
where $\Theta$ encodes that the *probe-responses* of Newtonian models converge to those of Galilean models under the zero-acceleration limit.

---

## 5. Empirical Layer

### 5.1 Empirical Categories
\[
\mathcal{Emp}_{\mathrm{New}}, \qquad \mathcal{Emp}_{\mathrm{Gal}}
\]
contain experimental results and their symmetries (time translations, rescalings, etc.).

### 5.2 Interpretation and Translation
\[
J_{\mathrm{New}}:\mathrm{Mod}_{\mathrm{New}}\to\mathcal{Emp}_{\mathrm{New}},
\quad
J_{\mathrm{Gal}}:\mathrm{Mod}_{\mathrm{Gal}}\to\mathcal{Emp}_{\mathrm{Gal}},
\quad
H:\mathcal{Emp}_{\mathrm{New}}\to\mathcal{Emp}_{\mathrm{Gal}}.
\]

### 5.3 Empirical Adequacy 2-Cell
\[
\eta:\;J_{\mathrm{Gal}}\circ\Phi
\Rightarrow
H\circ J_{\mathrm{New}}.
\]
This ensures empirical predictions of Newtonian models reduce correctly to Galilean ones in the appropriate regime.

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

All squares commute up to the indicated 2-cells.

---

## 7. Explicit Example: Free Particle

### 7.1 Newtonian Side
- Model: $(x(t),v(t),a(t),F(t))$ with $a(t)=0$, $F(t)=0$.
- Probes: measurement setups $P_a$ testing acceleration; maps  
  $i_{\mathrm{New}}(P_a)\to M$ trivialize for $a=0$.

### 7.2 Galilean Side
- Model: $(x(t),v(t))$ with $v(t)=v_0$ constant.
- Probes: velocity probes $P_v$; maps $i_{\mathrm{Gal}}(P_v)\to \Phi(M)$ are identical to those from $P_a$ above through $\Theta$.

### 7.3 Empirical Correspondence
\[
\eta_M: J_{\mathrm{Gal}}(\Phi(M)) \longrightarrow H(J_{\mathrm{New}}(M))
\]
is the identity natural transformation on measured velocities.

---

## 8. Philosophical Reading

This construction embodies two key structuralist/Yoneda insights:

1. **Relational definition (Yoneda):**  
   Each physical structure (instrument, model, empirical setup) is *completely determined by its morphisms to and from probes*.  
   The passage to presheaves makes this literal: models are identified by their full response functors \(y(M)\).

2. **Probing (simplicial / representational viewpoint):**  
   Complex systems are characterized by how *families of probes* map into them, and the Newtonian → Galilean transition is a natural transformation between such *response presheaves*.

Hence, this 2-categorical formulation **makes explicit** the structuralist picture: physical theories are higher-categorical organisms whose identity and empirical meaning are encoded entirely in the web of morphisms they sustain with instruments, probes, and phenomena.
