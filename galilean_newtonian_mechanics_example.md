# Galilean vs Newtonian Mechanics: Categorical Example (Fully Formalized)

This example provides a rigorous categorical account of the transition from Galilean to Newtonian mechanics, with explicit formalization of empirical phenomena (Emp), instruments/POVs (I), institutions (Inst), models (Mod), and all relevant categorical constructs.

---

## 1. Institutions: Full Formalization

### Galilean Institution $\mathcal{Inst}_G = (\text{Sign}_G, \text{Sen}_G, \text{Mod}_G, \models_G)$
- **Signatures $\Sigma_G$:**
  - Sorts: $\mathsf{Space}$ (Euclidean space $\mathbb{R}^3$), $\mathsf{Time}$ ($\mathbb{R}$), $\mathsf{Vel}$ (velocity vectors).
  - Operations: $+$, scalar multiplication, Galilean transformation $x' = x + vt$.
- **Sentences $\text{Sen}_G(\Sigma_G)$:**
  - $\gamma_1$: $v = \text{const}$ (constant velocity motion)
  - $\gamma_2$: $x(t) = x_0 + vt$
- **Models $\text{Mod}_G(\Sigma_G)$:**
  - Objects: $M_G = (\mathbb{R}^3, \mathbb{R}, v)$
  - Morphisms: Galilean transformations, time translations.
- **Satisfaction $\models_G$:**
  - $M_G \models_G \gamma$ iff $M_G$ interprets $\gamma$ as true (e.g., $v$ is constant).

### Newtonian Institution $\mathcal{Inst}_N = (\text{Sign}_N, \text{Sen}_N, \text{Mod}_N, \models_N)$
- **Signatures $\Sigma_N$:**
  - Sorts: $\mathsf{Space}$ ($\mathbb{R}^3$), $\mathsf{Time}$ ($\mathbb{R}$), $\mathsf{Vel}$, $\mathsf{Acc}$ (acceleration), $\mathsf{Force}$.
  - Operations: $+$, scalar multiplication, differentiation, Newton's second law $F = ma$.
- **Sentences $\text{Sen}_N(\Sigma_N)$:**
  - $\nu_1$: $F = ma$
  - $\nu_2$: $a = \frac{dv}{dt}$
  - $\nu_3$: $x(t) = x_0 + v_0 t + \frac{1}{2} a t^2$
- **Models $\text{Mod}_N(\Sigma_N)$:**
  - Objects: $M_N = (\mathbb{R}^3, \mathbb{R}, v(t), a(t), F(t))$
  - Morphisms: Time evolution, force transformations.
- **Satisfaction $\models_N$:**
  - $M_N \models_N \nu$ iff $M_N$ interprets $\nu$ as true (e.g., $F = ma$ holds).

---

## 2. Instruments/POVs/Observational Languages


### Galilean Instruments $\mathcal{I}_G$
**Definition:** $\mathcal{I}_G$ is a category whose objects are tuples $(F, R, C)$, where:
  - $F$: Reference frame (an affine coordinate system in $\mathbb{R}^3$)
  - $R$: Ruler (a mapping $r: \mathbb{R}^3 \to \mathbb{R}$ for measuring distances)
  - $C$: Clock (a mapping $c: \mathbb{R} \to \mathbb{R}$ for measuring time)
Morphisms $\phi: (F, R, C) \to (F', R', C')$ are triples $(\phi_F, \phi_R, \phi_C)$ where:
  - $\phi_F$: Galilean transformation (translation, rotation, boost) between frames
  - $\phi_R$: Isomorphism of rulers (e.g., rescaling, shifting)
  - $\phi_C$: Isomorphism of clocks (e.g., time translation, rescaling)
Composition: $(\phi_F, \phi_R, \phi_C) \circ (\psi_F, \psi_R, \psi_C) = (\phi_F \circ \psi_F, \phi_R \circ \psi_R, \phi_C \circ \psi_C)$
Identity: $\mathrm{id}_{(F, R, C)} = (\mathrm{id}_F, \mathrm{id}_R, \mathrm{id}_C)$
Closure: Composition and identity are well-defined; morphisms are invertible if each component is invertible.

### Newtonian Instruments $\mathcal{I}_N$
**Definition:** $\mathcal{I}_N$ is a category whose objects are tuples $(F, R, C, S)$, where:
  - $F$: Reference frame (as above)
  - $R$: Ruler (as above)
  - $C$: Clock (as above)
  - $S$: Sensor (force sensor or accelerometer, modeled as a mapping $s: \mathbb{R}^3 \times \mathbb{R} \to \mathbb{R}$)
Morphisms $\psi: (F, R, C, S) \to (F', R', C', S')$ are quadruples $(\psi_F, \psi_R, \psi_C, \psi_S)$ where:
  - $\psi_F$: Galilean transformation (translation, rotation, boost)
  - $\psi_R$: Isomorphism of rulers
  - $\psi_C$: Isomorphism of clocks
  - $\psi_S$: Isomorphism of sensors (e.g., calibration, rescaling)
Composition: $(\psi_F, \psi_R, \psi_C, \psi_S) \circ (\chi_F, \chi_R, \chi_C, \chi_S) = (\psi_F \circ \chi_F, \psi_R \circ \chi_R, \psi_C \circ \chi_C, \psi_S \circ \chi_S)$
Identity: $\mathrm{id}_{(F, R, C, S)} = (\mathrm{id}_F, \mathrm{id}_R, \mathrm{id}_C, \mathrm{id}_S)$
Closure: Composition and identity are well-defined; morphisms are invertible if each component is invertible.

---

## 3. Models and Fibrations

- **Galilean models fibered over Galilean instruments:**
  - $p_G: \text{Mod}_G(\Sigma_G) \to \mathcal{I}_G$, $p_G((\mathbb{R}^3, \mathbb{R}, v)) = $ velocity measurement setup
- **Newtonian models fibered over Newtonian instruments:**
  - $p_N: \text{Mod}_N(\Sigma_N) \to \mathcal{I}_N$, $p_N((\mathbb{R}^3, \mathbb{R}, v(t), a(t), F(t))) = $ force/acceleration measurement setup
- **Fibration structure:**
  - For each instrument $I$ in $\mathcal{I}_G$ or $\mathcal{I}_N$, the fiber $p^{-1}(I)$ is the category of models as seen by $I$.

---

## 4. Empirical Phenomena and Interpretation Functors

### Galilean Empirical Category $\mathcal{Emp}_G$
- **Objects:** Empirical outcomes/statistics for Galilean measurements (e.g., measured constant velocity, position over time).
- **Morphisms:** Change of measurement, time translation.

### Newtonian Empirical Category $\mathcal{Emp}_N$
- **Objects:** Empirical outcomes/statistics for Newtonian measurements (e.g., measured acceleration, force, position over time).
- **Morphisms:** Change of measurement, time translation.

### Empirical Interpretation Functors
- $J_G: \text{Mod}_G(\Sigma_G) \to \mathcal{Emp}_G$, $J_G((\mathbb{R}^3, \mathbb{R}, v), I) = $ measured velocity/statistics
- $J_N: \text{Mod}_N(\Sigma_N) \to \mathcal{Emp}_N$, $J_N((\mathbb{R}^3, \mathbb{R}, v(t), a(t), F(t)), I) = $ measured acceleration/force/statistics

---

## 5. Institution Morphisms: Galilean-to-Newtonian Translation

- **Signature morphism:** $\Phi: \Sigma_G \to \Sigma_N$, e.g., $x \mapsto x$, $v \mapsto v$, $t \mapsto t$
- **Sentence morphism:** $\alpha: \text{Sen}_G(\Sigma_G) \to \text{Sen}_N(\Phi\Sigma_G)$, e.g., $\gamma_1$ (constant velocity) $\mapsto$ $\nu_2$ (zero acceleration)
- **Model morphism:** $\beta: \text{Mod}_N(\Phi\Sigma_G) \to \text{Mod}_G(\Sigma_G)$, e.g., $v(t), a(t), F(t) \mapsto v$ when $a(t) = 0$
- **Satisfaction condition:**
  $$
  M_N \models_N \alpha(\gamma) \iff \beta(M_N) \models_G \gamma
  $$

---

## 6. Functorial and Natural Transformations

- **Empirical functor:** $H: \mathcal{Emp}_N \to \mathcal{Emp}_G$, $H($measured acceleration/force$) = $measured velocity/statistics when $a = 0$
- **Model functor:** $F: \text{Mod}_N(\Sigma_N) \to \text{Mod}_G(\Sigma_G)$, $F(v(t), a(t), F(t)) = v$ when $a(t) = 0$
- **Instrument functor:** $G: \mathcal{I}_N \to \mathcal{I}_G$, $G($force/acceleration setup$) = $velocity setup
- **Natural transformation:** $\eta: J_G \circ F \Rightarrow H \circ J_N$

---

## 7. (Co)limits and Universal Properties

- **Diagrams:** $D_N: \Lambda \to \text{Mod}_N(\Sigma_N)$, $D_G: \Lambda \to \text{Mod}_G(\Sigma_G)$ (indexed by $a$, $F$, $t$)
- **Colimit:** $\mathrm{colim}_{a \to 0} F(D_N)$ in $\text{Mod}_G(\Sigma_G)$ is the universal Galilean model for zero acceleration
- **Pullbacks/pushouts:** Used to describe overlap or extension of empirical content between frameworks.

---

## 8. Explicit Example: Free Particle

- **Galilean:**
  - Signature: $\Sigma_G$ as above
  - Model: $v = \text{const}$
  - Instrument: Velocity measurement setup
  - Empirical: Measured $v$ over time
  - Satisfaction: $M_G \models_G \gamma_1$

- **Newtonian:**
  - Signature: $\Sigma_N$ as above
  - Model: $a(t) = 0$, $F(t) = 0$, $v(t) = v_0$
  - Instrument: Force/acceleration measurement setup
  - Empirical: Measured $a = 0$, $F = 0$, $v = v_0$
  - Satisfaction: $M_N \models_N \nu_2$, $M_N \models_N \nu_1$

- **Translation:**
  - $\Phi(x) = x$, $\Phi(v) = v$, $\Phi(t) = t$
  - $\alpha(\gamma_1) = \nu_2$ (constant velocity $\to$ zero acceleration)
  - $\beta(v(t), a(t), F(t)) = v$ when $a(t) = 0$
  - $H($measured $a = 0, F = 0, v = v_0$) = $measured $v = v_0$

---

## 9. (Co)limits and Institution Model Morphisms: Full Formalization

### 9.1. Diagrams of Models and Model Morphisms
- Let $\Lambda$ be an indexing category (e.g., acceleration $a$, force $F$, time $t$).
- Diagram $D_N: \Lambda \to \text{Mod}_N(\Sigma_N)$, $D_N(a) = (v(t), a, F)$
- Model morphisms: Time evolution, instrument change.
- $F(D_N): \Lambda \to \text{Mod}_G(\Sigma_G)$, $F(D_N(a)) = v$ when $a = 0$

### 9.2. (Co)limit Construction and Compatibility
- Colimit $\mathrm{colim}_{a \to 0} F(D_N)$ in $\text{Mod}_G(\Sigma_G)$ is the universal Galilean model for zero acceleration.
- Institution morphism $\beta$ satisfies:
  $$
  \beta\left(\mathrm{colim}_{a \to 0} F(D_N)\right) \cong \mathrm{colim}_{a \to 0} \beta \circ F(D_N)
  $$
- This ensures the process of taking the Galilean limit and translating models via institution morphisms is functorial and commutes with the (co)limit construction.
