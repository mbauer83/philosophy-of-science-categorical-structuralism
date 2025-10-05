# Galilean → Newtonian Mechanics: Fully Formalized Categorical Example (renamed)

This example provides a fully explicit categorical account of the transition from Newtonian to Galilean mechanics, with an unambiguous naming scheme:

- Explicit **instrument categories** with morphisms  
- **Fibrations** of model categories over instruments  
- **Empirical categories** and interpretation functors  
- **Functors** between Newtonian and Galilean structures (with cover/coherence data)  
- **Natural transformations** mediating empirical interpretation  
- **Colimit constructions** encoding the Galilean limit

---

## Notation / Naming conventions

- Instrument categories:
  - $\mathcal{I}_{\mathrm{Gal}}$ — Galilean instruments
  - $\mathcal{I}_{\mathrm{New}}$ — Newtonian instruments
- Fibrations (models over instruments):
  - $p_{\mathrm{Gal}} : \mathrm{Mod}_{\mathrm{Gal}} \to \mathcal{I}_{\mathrm{Gal}}$
  - $p_{\mathrm{New}} : \mathrm{Mod}_{\mathrm{New}} \to \mathcal{I}_{\mathrm{New}}$
- Instrument base-change (forgetful / underlying) functor:
  - $\pi_{\mathcal{I}} : \mathcal{I}_{\mathrm{New}} \to \mathcal{I}_{\mathrm{Gal}}$
    (reads: “underlying Galilean instrument of a Newtonian instrument”)
- Model functor (covering $\pi_{\mathcal{I}}$):
  - $\Phi: \mathrm{Mod}_{\mathrm{New}} \to \mathrm{Mod}_{\mathrm{Gal}}$
    (with coherence isomorphism relating $p_{\mathrm{Gal}}\circ\Phi$ and $\pi_{\mathcal{I}}\circ p_{\mathrm{New}}$)
- Empirical categories:
  - $\mathcal{E}_{\mathrm{Gal}}$ — Galilean empirical phenomena
  - $\mathcal{E}_{\mathrm{New}}$ — Newtonian empirical phenomena
- Interpretation functors:
  - $J_{\mathrm{Gal}} : \mathrm{Mod}_{\mathrm{Gal}} \to \mathcal{E}_{\mathrm{Gal}}$
  - $J_{\mathrm{New}} : \mathrm{Mod}_{\mathrm{New}} \to \mathcal{E}_{\mathrm{New}}$
- Empirical reduct / comparison functor:
  - $\Psi : \mathcal{E}_{\mathrm{New}} \to \mathcal{E}_{\mathrm{Gal}}$
- Natural transformation (empirical adequacy of the reduct):
  - $\eta : J_{\mathrm{Gal}}\circ\Phi \Rightarrow \Psi\circ J_{\mathrm{New}}$

---

## 1. Instrument Categories

### 1.1 Galilean Instruments $\mathcal{I}_{\mathrm{Gal}}$
- **Objects:** tuples $(F, R, C)$, where:
  - $F$: reference frame (affine coordinate system in $\mathbb{R}^3$)
  - $R$: ruler $r: \mathbb{R}^3 \to \mathbb{R}$
  - $C$: clock $c: \mathbb{R} \to \mathbb{R}$
- **Morphisms:** triples $(\phi_F, \phi_R, \phi_C)$ where
  - $\phi_F$: Galilean transformation (translation, rotation, boost)
  - $\phi_R$: isomorphism of rulers (rescaling/shifting)
  - $\phi_C$: isomorphism of clocks (translation/rescaling)
- **Composition:** componentwise.

### 1.2 Newtonian Instruments $\mathcal{I}_{\mathrm{New}}$
- **Objects:** tuples $(F, R, C, S)$, with $S$: force/acceleration sensor $s: \mathbb{R}^3\times \mathbb{R}\to \mathbb{R}$
- **Morphisms:** quadruples $(\psi_F, \psi_R, \psi_C, \psi_S)$ with $\psi_S$ an isomorphism of sensors
- **Composition:** componentwise.

### 1.3 Instrument Functor (underlying Galilean instrument)
- $\pi_{\mathcal{I}} : \mathcal{I}_{\mathrm{New}} \to \mathcal{I}_{\mathrm{Gal}}$ defined by
  $$
  \pi_{\mathcal{I}}(F,R,C,S) = (F,R,C),\qquad
  \pi_{\mathcal{I}}(\psi_F,\psi_R,\psi_C,\psi_S) = (\psi_F,\psi_R,\psi_C).
  $$

---

## 2. Model Categories and Fibrations

### 2.1 Galilean Models
- Category $\mathrm{Mod}_{\mathrm{Gal}}$:
  - **Objects:** triples $(\mathbb{R}^3, \mathbb{R}, v(t))$ satisfying Galilean axioms (e.g. for a free particle $v=\text{const}$)
  - **Morphisms:** time evolutions, frame-preserving transformations, etc.
- **Fibration:** $p_{\mathrm{Gal}}: \mathrm{Mod}_{\mathrm{Gal}} \to \mathcal{I}_{\mathrm{Gal}}$ with fiber $p_{\mathrm{Gal}}^{-1}(I)$ = models as seen by instrument $I$.

### 2.2 Newtonian Models
- Category $\mathrm{Mod}_{\mathrm{New}}$:
  - **Objects:** $(\mathbb{R}^3, \mathbb{R}, v(t), a(t), F(t))$ satisfying Newton's laws
  - **Morphisms:** time evolution, frame- and sensor-preserving transformations
- **Fibration:** $p_{\mathrm{New}}: \mathrm{Mod}_{\mathrm{New}} \to \mathcal{I}_{\mathrm{New}}$.

### 2.3 Model Functor Covering the Instrument Functor
- Functor $\Phi: \mathrm{Mod}_{\mathrm{New}} \to \mathrm{Mod}_{\mathrm{Gal}}$ intended to “forget” sensor-specific structure or take an appropriate limit (e.g. $a\to 0$).
- **Covering/coherence data:** a specified natural isomorphism (or equality if strict)
  $$
  \kappa: \; p_{\mathrm{Gal}}\circ\Phi \xRightarrow{\ \cong\ } \pi_{\mathcal{I}}\circ p_{\mathrm{New}},
  $$
  making $\Phi$ into a morphism of fibrations (a *fibered functor*). In practice one chooses $\kappa$ to be identity on the underlying frame/ruler/clock components and discard sensor data.

---

## 3. Empirical Categories and Interpretation

### 3.1 Galilean Empirical Category $\mathcal{E}_{\mathrm{Gal}}$
- **Objects:** measured positions and velocities over time (as read off instruments in $\mathcal{I}_{\mathrm{Gal}}$)
- **Morphisms:** time translations, changes of measurement scale (ruler/clock isomorphisms), etc.

### 3.2 Newtonian Empirical Category $\mathcal{E}_{\mathrm{New}}$
- **Objects:** measured positions, velocities, accelerations, forces over time (sensor-inclusive)
- **Morphisms:** time translations, change of measurement (ruler/clock/sensor isomorphisms)

### 3.3 Interpretation Functors
- $J_{\mathrm{Gal}}: \mathrm{Mod}_{\mathrm{Gal}} \to \mathcal{E}_{\mathrm{Gal}}$, mapping a model to its predicted measured position/velocity signals.
- $J_{\mathrm{New}}: \mathrm{Mod}_{\mathrm{New}} \to \mathcal{E}_{\mathrm{New}}$, mapping to predicted positions/velocities/accelerations/forces.

### 3.4 Empirical Reduct / Comparison Functor
- $\Psi: \mathcal{E}_{\mathrm{New}} \to \mathcal{E}_{\mathrm{Gal}}$ defined by
  $$
  \Psi(\text{measured }(x,v,a,F)) = (\text{measured }x,\ v) \quad\text{(when $a\approx 0$ or sensor info is ignored)}
  $$

### 3.5 Natural Transformation (empirical adequacy)
- A natural transformation
  $$
  \eta : J_{\mathrm{Gal}}\circ\Phi \;\Rightarrow\; \Psi\circ J_{\mathrm{New}}
  $$
  whose component at a Newtonian model $M$ is a map in $\mathcal{E}_{\mathrm{Gal}}$ expressing that the Galilean prediction extracted from $\Phi(M)$ agrees (up to experimental indistinguishability/coarsening) with the Galilean data obtained by discarding Newtonian sensor detail via $\Psi\circ J_{\mathrm{New}}(M)$.

---

## 4. Colimits / Limit Constructions (Galilean limit)

- Let $\Lambda$ be an indexing category whose objects parameterise accelerations $a$, forces $F$, and time $t$, with morphisms representing time evolution or arrows $a_1 \to a_2$ for $a_1$ “smaller” than $a_2$ (a filtered system toward $a\to 0$).
- Diagram $D_{\mathrm{New}}: \Lambda \to \mathrm{Mod}_{\mathrm{New}}$, $D_{\mathrm{New}}(a,F,t) = (v(t), a, F(t))$.
- The Galilean limit is the (filtered) colimit after applying $\Phi$:
  $$
  \mathrm{colim}_{\Lambda} \big(\Phi\circ D_{\mathrm{New}}\big) \in \mathrm{Mod}_{\mathrm{Gal}}.
  $$
- Compatibility with interpretations:
  $$
  \eta_{\mathrm{colim}}: \; J_{\mathrm{Gal}}\Big(\mathrm{colim}_\Lambda \Phi(D_{\mathrm{New}})\Big)
  \;\longrightarrow\; \Psi\Big(\mathrm{colim}_\Lambda J_{\mathrm{New}}(D_{\mathrm{New}})\Big)
  $$
  (provided colimit and $J$ commute appropriately, or by universal property and a coherence argument).

---

## 5. Explicit Example: Free Particle

- **Galilean model:** $v = \mathrm{const}$.
- **Instrument:** velocity-measuring ruler/clock $(F,R,C)$.
- **Empirical outcome:** measured constant velocity $v_0$.

- **Newtonian model:** $v(t) = v_0$, $a(t)=0$, $F(t)=0$.
- **Instrument:** ruler/clock/force sensor $(F,R,C,S)$.
- **Empirical outcome:** measured $a=0$, $F=0$, $v=v_0$.

- **Mappings:**
  - $\pi_{\mathcal{I}}(F,R,C,S) = (F,R,C)$.
  - $\Phi(v(t),a(t),F(t)) = v(t)$ (or more precisely: the Galilean object obtained by applying the fiberwise reduction $\Phi$).
  - $\Psi(a,F,v) = v$ (or coarsening to velocity data).
  - $\eta_{M}$ is identity in this trivial example.

---

## 6. Summary Diagram (Fully Typed, with Instrument Layer)

\[
\begin{array}{ccccc}
\mathcal{I}_{\mathrm{New}} 
& \xrightarrow{\ \pi_{\mathcal{I}}\ } 
& \mathcal{I}_{\mathrm{Gal}} 
& & \text{(instrument forgetful functor)} \\[1em]
\Big\downarrow^{p_{\mathrm{New}}} 
& 
& 
\Big\downarrow^{p_{\mathrm{Gal}}} 
& & \text{(fibrations of models over instruments)} \\[1em]
\mathrm{Mod}_{\mathrm{New}} 
& \xrightarrow{\ \Phi\ } 
& \mathrm{Mod}_{\mathrm{Gal}} 
& & \text{(model functor covering }\pi_{\mathcal{I}}\text{)} \\[1em]
\Big\downarrow^{J_{\mathrm{New}}} 
& \overset{\eta}{\Rightarrow} 
& \Big\downarrow^{J_{\mathrm{Gal}}} 
& & \text{(interpretation functors and natural transformation)} \\[1em]
\mathcal{E}_{\mathrm{New}} 
& \xrightarrow{\ \Psi\ } 
& \mathcal{E}_{\mathrm{Gal}} 
& & \text{(empirical reduct / coarsening)}
\end{array}
\]

\[
\begin{aligned}
&\pi_{\mathcal{I}}: \mathcal{I}_{\mathrm{New}} \to \mathcal{I}_{\mathrm{Gal}}, \\
&\Phi: \mathrm{Mod}_{\mathrm{New}} \to \mathrm{Mod}_{\mathrm{Gal}},\quad
\kappa: p_{\mathrm{Gal}}\circ\Phi \xRightarrow{\ \cong\ } \pi_{\mathcal{I}}\circ p_{\mathrm{New}},\\
&\Psi: \mathcal{E}_{\mathrm{New}} \to \mathcal{E}_{\mathrm{Gal}},\\
&\eta: J_{\mathrm{Gal}}\circ\Phi \Rightarrow \Psi\circ J_{\mathrm{New}}.
\end{aligned}
\]
