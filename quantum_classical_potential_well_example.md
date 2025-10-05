# Quantum-to-Classical Functorial Example: 1D Potential Well (Fully Formalized)

This example provides a rigorous categorical account of the quantum-to-classical transition for a particle in a 1D potential well, with explicit formalization of institutions, models, instruments/POVs, empirical phenomena, and all relevant categorical constructs.

---

## 1. Institutions: Full Formalization

### Quantum Institution $\mathcal{Inst}_Q = (\text{Sign}_Q, \text{Sen}_Q, \text{Mod}_Q, \models_Q)$
- **Signatures $\Sigma_Q$:**
  - Sorts: $\mathsf{Hilb}$ (Hilbert space $L^2([0,a])$), $\mathsf{Obs}$ (self-adjoint operators), $\mathsf{Proj}$ (projectors $P_\Delta$), $\mathsf{Ham}$ (Hamiltonian $H$).
  - Operations: $+$, $\cdot$, $[A,B]$, spectral decomposition, functional calculus.
- **Sentences $\text{Sen}_Q(\Sigma_Q)$:**
  - $\varphi_1$: $H \psi_n = E_n \psi_n$ (energy eigenvalue equation)
  - $\varphi_2$: $\text{Prob}(P_\Delta | \rho) = \operatorname{Tr}(\rho P_\Delta)$ (Born rule)
  - $\varphi_3$: $[x,p] = i\hbar$ (canonical commutation)
- **Models $\text{Mod}_Q(\Sigma_Q)$:**
  - Objects: $M_Q = (L^2([0,a]), \rho)$, where $\rho$ is a density operator (e.g., $\rho = |\psi_n\rangle\langle\psi_n|$)
  - Morphisms: Unitary maps, time evolution $U_t$, symmetries.
- **Satisfaction $\models_Q$:**
  - $M_Q \models_Q \varphi$ iff $M_Q$ interprets $\varphi$ as true (e.g., $\rho$ satisfies Born rule for $P_\Delta$).

### Classical Institution $\mathcal{Inst}_C = (\text{Sign}_C, \text{Sen}_C, \text{Mod}_C, \models_C)$
- **Signatures $\Sigma_C$:**
  - Sorts: $\mathsf{PhSp}$ (phase space $[0,a] \times \mathbb{R}$), $\mathsf{Obs}$ (functions $f(x,p)$), $\mathsf{Ind}$ (indicator functions $D_\Delta$), $\mathsf{Ham}$ (Hamiltonian $H_{cl}$).
  - Operations: $+$, $\cdot$, $\{f,g\}$ (Poisson bracket), integration.
- **Sentences $\text{Sen}_C(\Sigma_C)$:**
  - $\psi_1$: $H_{cl}(x,p) = \frac{p^2}{2m} + V(x)$
  - $\psi_2$: $\text{Prob}(D_\Delta | \mu) = \int_{\Delta} \left(\int \mu(x,p) dp\right) dx$
  - $\psi_3$: $\{x,p\} = 1$
- **Models $\text{Mod}_C(\Sigma_C)$:**
  - Objects: $M_C = ([0,a] \times \mathbb{R}, \mu)$, $\mu$ a probability density (e.g., microcanonical ensemble at $E_n$)
  - Morphisms: Canonical transformations, time evolution $\Phi_t$, symmetries.
- **Satisfaction $\models_C$:**
  - $M_C \models_C \psi$ iff $M_C$ interprets $\psi$ as true (e.g., $\mu$ satisfies Liouville equation).

---

## 2. Instruments/POVs/Observational Languages

### Quantum Instruments $\mathcal{I}_Q$
- **Objects:** Projectors $P_\Delta$ (measurement of position in interval $\Delta$), POVMs, spectral decompositions.
- **Morphisms:** Refinement/coarse-graining of intervals, change of observable.

### Classical Instruments $\mathcal{I}_C$
- **Objects:** Indicator functions $D_\Delta$ (measurement of position in interval $\Delta$), partitions of phase space.
- **Morphisms:** Refinement/coarse-graining, change of observable.

---

## 3. Models and Fibrations

- **Quantum models fibered over quantum instruments:**
  - $p_Q: \text{Mod}_Q(\Sigma_Q) \to \mathcal{I}_Q$, $p_Q((L^2([0,a]), \rho)) = P_\Delta$
- **Classical models fibered over classical instruments:**
  - $p_C: \text{Mod}_C(\Sigma_C) \to \mathcal{I}_C$, $p_C(([0,a] \times \mathbb{R}, \mu)) = D_\Delta$
- **Fibration structure:**
  - For each instrument $I$ in $\mathcal{I}_Q$ or $\mathcal{I}_C$, the fiber $p^{-1}(I)$ is the category of models as seen by $I$.

---

## 4. Empirical Phenomena and Interpretation Functors

### Quantum Empirical Category $\mathcal{Emp}_Q$
- **Objects:** Empirical outcomes/statistics for quantum measurements (e.g., $\operatorname{Tr}(\rho P_\Delta)$)
- **Morphisms:** Change of measurement, time evolution of statistics.

### Classical Empirical Category $\mathcal{Emp}_C$
- **Objects:** Empirical outcomes/statistics for classical measurements (e.g., $\int_{\Delta} \left(\int \mu(x,p) dp\right) dx$)
- **Morphisms:** Change of measurement, time evolution of statistics.

### Empirical Interpretation Functors
- $J_Q: \text{Mod}_Q(\Sigma_Q) \to \mathcal{Emp}_Q$, $J_Q((L^2([0,a]), \rho), P_\Delta) = \operatorname{Tr}(\rho P_\Delta)$
- $J_C: \text{Mod}_C(\Sigma_C) \to \mathcal{Emp}_C$, $J_C(([0,a] \times \mathbb{R}, \mu), D_\Delta) = \int_{\Delta} \left(\int \mu(x,p) dp\right) dx$

---

## 5. Institution Morphisms: Quantum-to-Classical Translation

- **Signature morphism:** $\Phi: \Sigma_Q \to \Sigma_C$, e.g., $x \mapsto x$, $p \mapsto p$, $H \mapsto H_{cl}$
- **Sentence morphism:** $\alpha: \text{Sen}_Q(\Sigma_Q) \to \text{Sen}_C(\Phi\Sigma_Q)$, e.g., $\varphi_2$ (Born rule) $\mapsto$ $\psi_2$ (classical probability)
- **Model morphism:** $\beta: \text{Mod}_C(\Phi\Sigma_Q) \to \text{Mod}_Q(\Sigma_Q)$, e.g., $\mu \mapsto \rho$ via Wigner transform or classical limit
- **Satisfaction condition:**
  $$
  M_C \models_C \alpha(\varphi) \iff \beta(M_C) \models_Q \varphi
  $$

---

## 6. Functorial and Natural Transformations

- **Empirical functor:** $H: \mathcal{Emp}_Q \to \mathcal{Emp}_C$, $H(\operatorname{Tr}(\rho P_\Delta)) = \int_{\Delta} \left(\int W_\rho(x,p) dp\right) dx$
- **Model functor:** $F: \text{Mod}_Q(\Sigma_Q) \to \text{Mod}_C(\Sigma_C)$, $F(\rho) = W_\rho$
- **Instrument functor:** $G: \mathcal{I}_Q \to \mathcal{I}_C$, $G(P_\Delta) = D_\Delta$
- **Natural transformation:** $\eta: J_C \circ F \Rightarrow H \circ J_Q$

---

## 7. (Co)limits and Universal Properties

- **Diagrams:** $D_Q: \Lambda \to \mathcal{Emp}_Q$, $D_C: \Lambda \to \mathcal{Emp}_C$ (indexed by $n$, $\hbar$)
- **Colimit:** $\mathrm{colim}_{n \to \infty} H(J_Q(|\psi_n\rangle\langle\psi_n|)) = J_C(\mu_n)$
- **Pullbacks/pushouts:** Used to describe overlap or extension of empirical content between frameworks.

---

## 8. Concrete Example: 1D Potential Well

- **Quantum:**
  - Signature: $\Sigma_Q$ as above
  - Model: $|\psi_n\rangle\langle\psi_n|$ (energy eigenstate)
  - Instrument: $P_\Delta$ (projector onto $x \in \Delta$)
  - Empirical: $\operatorname{Tr}(|\psi_n\rangle\langle\psi_n| P_\Delta) = \int_{\Delta} |\psi_n(x)|^2 dx$
  - Satisfaction: $|\psi_n\rangle\langle\psi_n| \models_Q \varphi_2$

- **Classical:**
  - Signature: $\Sigma_C$ as above
  - Model: $\mu_n(x,p)$ (microcanonical ensemble at $E_n$)
  - Instrument: $D_\Delta$ (indicator for $x \in \Delta$)
  - Empirical: $\int_{\Delta} \left(\int \mu_n(x,p) dp\right) dx$
  - Satisfaction: $\mu_n \models_C \psi_2$

- **Translation:**
  - $\Phi(x) = x$, $\Phi(p) = p$, $\Phi(H) = H_{cl}$
  - $\alpha(\varphi_2) = \psi_2$
  - $\beta(\mu_n) = |\psi_n\rangle\langle\psi_n|$ in the limit $n \to \infty$
  - $H(\operatorname{Tr}(|\psi_n\rangle\langle\psi_n| P_\Delta)) \to \int_{\Delta} \left(\int \mu_n(x,p) dp\right) dx$

---


## 9. (Co)limits and Institution Model Morphisms: Full Formalization

### 9.1. Diagrams of Models and Model Morphisms
- Let $\Lambda$ be an indexing category (e.g., quantum number $n$, Planck's constant $\hbar$, or time $t$).
- Consider a diagram $D_Q: \Lambda \to \text{Mod}_Q(\Sigma_Q)$ in the quantum model category, where $D_Q(\lambda)$ is a quantum model (e.g., $|\psi_n\rangle\langle\psi_n|$ for $n$).
- Model morphisms in $\text{Mod}_Q(\Sigma_Q)$ (e.g., unitary evolution, symmetries) form the arrows of the diagram.
- Similarly, $D_C: \Lambda \to \text{Mod}_C(\Sigma_C)$ in the classical model category.

### 9.2. Functorial Translation and Institution Morphism
- Let $F: \text{Mod}_Q(\Sigma_Q) \to \text{Mod}_C(\Sigma_C)$ be a functor (e.g., classical limit, Wigner transform).
- The institution morphism's model component $\beta: \text{Mod}_C(\Phi\Sigma_Q) \to \text{Mod}_Q(\Sigma_Q)$ should be compatible with $F$ and the (co)limit construction.

### 9.3. (Co)limit Construction
- The colimit $\mathrm{colim}_{\Lambda} D_Q$ in $\text{Mod}_Q(\Sigma_Q)$ represents the universal quantum model emerging from the diagram (e.g., high-$n$ limit).
- The image diagram $F(D_Q): \Lambda \to \text{Mod}_C(\Sigma_C)$ translates quantum models to classical models.
- The colimit $\mathrm{colim}_{\Lambda} F(D_Q)$ in $\text{Mod}_C(\Sigma_C)$ is the emergent classical model.

### 9.4. Compatibility Condition
- The institution morphism $\beta$ should satisfy:
  $$
  \beta\left(\mathrm{colim}_{\Lambda} F(D_Q)\right) \cong \mathrm{colim}_{\Lambda} \beta \circ F(D_Q)
  $$
- This means that translating the colimit of classical models via $\beta$ yields the same result as taking the colimit of the translated models.
- In the quantum-classical case, this ensures that the classical limit of quantum models (via $F$) and the institution morphism $\beta$ commute with the colimit construction.

### 9.5. Explicit Example: Particle in a 1D Well
- **Diagram $D_Q$:** $n \mapsto |\psi_n\rangle\langle\psi_n|$ (quantum energy eigenstates)
- **Model morphisms:** Unitary time evolution $U_t$, symmetry transformations $S$
- **Functor $F$:** $F(|\psi_n\rangle\langle\psi_n|) = \mu_n$ (Wigner transform or classical limit)
- **Diagram $F(D_Q)$:** $n \mapsto \mu_n$ (classical microcanonical ensembles)
- **Colimit:** $\mathrm{colim}_{n \to \infty} \mu_n$ is the universal classical model for high energy
- **Institution morphism $\beta$:** $\beta(\mu_n) = |\psi_n\rangle\langle\psi_n|$ in the limit
- **Compatibility:**
  $$
  \beta\left(\mathrm{colim}_{n \to \infty} \mu_n\right) \cong \mathrm{colim}_{n \to \infty} \beta(\mu_n)
  $$
- This formalizes the idea that the process of taking the classical limit and translating models via institution morphisms is functorial and commutes with the (co)limit construction.

### 9.6. Generalization
- For any diagram of models and model morphisms relevant to theory-change, the institution morphism should be constructed so that it preserves (co)limits, ensuring universal properties and emergent models are correctly related across frameworks.
