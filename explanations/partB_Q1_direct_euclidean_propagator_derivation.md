# ウィック回転を使わないユークリッド伝播関数の直接導出ガイド

本ドキュメントは、**「ミンコフスキー空間からの Wick 回転（後からの解析接続）を使わずに、最初からユークリッド空間（Euclidean space）で理論を定義して伝播関数 $G_0^E(p_E) = \frac{1}{p_E^2 + m_0^2}$ を直接求める 3 つのアプローチ」** について解説した特別ガイドです。

---

## 1. なぜ Wick 回転なしで直接求められるのか？

ミンコフスキー空間とユークリッド空間では、支配する微分演算子の数学的性質が本質的に異なります：

* **ミンコフスキー空間**:
  ダランベルシアン $\square = \frac{\partial^2}{\partial t^2} - \nabla^2$ は **双曲型演算子 (Hyperbolic Operator)** です。
  極が実軸上に乗るため、そのままでは逆演算子が存在せず、極を上下のどちらに避けるかという **$i\epsilon$ 処方（境界条件）** が必要になります。
* **ユークリッド空間**:
  ユークリッド・ラプラシアン $\Delta_E = \frac{\partial^2}{\partial x_4^2} + \nabla^2$ に基づく演算子 **$(-\Delta_E + m_0^2)$ は 楕円型演算子 (Elliptic Operator)** であり、**厳密に正定値 (Positive-definite)** です。

したがって、ユークリッド空間では最初から極（Poles）が実軸上に存在せず、**$i\epsilon$ も Wick 回転も一切使わずにグリーン関数（伝播関数）が一義的に直接求まります。**

---

## 2. 直接導出の 3 つのアプローチ

### アプローチ 1: グリーン関数方程式（偏微分方程式）からの直接解法
4次元ユークリッド空間 $\mathbb{R}^4$ （座標 $x_E = (x_1, x_2, x_3, x_4)$）において、自由スカラー場の作用は：

$$S_E[\phi] = \int \mathrm{d}^4 x_E \left[ \frac{1}{2} (\partial \phi)^2 + \frac{1}{2} m_0^2 \phi^2 \right] = \frac{1}{2} \int \mathrm{d}^4 x_E \, \phi(x_E) (-\Delta_E + m_0^2) \phi(x_E)$$

ユークリッド自由伝播関数 $G_0^E(x_E - y_E)$ は、この演算子 $(-\Delta_E + m_0^2)$ の Green 関数として直接定義されます：

$$(-\Delta_E + m_0^2) G_0^E(x_E - y_E) = \delta^4(x_E - y_E)$$

この両辺を 4 次元ユークリッド運動量空間 $p_E = (p_1, p_2, p_3, p_4)$ でフーリエ変換します：

* 作用素の変換: $-\Delta_E \xrightarrow{\text{Fourier}} p_E^2 = p_1^2 + p_2^2 + p_3^2 + p_4^2$
* デルタ関数の変換: $\delta^4(x_E - y_E) \xrightarrow{\text{Fourier}} 1$

代入すると：

$$(p_E^2 + m_0^2) \tilde{G}_0^E(p_E) = 1 \implies \mathbf{\tilde{G}_0^E(p_E) = \frac{1}{p_E^2 + m_0^2}}$$

> **ポイント**: $p_E^2 \ge 0$ かつ $m_0^2 > 0$ であるため、$p_E^2 + m_0^2 \ge m_0^2 > 0$ となり、分母がゼロになる「極」が全運動量空間で一度も発生しません。

---

### アプローチ 2: ユークリッド経路積分（ガウス積分）からの直接導出
ユークリッド場論における自由場の生成汎関数は、4次元統計力学のガウス型分配関数そのものです：

$$Z_0[J] = \int \mathcal{D}\phi \exp\left( -\int \mathrm{d}^4 x_E \left[ \frac{1}{2} \phi (-\Delta_E + m_0^2) \phi - J\phi \right] \right)$$

一般の有限次元ガウス積分公式 $\int \mathrm{d}^N x \, e^{-\frac{1}{2} x^T A x + J^T x} = \det(A/2\pi)^{-1/2} e^{\frac{1}{2} J^T A^{-1} J}$ を汎関数積分へ適用すると、演算子 $A = -\Delta_E + m_0^2$ の逆演算子 $A^{-1}$ を用いて：

$$Z_0[J] = Z_0[0] \exp\left( \frac{1}{2} \int \mathrm{d}^4 x_E \mathrm{d}^4 y_E \, J(x_E) A^{-1}(x_E, y_E) J(y_E) \right)$$

自由 2 点相関関数（プロパゲーター）は、定義によりソース $J$ による 2 回汎関数微分で得られます：

$$G_0^E(x_E - y_E) \equiv \langle \phi(x_E) \phi(y_E) \rangle_0 = \frac{\delta^2 \ln Z_0[J]}{\delta J(x_E) \delta J(y_E)}\Bigg|_{J=0} = A^{-1}(x_E, y_E) = (-\Delta_E + m_0^2)^{-1}$$

運動量空間では対角化されて逆行列をとるだけなので、直接 $\tilde{G}_0^E(p_E) = \frac{1}{p_E^2 + m_0^2}$ となります。

---

### アプローチ 3: 有限温度統計力学（松原周波数）からの零温度極限
熱統計力学において、逆温度 $\beta = 1/(k_B T)$ のもとでの虚数時間プロパゲーターは、離散的な松原周波数（Matsubara frequencies $\omega_n = \frac{2n\pi}{\beta}$）で記述されます：

$$G(\omega_n, \mathbf{p}) = \frac{1}{\omega_n^2 + \mathbf{p}^2 + m_0^2}$$

ここで、絶対零度極限 $\beta \to \infty$（$T \to 0$）を取ると、離散的な周波数の和が連続積分へ移行します：

$$\frac{1}{\beta} \sum_{n=-\infty}^\infty \longrightarrow \int_{-\infty}^\infty \frac{\mathrm{d}p_4}{2\pi}$$

これにより、離散変数 $\omega_n$ が連続変数 $p_4$ に置き換わり、4次元連続ユークリッド伝播関数：

$$G_0^E(p_E) = \frac{1}{p_4^2 + \mathbf{p}^2 + m_0^2} = \frac{1}{p_E^2 + m_0^2}$$

が熱力学の自然な極限として得られます。

---

## 3. まとめ

| 観点 | ミンコフスキー場の量子論 | ユークリッド場の量子論 |
| :--- | :--- | :--- |
| **微分演算子** | 双曲型 $(-\partial_t^2 + \nabla^2 - m_0^2)$ | 楕円型正定値 $(-\Delta_E + m_0^2)$ |
| **極 (Poles)** | 実軸上に極が存在する | **全空間で極が存在しない ($p_E^2+m_0^2 > 0$)** |
| **導出方法** | Cauchyの主値・$i\epsilon$ 処方または Wick 回転 | **Green関数方程式またはガウス経路積分の直接逆演算** |
| **数学的状態** | 振動的 ($e^{iS}$)、特異的 | **絶対収縮的 ($e^{-S_E}$)、解析的に極めて健全** |
