# Part B 第1問 (7) 自己エネルギー・質量再規格化・量子力学エネルギーシフトの深層解説報告書

本ドキュメントは、`Kokin_Cho_QFT_term_paper.tex` の Part B 第1問 (7) における **自己エネルギー $\Sigma(p)$ の導出、質量再規格化 $m^2 = m_0^2 + \Sigma$、および質量が「上向き（Renormalized UP）」に再規格化される量子力学的・場論的物理機構** について、基礎から深層まで網羅的に解説したものです。

---

## 1. 自己エネルギー $\Sigma(p)$ と Dyson 方程式の数学的導出

### 1.1. Dyson 方程式の幾何級数表現
場の量子論において、相互作用を受けるフル 2点伝播関数 $G^{(2)}(p)$ は、自由伝播関数 $G_0(p)$ に 1粒子既約 (1PI) な自己エネルギーブロック $\Sigma(p)$ が $0, 1, 2, \dots$ 回挿入された全ダイアグラムの和として表現されます。

$$G^{(2)}(p) = G_0(p) - G_0(p)\Sigma(p)G_0(p) + G_0(p)\Sigma(p)G_0(p)\Sigma(p)G_0(p) - \dots$$

これを初項 $G_0(p)$、公比 $-G_0(p)\Sigma(p)$ の無限等比級数として和をとると：

$$G^{(2)}(p) = \frac{G_0(p)}{1 + G_0(p)\Sigma(p)}$$

両辺の逆数を取ると、有名な **Dyson 方程式 (Dyson Equation)** が得られます：

$$[G^{(2)}(p)]^{-1} = [G_0(p)]^{-1} + \Sigma(p)$$

Euclidean 時空における自由伝播関数は $[G_0(p)]^{-1} = p^2 + m_0^2$ であるため：

$$[G^{(2)}(p)]^{-1} = p^2 + m_0^2 + \Sigma(p)$$

---

### 1.2. 1次摂動 ($\mathcal{O}(\lambda^1)$) における自己エネルギーの決定
設問 (6) で求めた 1次までの 2点関数は：

$$G^{(2)}(p) = G_0(p) - 4\lambda [G_0(p)]^2 G_0(0) + \mathcal{O}(\lambda^2) = G_0(p) \left[ 1 - 4\lambda G_0(p) G_0(0) \right]$$

この逆数を 1次までテイラー展開 ($(1 - x)^{-1} \approx 1 + x$) すると：

$$[G^{(2)}(p)]^{-1} = [G_0(p)]^{-1} \left[ 1 - 4\lambda G_0(p) G_0(0) \right]^{-1} \approx [G_0(p)]^{-1} \left[ 1 + 4\lambda G_0(p) G_0(0) \right] = [G_0(p)]^{-1} + 4\lambda G_0(0)$$

Dyson 方程式 $[G^{(2)}(p)]^{-1} = [G_0(p)]^{-1} + \Sigma(p)$ と比較することにより、1次の自己エネルギーが**運動量に依存しない定数**として一義的に決まります：

$$\Sigma(p) = 4\lambda G_0(0) = 4\lambda \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2}$$

---

## 2. 物理的質量（Renormalized Mass）の定義と再規格化の向き

### 2.1. 極（Pole）による物理的質量の定義
運動量空間において、物理的（再規格化）質量 $m$ は**フル伝播関数 $G^{(2)}(p)$ の極の位置**として定義されます。

$$[G^{(2)}(p)]^{-1} \Big|_{p^2 = -m^2} = 0 \quad (\text{Euclidean では } p^2 + m^2 = 0 \text{ の形})$$

したがって：

$$p^2 + m^2 = p^2 + m_0^2 + \Sigma(p) \implies m^2 = m_0^2 + \Sigma$$

1次の自己エネルギーを代入すると：

$$m^2 = m_0^2 + 4\lambda \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2}$$

---

### 2.2. 質量は UP か DOWN か？
- **ループ積分の符号**: Euclidean 運動量空間での積分被関数 $\frac{1}{k^2 + m_0^2}$ は、すべての運動量 $k$ について正（$> 0$）です。
- **結合定数**: 理論の安定性から $\lambda > 0$（正の結合定数）。

したがって、自己エネルギー寄与は**厳密に正 (strictly positive)** です：

$$\Sigma = 4\lambda \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2} > 0$$

これにより：

$$m^2 > m_0^2 \implies m > m_0$$

結論として、粒子質量は **上向きに再規格化される（Renormalized UP）** ことが示されます。

---

## 3. 物理的解釈（直感とヒントの完全解説）

問題文のヒント：「量子力学におけるエネルギー準位のシフトを考えよ (Hint: think of the shift of the energy levels in quantum mechanics)」に対する深い回答です。

### 解釈 1: 量子力学の 1次摂動論におけるエネルギーシフト
量子力学において、ハミルトニアン $H = H_0 + V$ を考えます。未摂動の基底状態 $|n\rangle$ のエネルギー $E_n^{(0)}$ に対し、1次摂動によるエネルギーシフトは：

$$\Delta E_n = \langle n | V | n \rangle$$

もし摂動ポテンシャル $V(x)$ が空間全体で**正定値（Positive-definite, $V(x) > 0$）** であれば、行列要素は必ず正となり、**エネルギー準位は常に上向き（UP）にシフト ($\Delta E_n > 0$)** します。

本問題の複素スカラー場理論における相互作用ハミルトニアン密度は：

$$\mathcal{H}_{\text{int}} = +\lambda (\phi^* \phi)^2 > 0$$

であり、完全に正定値です。場の量子論において、単一粒子状態の静止エネルギーはまさにその粒子質量 $E = m$（$c=1$）に相当するため、**正定値なポテンシャルの存在によって一粒子状態のエネルギー（質量）が上向きにシフトする** のは、量子力学の 1次摂動論の直接的な帰結です。

---

### 解釈 2: 仮想粒子クラウド（Virtual Particle Cloud）と慣性の増加
場の量子論的な描像では：
1. 裸の粒子（Bare particle, 質量 $m_0$）は孤立して存在するのではなく、相互作用 $\lambda(\phi^*\phi)^2$ を通じて自身の周りに仮想粒子・反粒子のペアを絶えず放出しては再吸収する「自セルフループ（タドポール）」を形成しています。
2. その結果、物理的な粒子は自らが生成した**「仮想粒子の雲（Virtual particle cloud）」を身に纏った状態（Dressed particle）** となります。
3. この粒子を加速（運動）させようとすると、周囲の仮想粒子クラウドの場も一緒に励起・移動させる必要があるため、**物体の運動に対する抵抗＝実効的な慣性（Inertia）が増大** します。
4. アインシュタインの等価性 $E = mc^2$ より、慣性の増大は物理的質量 $m$ の増加（Renormalized UP）として観測されます。

---

## 4. TeX レポートでの推奨記述（改訂案）

`Kokin_Cho_QFT_term_paper.tex` の Part B Q1 (7) の解答枠を、以下の洗練された英文テキストに更新することで、完璧なレポートが完成します：

```latex
\begin{proofbox}
The self-energy $\Sigma(p)$ represents the sum of all 1PI 2-point insertion diagrams and is defined via the Dyson equation for the full propagator $G^{(2)}(p)$:
\[
[G^{(2)}(p)]^{-1} = [G_0(p)]^{-1} + \Sigma(p).
\]
From the first-order calculation in part (6), the full 2-point function is $G^{(2)}(p) = G_0(p) - 4\lambda G_0(p)^2 G_0(0) + \mathcal{O}(\lambda^2)$. Inverting this expansion via $(1 - x)^{-1} \approx 1 + x$:
\[
[G^{(2)}(p)]^{-1} = [G_0(p)]^{-1} \left( 1 - 4\lambda G_0(p) G_0(0) \right)^{-1} \approx [G_0(p)]^{-1} + 4\lambda G_0(0).
\]
Matching this with Dyson's equation yields the momentum-independent 1st-order self-energy:
\[
\Sigma(p) = 4\lambda G_0(0) = 4\lambda \int \frac{\dd^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2}.
\]
The physical (renormalized) mass $m$ corresponds to the pole of the full propagator in momentum space, defined by $[G^{(2)}(p)]^{-1}|_{p^2 = -m^2} = 0$:
\[
p^2 + m^2 = p^2 + m_0^2 + \Sigma(p) \implies m^2 = m_0^2 + 4\lambda \int \frac{\dd^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2}.
\]
Since the Euclidean integrand $\frac{1}{k^2 + m_0^2} > 0$ and the coupling constant $\lambda > 0$, the self-energy correction is strictly positive ($\Sigma > 0$). Consequently, $m^2 > m_0^2$, establishing that the mass is renormalized **up** ($m > m_0$).

\paragraph{Physical Explanation and Quantum Mechanical Analogy:}
This upward mass shift can be understood intuitively from two complementary perspectives:
\begin{enumerate}
    \item \textbf{Quantum Mechanical Energy Shift}: In standard quantum mechanics, adding a positive-definite perturbation potential $V(x) > 0$ to a system shifts the unperturbed energy levels upwards by $\Delta E = \langle 0 | V | 0 \rangle > 0$ in first-order perturbation theory. In our field theory, the interaction Hamiltonian density $\mathcal{H}_{\mathrm{int}} = +\lambda (\phi^*\phi)^2 > 0$ is positive-definite. Because the rest energy of a single-particle state corresponds to its physical mass $E = m$, this positive interaction potential naturally shifts the single-particle energy level (rest mass) upwards.
    \item \textbf{Virtual Particle Cloud (Dressing) and Inertia}: In quantum field theory, a bare particle continuously emits and reabsorbs virtual particles via the self-interaction loop (tadpole), surrounding itself with a "virtual particle cloud." When an external force accelerates the physical (dressed) particle, this cloud must be accelerated along with it, increasing the effective resistance to motion—that is, increasing its physical inertia, which directly corresponds to an increased renormalized mass $m > m_0$.
\end{enumerate}
\end{proofbox}
```
