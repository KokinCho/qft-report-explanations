# Part B 第1問 (9) Wick回転・$i\epsilon$処方・虚数時間解析接続の厳密数学解説ドキュメント

本ドキュメントは、`Kokin_Cho_QFT_term_paper.tex` の Part B 第1問 (9) における **$i\epsilon$ の極の因数分解、Wick回転による複素積分経路の変形、測度の $i$ と分母の符号相殺プロセス、および虚数時間への解析接続** について、途中の数式ステップを省略することなく完全かつ厳密に解説した公式ガイドです。

---

## 1. $i\epsilon$ の因数分解と極（Poles）の位置の厳密証明

### 1.1. ミンコフスキー空間での伝播関数分母
運動量空間におけるファインマン伝播関数は以下のように定義されます：

$$i D_F(k) = \frac{i}{k_0^2 - \mathbf{k}^2 - m_0^2 + i\epsilon} = \frac{i}{k_0^2 - (\omega_k^2 - i\epsilon)}$$

ここで $\omega_k = \sqrt{\mathbf{k}^2 + m_0^2} > 0$ はオンシェルエネルギーであり、$\epsilon > 0$ は極限 $\epsilon \to 0^+$ を取る正の無限小です。

### 1.2. 平方根のテーラー展開と因数分解
分母 $k_0^2 - (\omega_k^2 - i\epsilon)$ を $k_0$ について因数分解するために、ズレを含んだ質量項の平方根を計算します。$\frac{\epsilon}{\omega_k^2} \ll 1$ であるため、テイラー展開 $\sqrt{1 - x} \approx 1 - \frac{1}{2}x$ を適用できます：

$$\sqrt{\omega_k^2 - i\epsilon} = \omega_k \sqrt{1 - \frac{i\epsilon}{\omega_k^2}} \approx \omega_k \left( 1 - \frac{i\epsilon}{2\omega_k^2} \right) = \omega_k - i\epsilon' \quad \left( \text{ただし } \epsilon' \coloneqq \frac{\epsilon}{2\omega_k} > 0 \right)$$

この展開を平方の差の公式 $A^2 - B^2 = (A - B)(A + B)$ に代入します：

$$\begin{aligned}
k_0^2 - \mathbf{k}^2 - m_0^2 + i\epsilon &= k_0^2 - (\omega_k - i\epsilon')^2 \\
&= \left[ k_0 - (\omega_k - i\epsilon') \right] \left[ k_0 + (\omega_k - i\epsilon') \right] \\
&= (k_0 - \omega_k + i\epsilon')(k_0 + \omega_k - i\epsilon')
\end{aligned}$$

無次元化された無限小記号として $\epsilon'$ を改めて $\epsilon > 0$ と書き直すと、伝播関数の分母は**厳密に**以下の形に因数分解されます：

$$k_0^2 - \mathbf{k}^2 - m_0^2 + i\epsilon = (k_0 - \omega_k + i\epsilon)(k_0 + \omega_k - i\epsilon)$$

---

### 1.3. 極の象限配置
分母がゼロになる複素 $k_0$ 平面での極（Poles）の位置は以下の 2 点です：

1. **$k_0 = \omega_k - i\epsilon$** ： **第 4 象限（複素平面の右下）**
2. **$k_0 = -\omega_k + i\epsilon$** ： **第 2 象限（複素平面の左上）**

> **【重要な構造】**:
> **第 1 象限（右上）** および **第 3 象限（左下）** には極が存在しません。
> したがって、実軸上の積分経路 $k_0 \in (-\infty, \infty)$ を**時計回りに $90^\circ$ 回転**させて虚軸上に持ち上げても、途中で極を跨いだり横切ったりすることはありません。

---

## 2. Cauchy の積分定理と Wick 回転の厳密なステップ

### 2.1. 閉回路（Contour）の構築
複素 $k_0$ 平面において、以下の 4 つの経路からなる半径 $R \to \infty$ の閉曲線 $C$ を考えます：
1. **$C_1$ (実軸)**: $k_0 \in [-R, R]$ （元の積分経路）
2. **$C_R^{(1)}$ (第 4 象限の円弧)**: $k_0 = R e^{-i\theta} \quad (\theta \in [0, \pi/2])$
3. **$C_2$ (虚軸)**: $k_0 = -i k_4 \quad (k_4 \in [-R, R])$
4. **$C_R^{(2)}$ (第 2 象限の円弧)**: $k_0 = -R e^{-i\theta} \quad (\theta \in [0, \pi/2])$

第 1 象限および第 3 象限に極が存在しない領域で閉回路を形成するため、Cauchy の積分定理により：

$$\oint_C \mathrm{d}k_0 \, f(k_0) = 0 \implies \int_{-\infty}^\infty \mathrm{d}k_0 \, f(k_0) = \int_{-i\infty}^{i\infty} \mathrm{d}k_0 \, f(k_0)$$

---

### 2.2. 変数変換 $k_0 = i k_4$
虚軸上の積分を行うため、実数変数 $k_4 \in (-\infty, \infty)$ を用いて $k_0 = i k_4$ と置換します。

* **四次元運動量の 2 乗**:
  $$k^2 = k_0^2 - \mathbf{k}^2 = (i k_4)^2 - \mathbf{k}^2 = -k_4^2 - \mathbf{k}^2 = -(\mathbf{k}^2 + k_4^2) = -k_E^2$$
  （ここで $k_E^2 = \mathbf{k}^2 + k_4^2$ は正定値な 4 次元ユークリッド運動量の 2 乗）
* **体積要素 (Integration Measure)**:
  $$\mathrm{d}^4 k = \mathrm{d}k_0 \, \mathrm{d}^3 \mathbf{k} = (i \, \mathrm{d}k_4) \, \mathrm{d}^3 \mathbf{k} = i \, \mathrm{d}^4 k_E$$
  （$k_E = (\mathbf{k}, k_4) \in \mathbb{R}^4$）

---

### 2.3. 被積分関数と $i^2 = -1$ による相殺ステップ（核心部）

ミンコフスキー空間の積分にこれらの変換式を愚直に代入します：

$$\int_{\mathbb{R}^4} \mathrm{d}^4 k \frac{i}{k^2 - m_0^2 + i\epsilon} = \int_{\mathbb{R}^4} (i \, \mathrm{d}^4 k_E) \frac{i}{-k_E^2 - m_0^2}$$

分子の $i$ の積を計算します：

$$\text{分子} = (i \, \mathrm{d}^4 k_E) \times i = i^2 \, \mathrm{d}^4 k_E = -\mathrm{d}^4 k_E$$

分母のマイナス符号を括り出します：

$$\text{分母} = -k_E^2 - m_0^2 = -(k_E^2 + m_0^2)$$

これらを合わせると：

$$\frac{-\mathrm{d}^4 k_E}{-(k_E^2 + m_0^2)} = \frac{\mathrm{d}^4 k_E}{k_E^2 + m_0^2}$$

したがって：

$$\int_{\mathbb{R}^4} \mathrm{d}^4 k \frac{i}{k^2 - m_0^2 + i\epsilon} = \int_{\mathbb{R}^4} \mathrm{d}^4 k_E \frac{1}{k_E^2 + m_0^2}$$

となり、**虚数単位 $i$ が完全に消去され、正定値なユークリッド伝播関数の積分に厳密に一致する** ことが示されます。

---

## 3. 虚数時間への解析接続と時空ドメインの物理的意味

### 3.1. 運動量空間と実時空の双対性
運動量空間での Wick 回転 $k_0 = i k_4$ は、フーリエ変換の双対性（位相 $e^{-i k \cdot x} = e^{-i k_0 t + i \mathbf{k} \cdot \mathbf{x}}$）を通じて、**実空間の時間座標の解析接続** と 1 対 1 に対応します：

$$t \to -i \tau \quad (\tau \in \mathbb{R})$$

### 3.2. 計量（Metric）の変化
* **ミンコフスキー時空の不変量**:
  $$\mathrm{d}s^2 = \mathrm{d}t^2 - \mathrm{d}\mathbf{x}^2 \quad (\text{符号構図 } (+, -, -, -))$$
  時間方向と空間方向で符号が異なり、光錐（Light-cone）構造を持ちます。
* **ユークリッド空間の不変量**:
  $t = -i\tau \implies \mathrm{d}t^2 = (-\mathrm{d}\tau)^2 = -\mathrm{d}\tau^2$。全体の符号を反転させた Euclid 計量は：
  $$\mathrm{d}s_E^2 = \mathrm{d}\tau^2 + \mathrm{d}\mathbf{x}^2 \quad (\text{符号構図 } (+, +, +, +))$$
  完全に正定値な 4 次元リーマン多様体となります。

### 3.3. 記述される物理ドメイン（Domain of Spacetime Events）
1. **因果的光錐構造の消失**:
   虚数時間 $\tau$ の世界では、時間軸と空間軸が同等になり、因果律（Causality）や光錐（未来・過去）が存在しなくなります。
2. **波動伝播から減衰・統計力学へ**:
   実時間における波の位相振動 $e^{-i E t}$ が、虚数時間では指数関数的減衰 $e^{-E \tau}$ に変化します。
   これは、場の量子論の真空期待値と、4 次元統計力学（Thermodynamics / Diffusion process）の分配関数 $e^{-\beta H}$ が数学的に完全一致することを意味しています。
