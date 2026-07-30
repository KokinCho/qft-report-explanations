# 相互作用場における生成汎関数 $Z[J, J^*]$ の微分演算子表現の完全導出

## 1. 定義と問題設定

自由場に相互作用項 $\mathcal{L}_{\text{int}} = -\lambda (\phi^* \phi)^2$ が追加されたフル理論の経路積分表示（生成汎関数）は以下のように定義されます：

$$
Z[J, J^*] = \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \mathcal{D}\phi^* \exp\left\{ i \int \mathrm{d}^4 x \left[ \mathcal{L}_0(\phi, \phi^*) - \lambda (\phi^* \phi)^2 + J^*\phi + J\phi^* \right] \right\}
$$

目的は、この汎関数積分内にある相互作用項 $\exp\left( -i \int \mathrm{d}^4x \lambda (\phi^*\phi)^2 \right)$ を、微分演算子の形にして積分の**外側に完全に引き出す**公式：

$$
Z[J, J^*] = \exp\left\{ -i \int \mathrm{d}^4 x \lambda \left( \frac{\delta}{i\delta J(x)} \frac{\delta}{i\delta J^*(x)} \right)^2 \right\} Z_0[J, J^*]
$$

を1つの行間もなくステップバイステップで証明することです。

---

## 2. 行間を埋めるステップバイステップ導出

### Step 1: 被積分関数の指数関数の分離

> **【重要な概念的補足: なぜ BCH 公式なしで $e^{A+B} = e^A e^B$ と展開できるのか？】**  
> - **演算子形式（q-number）**: 場の演算子 $\hat{\phi}(\mathbf{x}), \hat{\pi}(\mathbf{y})$ やハミルトニアン演算子 $\hat{H}$ は互いに非可換（$[\hat{\phi}, \hat{\pi}] = i \delta^3$）であるため、演算子 $e^{\hat{A}+\hat{B}}$ を分離する際には Baker-Campbell-Hausdorff (BCH) 公式や時間順序積演算子 $T$ の導入が不可欠です。
> - **経路積分形式（c-number）**: 一方で、**経路積分 $\int \mathcal{D}\phi$ の中において、場 $\phi(x)$ や $\phi^*(x)$ は演算子ではなく単なる「c-number の古典的関数（数）」** です！ 時空の全点において $\phi(x) \phi(y) = \phi(y) \phi(x)$ と可換であるため、作用の項 $A = -i \int \lambda (\phi^* \phi)^2$ と $B = i S_0 + i \int (J^*\phi + J\phi^*)$ は完全な複素数（c-number）です。
> - したがって、**経路積分の被積分関数の中では通常の指数法則 $e^{A+B} = e^A e^B$ が BCH 公式一切なしで厳密に成立します**。演算子の非可換性に由来する時間順序積 $T$ の効果は、全配置にわたる汎関数積分を実行した結果として自動的に出現する仕組みになっています。

指数法則 $e^{A+B} = e^A e^B$ を用いて、被積分関数を「相互作用項」と「自由場＋外源の項」に分離します：

$$
Z[J, J^*] = \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \mathcal{D}\phi^* \underbrace{\exp\left\{ -i \int \mathrm{d}^4x \lambda (\phi^*(x)\phi(x))^2 \right\}}_{\text{相互作用項}} \underbrace{\exp\left\{ i S_0[\phi, \phi^*] + i \int \mathrm{d}^4x (J^*\phi + J\phi^*) \right\}}_{\text{自由場項＋源の結合}}
$$

ここで $S_0[\phi, \phi^*] = \int \mathrm{d}^4x \mathcal{L}_0(\phi, \phi^*)$ です。

---

### Step 2: 源の項の汎関数微分による場の抽出

源の結合項 $E[J, J^*] \equiv \exp\left\{ i \int \mathrm{d}^4y (J^*(y)\phi(y) + J(y)\phi^*(y)) \right\}$ を外源 $J^*(x)$ および $J(x)$ でそれぞれ汎関数微分します。

1. **$J^*(x)$ での汎関数微分**:
   $$
   \frac{\delta}{\delta J^*(x)} \exp\left\{ i \int \mathrm{d}^4y (J^*(y)\phi(y) + J(y)\phi^*(y)) \right\} = i \phi(x) \exp\left\{ i \int \mathrm{d}^4y (J^*\phi + J\phi^*) \right\}
   $$
   両辺を $i$ で割る（$-i$ を掛ける）と：
   $$
   \phi(x) E[J, J^*] = \frac{\delta}{i \delta J^*(x)} E[J, J^*]
   $$

2. **$J(x)$ での汎関数微分**:
   $$
   \frac{\delta}{\delta J(x)} \exp\left\{ i \int \mathrm{d}^4y (J^*(y)\phi(y) + J(y)\phi^*(y)) \right\} = i \phi^*(x) \exp\left\{ i \int \mathrm{d}^4y (J^*\phi + J\phi^*) \right\}
   $$
   同様に両辺を $i$ で割ると：
   $$
   \phi^*(x) E[J, J^*] = \frac{\delta}{i \delta J(x)} E[J, J^*]
   $$

自由場の作用 $S_0[\phi, \phi^*]$ は外源 $J, J^*$ に依存しないため、上記の微分演算子は自由場項も含めた全因子 $\exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\}$ に作用させても全く同じ結果を与えます：

$$
\phi(x) \exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\} = \frac{\delta}{i \delta J^*(x)} \exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\}
$$

$$
\phi^*(x) \exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\} = \frac{\delta}{i \delta J(x)} \exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\}
$$

---

### Step 3: 任意の多項式・関数の演算子置換法則

これを繰り返すことで、場 $\phi(x)$ や $\phi^*(x)$ の高重積（およびその Taylor 展開である任意の汎関数 $\mathcal{F}[\phi, \phi^*]$）について、以下の置換公式が成り立ちます：

$$
\mathcal{F}[\phi, \phi^*] \exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\} = \mathcal{F}\left[ \frac{\delta}{i\delta J^*}, \frac{\delta}{i\delta J} \right] \exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\}
$$

特に、相互作用の単位量 $\phi^*(x) \phi(x)$ については：

$$
\phi^*(x) \phi(x) \longleftrightarrow \left( \frac{\delta}{i \delta J(x)} \right) \left( \frac{\delta}{i \delta J^*(x)} \right)
$$

となり、その2乗 $(\phi^*(x) \phi(x))^2$ は：

$$
(\phi^*(x) \phi(x))^2 \longleftrightarrow \left( \frac{\delta}{i \delta J(x)} \frac{\delta}{i \delta J^*(x)} \right)^2
$$

と置き換わります。

---

### Step 4: 演算子の汎関数積分の外への繰り出し

Step 3 の置換法則を Step 1 の相互作用汎関数 $\mathcal{F}[\phi, \phi^*] = \exp\left\{ -i \int \mathrm{d}^4x \lambda (\phi^*(x)\phi(x))^2 \right\}$ に適用すると：

$$
\begin{aligned}
Z[J, J^*] &= \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \mathcal{D}\phi^* \left[ \exp\left\{ -i \int \mathrm{d}^4x \lambda (\phi^*(x)\phi(x))^2 \right\} \exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\} \right] \\
&= \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \mathcal{D}\phi^* \left[ \exp\left\{ -i \int \mathrm{d}^4x \lambda \left( \frac{\delta}{i\delta J(x)} \frac{\delta}{i\delta J^*(x)} \right)^2 \right\} \exp\left\{ i S_0 + i \int (J^*\phi + J\phi^*) \right\} \right]
\end{aligned}
$$

ここで重要なのは、**微分演算子 $\exp\left\{ -i \int \mathrm{d}^4x \lambda \left( \frac{\delta}{i\delta J(x)} \frac{\delta}{i\delta J^*(x)} \right)^2 \right\}$ は $J, J^*$ に関する微分であり、積分の変数である場 $\phi, \phi^*$ には一切依存していない**ということです。

したがって、線形演算子として汎関数積分 $\int \mathcal{D}\phi \mathcal{D}\phi^*$ の**外側に完全に引き出す**ことができます：

$$
Z[J, J^*] = \exp\left\{ -i \int \mathrm{d}^4x \lambda \left( \frac{\delta}{i\delta J(x)} \frac{\delta}{i\delta J^*(x)} \right)^2 \right\} \underbrace{\left( \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \mathcal{D}\phi^* \exp\left\{ i S_0[\phi, \phi^*] + i \int \mathrm{d}^4x (J^*\phi + J\phi^*) \right\} \right)}_{= Z_0[J, J^*]}
$$

括弧内の経路積分は、まさに自由場の生成汎関数 $Z_0[J, J^*]$ そのものです！
これにより、所望の公式が得られます：

$$
Z[J, J^*] = \exp\left\{ -i \int \mathrm{d}^4 x \lambda \left( \frac{\delta}{i\delta J(x)} \frac{\delta}{i\delta J^*(x)} \right)^2 \right\} Z_0[J, J^*]
$$

---

## 3. ユークリッド時空への拡張（Wick 回転）

ユークリッド時空（$x^0 = -i x_E^4, \tau = i t$）では、作用の位相ファクターが $i S_M \to - S_E$ に変化し、源の微分は $\frac{\delta}{i\delta J} \to \frac{\delta}{\delta J_E}$ となります。

ユークリッド相互作用作用は $S_{E, \text{int}} = \int \mathrm{d}^4x_E \lambda (\phi_E^* \phi_E)^2$ であるため、まったく同様の微分演算子の引き出しにより：

$$
Z_E[J, J^*] = \exp\left\{ - \int \mathrm{d}^4 x_E \lambda \left( \frac{\delta}{\delta J(x_E)} \frac{\delta}{\delta J^*(x_E)} \right)^2 \right\} Z_{0,E}[J, J^*]
$$

が得られます。この公式を $\lambda$ について Taylor 展開することが、摂動論における**ファインマン・ダイアグラム（Feynman rules）の組合せ論的導出**の出発点となります。
