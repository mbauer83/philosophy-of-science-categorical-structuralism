# Galilean–Newtonian Theory Change
### (Topos-Theoretic and Fibration-Based Example, Corrected and Fully Typed)

---

## 1. Syntactic Level

**Signatures.**
- Galilean theory: sorts \(\{X,T,V\}\), operations for addition, scalar mult., constant-velocity dynamics.
- Newtonian theory: adds sorts \(\{A,F,m\}\), axioms \(F=mA,\ A=dV/dT\).

**Syntactic functor.**
There is an inclusion of theories \(T:\mathcal S_{\mathrm G}\hookrightarrow \mathcal S_{\mathrm N}\) (forgetting acceleration/force).

---

## 2. Context Categories \(I_{\mathrm N}, I_{\mathrm G}\)

- **Objects:**
  - \(I_{\mathrm N}\): instrument setups \((R,a\text{-sensor})\) — reference frames with accelerometers.
  - \(I_{\mathrm G}\): instrument setups \((R)\) — frames with only velocity sensors.

- **Morphisms:**
  - In \(I_{\mathrm N}\): frame transformations (Galilean boosts) and calibration refinements.
  - In \(I_{\mathrm G}\): same but without acceleration instruments.

- **Base functor:**
  \[
  b:I_{\mathrm N}\longrightarrow I_{\mathrm G}
  \]
  forgets acceleration instruments: \(b(R,a\text{-sensor})=R\).

---

## 3. Model Fibrations

\[
p_{\mathrm N}:E_{\mathrm N}\to I_{\mathrm N},\qquad
p_{\mathrm G}:E_{\mathrm G}\to I_{\mathrm G}.
\]

- **Objects in \(E_{\mathrm N}\):**
  \((i=(R,a\text{-sensor}),M=(x(t),v(t),a(t),F(t)))\)
   satisfying \(F=m a,\ a=\dot v\).

- **Objects in \(E_{\mathrm G}\):**
  \((j=(R),M'=(x(t),v(t)))\) 
  with \(v(t)=\text{const}\).

- **Morphisms:**
  - In \(E_{\mathrm N}\): \((f:i'\to i,\ \alpha:M'\to f^*M)\) — pullback of trajectories under frame change.
  - In \(E_{\mathrm G}\): \((g:j'\to j,\ \beta:M'\to g^*M)\) — same for constant-velocity models.

---

## 4. Inter-Theory Functor \(F\)

\[
F:E_{\mathrm N}\longrightarrow E_{\mathrm G}
\]
covering \(b:I_{\mathrm N}\to I_{\mathrm G}\), i.e.
\[
p_{\mathrm G}\circ F = b\circ p_{\mathrm N}.
\]

**On objects.**
\[
F\big((R,a\text{-sensor}), (x,v,a,F,m)\big)
  = (b(R,a\text{-sensor}), (x,v)) = (R, (x,v)).
\]

**On morphisms.**
\[
F(f:i'\to i,\ \alpha:(x',v',a',F')\to f^*(x,v,a,F))
  = (b(f):b(i')\to b(i),\ \mathrm{forgetAccel}(\alpha):(x',v')\to b(f)^*(x,v)).
\]

\(F\) is **cartesian** over \(b\): for all \(f\),
\[
F(f^*M) \cong b(f)^*(F(M)).
\]

---

## 5. Empirical Domains and Interpretation Functors

Empirical categories:

- \(\mathrm{Emp}_{\mathrm N}\): measured triples \((x(t),v(t),a(t))\) with morphisms for time evolution and calibration.
- \(\mathrm{Emp}_{\mathrm G}\): measured pairs \((x(t),v(t))\).

Interpretation functors:
\[
J_{\mathrm N}:E_{\mathrm N}\to\mathrm{Emp}_{\mathrm N},\qquad
J_{\mathrm G}:E_{\mathrm G}\to\mathrm{Emp}_{\mathrm G}.
\]
Given by “reading off” predicted measurement data from models.

---

## 6. Data Coarsening and Natural Transformation

Define
\[
H:\mathrm{Emp}_{\mathrm N}\to\mathrm{Emp}_{\mathrm G}
\]
by \(H(x,v,a)=(x,v)\) — forget acceleration channel.

Then there is a **natural transformation**
\[
\eta: J_{\mathrm G}\circ F \;\Rightarrow\; H\circ J_{\mathrm N}.
\]
For each \((i,M)\in E_{\mathrm N}\),
\[
\eta_{(i,M)} : J_{\mathrm G}(F(i,M)) \longrightarrow H(J_{\mathrm N}(i,M))
\]
is the identity in \(\mathrm{Emp}_{\mathrm G}\); it asserts empirical equivalence of predictions for position and velocity once acceleration is ignored.

---

## 7. Correct Squares

### (a) Base-covering fibration square
\[
\begin{array}{ccc}
E_{\mathrm N} & \xrightarrow{\,F\,} & E_{\mathrm G} \\
\downarrow^{p_{\mathrm N}} & & \downarrow^{p_{\mathrm G}} \\
I_{\mathrm N} & \xrightarrow{\,b\,} & I_{\mathrm G}
\end{array}
\]

### (b) Interpretation square with natural transformation
\[
\begin{array}{ccc}
E_{\mathrm N} & \xrightarrow{\,F\,} & E_{\mathrm G} \\
\Big\downarrow^{J_{\mathrm N}} & \overset{\eta}{\Rightarrow} & \Big\downarrow^{J_{\mathrm G}} \\
\mathrm{Emp}_{\mathrm N} & \xrightarrow{\,H\,} & \mathrm{Emp}_{\mathrm G}
\end{array}
\]

Both are strictly type-consistent.

---

## 8. Limit / Degenerate Case

Consider a filtered diagram \(D_a:E_{\mathrm N}\to E_{\mathrm G}\) varying acceleration magnitude \(a\to0\).  
Then
\[
\mathrm{colim}_{a\to0}F_a(i,M) = (b(i), M_0)
\]
where \(M_0=(x(t),v_0)\) with \(v_0\) constant.

Empirical commutation:
\[
J_{\mathrm G}\!\big(\mathrm{colim}_{a\to0}F_a(i,M)\big)
  = \mathrm{colim}_{a\to0} H(J_{\mathrm N}(i,M)).
\]
This expresses that Galilean empirical predictions are the limit of Newtonian ones as \(a\to0\).

---
# ✅ End of Galilean–Newtonian Example
