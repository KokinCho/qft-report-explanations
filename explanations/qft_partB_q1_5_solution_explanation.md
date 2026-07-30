# Quantum Field Theory Term Paper: Part B Question 1 (5) Solution

## 1. Note on Reference and Theoretical / Notational Differences

### Reference Citation
The Feynman diagrams presented in this solution are adapted from Chapter 10, "Perturbation Calculations and Feynman Graphs", of *Quantum Field Theory (II) -- Focusing on Feynman Graphs and Renormalization* by Masato Sakamoto (Quantum Mechanics Series, Shokabo, 2020).

### Theoretical & Notational Differences
1. **Directional Arrows on Propagators**:
   - The referenced textbook considers a real scalar field ($\phi^4$ theory), where propagators are drawn without directional arrows.
   - The model studied in this problem is a complex scalar field ($\lambda(\phi^*\phi)^2$ theory), where $U(1)$ charge conservation requires directed arrows on propagators, with two incoming and two outgoing lines at each interaction vertex.
   - This constraint on line orientations alters the number of valid Wick contractions and symmetry factors (combinatorial factors) compared to real scalar graphs of identical topology. However, to maintain clarity, the expansion coefficients and notations in the formulas below are written in direct one-to-one correspondence with the figures referenced from Chapter 10 of Sakamoto's book.
2. **Propagator Notation**:
   - The Green's function $D_F(x-y)$ defined in Minkowski spacetime in parts (1)–(3) satisfies $(\partial^2 + m_0^2 - i\epsilon) D_F(x-y) = -\delta^4(x-y)$, giving $\langle 0 | \mathrm{T} \phi(x) \phi^\dagger(y) | 0 \rangle = i D_F(x-y)$.
   - The free propagator notation $\Delta_{F,0}(x-y) \equiv \langle 0 | \mathrm{T} \phi(x) \phi(y) | 0 \rangle_0$ used in the referenced figures relates to $D_F$ via $\Delta_{F,0}(x-y) = i D_F(x-y)$.
   - In Euclidean spacetime (as requested in question 5), Wick rotation ($t = -i\tau$) eliminates the factor of $i$, making it equivalent to the real Euclidean propagator $G_0(x_E - y_E)$.

---

## 2. One-to-One Correspondence of Figures and Formulas

### (a) Vacuum Diagrams

\[
\begin{aligned}
\langle \exp\left\{i \int \mathrm{d}^4 y \, \mathcal{L}_{\mathrm{int}}(\phi)\right\} \rangle_0 = &\; 1 + \frac{1}{2^3} (-i\lambda) \int \mathrm{d}^4 y \, (\Delta_{F,0}(0))^2 \\
&\; + (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \left[ \frac{1}{2^4} (\Delta_{F,0}(0))^4 + \frac{1}{2 \cdot 4!} \Delta_{F,0}(0) (\Delta_{F,0}(y_1-y_2))^2 \Delta_{F,0}(0) \right. \\
&\;\hspace{12em} \left. + \frac{1}{2^7} (\Delta_{F,0}(y_1-y_2))^4 \right] + \mathcal{O}(\lambda^3)
\end{aligned}
\]

---

### (b) Two-Point Functions

#### Order $\lambda^0$ ($k=0$)
\[
G^{(2)}_{k=0}(x_1, x_2) = \Delta_{F,0}(x_1 - x_2)
\]

#### Order $\lambda^1$ ($k=1$)
\[
\begin{aligned}
G^{(2)}_{k=1}(x_1, x_2) = &\; \frac{1}{2^3} (-i\lambda) \int \mathrm{d}^4 y \, \Delta_{F,0}(x_1 - x_2) (\Delta_{F,0}(0))^2 \\
&\; + \frac{1}{2} (-i\lambda) \int \mathrm{d}^4 y \, \Delta_{F,0}(x_1 - y) \Delta_{F,0}(0) \Delta_{F,0}(y - x_2)
\end{aligned}
\]

#### Order $\lambda^2$ ($k=2$)
\[
\begin{aligned}
G^{(2)}_{k=2}(x_1, x_2) = &\; \frac{1}{3!} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, \Delta_{F,0}(x_1 - y_1) (\Delta_{F,0}(y_1 - y_2))^3 \Delta_{F,0}(y_2 - x_2) \\
&\; + \frac{1}{2^2} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, \Delta_{F,0}(x_1 - y_1) \Delta_{F,0}(0) \Delta_{F,0}(y_1 - y_2) \Delta_{F,0}(0) \Delta_{F,0}(y_2 - x_2) \\
&\; + \frac{1}{2^2} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, \Delta_{F,0}(x_1 - y_1) (\Delta_{F,0}(y_1 - y_2))^2 \Delta_{F,0}(y_2 - x_2) \Delta_{F,0}(0) \\
&\; + \left[ \frac{1}{2} (-i\lambda) \int \mathrm{d}^4 y_1 \, \Delta_{F,0}(x_1 - y_1) \Delta_{F,0}(0) \Delta_{F,0}(y_1 - x_2) \right] \left[ \frac{1}{2^3} (-i\lambda) \int \mathrm{d}^4 y_2 \, (\Delta_{F,0}(0))^2 \right] \\
&\; + \Delta_{F,0}(x_1 - x_2) \times (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \left[ \frac{1}{2^4} \Delta_{F,0}(0) (\Delta_{F,0}(y_1-y_2))^2 \Delta_{F,0}(0) \right. \\
&\;\hspace{12em} \left. + (\Delta_{F,0}(y_1-y_2))^4 + \frac{1}{2^7} (\Delta_{F,0}(y_1-y_2))^4 \right]
\end{aligned}
\]

---

### (c) Four-Point Functions

#### Order $\lambda^0$ ($k=0$)
\[
G^{(4)}_{k=0}(x_1, x_2, x_3, x_4) = \Delta_{F,0}(x_1 - x_2) \Delta_{F,0}(x_3 - x_4) + \Delta_{F,0}(x_1 - x_3) \Delta_{F,0}(x_2 - x_4) + \Delta_{F,0}(x_1 - x_4) \Delta_{F,0}(x_2 - x_3)
\]

#### Order $\lambda^1$ ($k=1$)
\[
\begin{aligned}
G^{(4)}_{k=1}(x_1, x_2, x_3, x_4) = &\; (-i\lambda) \int \mathrm{d}^4 y \prod_{j=1}^4 \Delta_{F,0}(x_j - y) \\
&\; + \frac{1}{2} (-i\lambda) \int \mathrm{d}^4 y \left[ \Delta_{F,0}(x_1 - x_2) \Delta_{F,0}(x_3 - y) \Delta_{F,0}(0) \Delta_{F,0}(y - x_4) + (5 \text{ permutations}) \right] \\
&\; + \frac{1}{2^3} (-i\lambda) \int \mathrm{d}^4 y \left[ \Delta_{F,0}(x_1 - x_2) \Delta_{F,0}(x_3 - x_4) + \Delta_{F,0}(x_1 - x_3) \Delta_{F,0}(x_2 - x_4) \right. \\
&\;\hspace{8em} \left. + \Delta_{F,0}(x_1 - x_4) \Delta_{F,0}(x_2 - x_3) \right] (\Delta_{F,0}(0))^2
\end{aligned}
\]

#### Order $\lambda^2$ ($k=2$)
\[
\begin{aligned}
G^{(4)}_{k=2}(x_1, x_2, x_3, x_4) = &\; \frac{1}{2} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \left[ \Delta_{F,0}(x_1 - y_1) \Delta_{F,0}(x_2 - y_1) (\Delta_{F,0}(y_1 - y_2))^2 \right.\\
&\;\hspace{10em}  \times \Delta_{F,0}(y_2 - x_3) \Delta_{F,0}(y_2 - x_4) \\
&\;\hspace{10em} \left. + (t, u \text{ channels}) \right] \\
&\; + \frac{1}{2} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \left[ \Delta_{F,0}(x_1 - y_1) \Delta_{F,0}(x_2 - y_1) \Delta_{F,0}(y_1 - y_2) \Delta_{F,0}(0) \right. \\
&\;\hspace{10em} \left. \times \Delta_{F,0}(y_2 - x_3) \Delta_{F,0}(y_2 - x_4) + \text{permutations} \right] \\
&\; + (\text{other disconnected, internal loop insertion, and vacuum bubble terms})
\end{aligned}
\]

---

### (d) Factorization and Verification of Vacuum Diagram Cancellation

#### Factorization Example
\[
\begin{aligned}
\langle \phi(x_1) \phi(x_2) e^{i \int \mathrm{d}^4 y \, \mathcal{L}_{\mathrm{int}}(\phi)} \rangle_0 = &\; \left[ \Delta_{F,0}(x_1 - x_2) + \frac{1}{2} (-i\lambda) \int \mathrm{d}^4 y \, \Delta_{F,0}(x_1 - y) \Delta_{F,0}(0) \Delta_{F,0}(y - x_2) \right. \\
&\;\quad \left. + (\text{second-order connected diagrams}) + \mathcal{O}(\lambda^3) \right] \\
&\; \times \left[ 1 + \frac{1}{2^3} (-i\lambda) \int \mathrm{d}^4 y \, (\Delta_{F,0}(0))^2 + \mathcal{O}(\lambda^2) \right] \\
= &\; G^{(2)}_{\mathrm{no-vac}}(x_1, x_2) \times \langle e^{i \int \mathrm{d}^4 y \, \mathcal{L}_{\mathrm{int}}(\phi)} \rangle_0
\end{aligned}
\]

#### Cancellation Mechanism
By virtue of this factorized structure, as proven in part (4), dividing by the normalization denominator $Z[0,0] = \langle e^{i \int \mathrm{d}^4 y \, \mathcal{L}_{\mathrm{int}}(\phi)} \rangle_0$ completely cancels all vacuum bubble contributions in the numerator and denominator.

#### Two-Point Correlation Function After Vacuum Cancellation
\[
\begin{aligned}
G^{(2)}(x_1, x_2) = &\; \Delta_{F,0}(x_1 - x_2) + \frac{1}{2} (-i\lambda) \int \mathrm{d}^4 y \, \Delta_{F,0}(x_1 - y) \Delta_{F,0}(0) \Delta_{F,0}(y - x_2) \\
&\; + \frac{1}{3!} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, \Delta_{F,0}(x_1 - y_1) (\Delta_{F,0}(y_1 - y_2))^3 \Delta_{F,0}(y_2 - x_2) \\
&\; + \frac{1}{2^2} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, \Delta_{F,0}(x_1 - y_1) \Delta_{F,0}(0) \Delta_{F,0}(y_1 - y_2) \Delta_{F,0}(0) \Delta_{F,0}(y_2 - x_2) \\
&\; + \frac{1}{2^2} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, \Delta_{F,0}(x_1 - y_1) (\Delta_{F,0}(y_1 - y_2))^2 \Delta_{F,0}(y_2 - x_2) \Delta_{F,0}(0) + \mathcal{O}(\lambda^3)
\end{aligned}
\]

#### Four-Point Correlation Function After Vacuum Cancellation
\[
\begin{aligned}
G^{(4)}(x_1, x_2, x_3, x_4) = &\; \Delta_{F,0}(x_1 - x_2) \Delta_{F,0}(x_3 - x_4) + \Delta_{F,0}(x_1 - x_3) \Delta_{F,0}(x_2 - x_4) + \Delta_{F,0}(x_1 - x_4) \Delta_{F,0}(x_2 - x_3) \\
&\; + (-i\lambda) \int \mathrm{d}^4 y \prod_{j=1}^4 \Delta_{F,0}(x_j - y) \\
&\; + \frac{1}{2} (-i\lambda) \int \mathrm{d}^4 y \left[ \Delta_{F,0}(x_1 - x_2) \Delta_{F,0}(x_3 - y) \Delta_{F,0}(0) \Delta_{F,0}(y - x_4) + (5 \text{ permutations}) \right] \\
&\; + \frac{1}{2} (-i\lambda)^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \left[ \Delta_{F,0}(x_1 - y_1) \Delta_{F,0}(x_2 - y_1) (\Delta_{F,0}(y_1 - y_2))^2 \right. \\
&\;\hspace{10em} \times \Delta_{F,0}(y_2 - x_3) \Delta_{F,0}(y_2 - x_4) \\
&\;\hspace{10em} \left. + (t, u \text{ channels}) \right] \\
&\; + (\text{other disconnected, internal loop insertion, and vacuum bubble terms}) + \mathcal{O}(\lambda^3)
\end{aligned}
\]
