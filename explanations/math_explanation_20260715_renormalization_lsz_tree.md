# ツリーレベルにおけるLSZを用いた行列要素の計算と $\phi(0)$ の $q$ 依存性

このドキュメントでは、擬スカラー相互作用ラグランジアンのもとで、LSZ簡約公式（および摂動論）を用いて三点関数のツリーレベルにおける行列要素 $\langle N(p') | \phi(0) | N(p) \rangle$ を具体的に計算し、その結果から運動量 $q$ への依存性を分析します。

---

## 1. セットアップ

相互作用ラグランジアン（湯川型の擬スカラー結合）を以下のように置きます：
$$\mathcal{L}_{\text{int}} = -i g \bar{\psi} \gamma_5 \psi \phi \tag{1}$$

求めたい行列要素は、オンシェルの核子状態 $|N(p)\rangle$, $\langle N(p')|$ で挟まれた、時空原点におけるメソン場 $\phi(0)$ です：
$$\langle N(p') | \phi(0) | N(p) \rangle \tag{2}$$

---

## 2. 摂動論を用いたツリーレベルの計算

相互作用描像における摂動展開を行います。ハミルトニアンの1次（ツリーレベル）において、この行列要素は以下のように展開されます：
$$\langle N(p') | \phi(x) | N(p) \rangle \approx i \int d^4y \, \langle N(p')_0 | \text{T} \phi_I(x) \mathcal{L}_{\text{int}, I}(y) | N(p)_0 \rangle \tag{3}$$
ここで、下付きの $0$ および $I$ は、相互作用のない自由粒子状態および自由場（相互作用描像の場）を表します。

式 (1) を式 (3) に代入します：
$$\begin{aligned}
\langle N(p') | \phi(x) | N(p) \rangle &\approx i \int d^4y \, \langle N(p')_0 | \text{T} \phi_I(x) \left( -i g \bar{\psi}_I(y) \gamma_5 \psi_I(y) \phi_I(y) \right) | N(p)_0 \rangle \\
&= g \int d^4y \, \langle N(p')_0 | \bar{\psi}_I(y) \gamma_5 \psi_I(y) | N(p)_0 \rangle \langle 0 | \text{T} \phi_I(x) \phi_I(y) | 0 \rangle \tag{4}
\end{aligned}$$
ここで、フェルミオン部分とメソン部分はそれぞれ独立な自由場なので、期待値が掛け算の形に因子化されます。

### 各因子の評価

#### (A) メソン部分（自由伝播関数）
$$\langle 0 | \text{T} \phi_I(x) \phi_I(y) | 0 \rangle = \Delta_F(x-y) = \int \frac{d^4k}{(2\pi)^4} \frac{i}{k^2 - \mu^2 + i\epsilon} e^{-ik(x-y)} \tag{5}$$

#### (B) フェルミオン部分
自由フェルミオン場の平面波展開（消滅・生成演算子による展開）を用いて、オンシェル状態の核子で挟むと、時空点 $y$ の依存性が指数関数として外に出ます：
$$\langle N(p')_0 | \bar{\psi}_I(y) \gamma_5 \psi_I(y) | N(p)_0 \rangle = \bar{u}(p') \gamma_5 u(p) e^{i(p'-p)y} \tag{6}$$
ここで $u(p), \bar{u}(p')$ はディラック・スピノールです。

---

## 3. 積分の実行

式 (5) と式 (6) を式 (4) に代入します：
$$\langle N(p') | \phi(x) | N(p) \rangle \approx g \bar{u}(p') \gamma_5 u(p) \int d^4y \, e^{i(p'-p)y} \int \frac{d^4k}{(2\pi)^4} \frac{i}{k^2 - \mu^2 + i\epsilon} e^{-ik(x-y)} \tag{7}$$

ここで、$y$ についての積分を先に実行します：
$$\int d^4y \, e^{i(p' - p + k)y} = (2\pi)^4 \delta^{(4)}(p' - p + k) \tag{8}$$

式 (8) を用いて $k$ についての積分を実行します：
$$\begin{aligned}
\langle N(p') | \phi(x) | N(p) \rangle &\approx g \bar{u}(p') \gamma_5 u(p) \int \frac{d^4k}{(2\pi)^4} \frac{i}{k^2 - \mu^2 + i\epsilon} e^{-ikx} (2\pi)^4 \delta^{(4)}(p' - p + k) \\
&= g \bar{u}(p') \gamma_5 u(p) \frac{i}{(p - p')^2 - \mu^2 + i\epsilon} e^{-i(p-p')x} \tag{9}
\end{aligned}$$

ここで、メソンの運動量を **$q = p' - p$** （放出されるメソンの運動量）と定義すると、$(p-p')^2 = (-q)^2 = q^2$ となり、式 (9) は以下のように整理されます：
$$\langle N(p') | \phi(x) | N(p) \rangle \approx \bar{u}(p') \gamma_5 u(p) \frac{i g}{q^2 - \mu^2 + i\epsilon} e^{iqx} \tag{10}$$

最後に、時空の原点 $x = 0$ における値を求めます：
$$\langle N(p') | \phi(0) | N(p) \rangle \approx \bar{u}(p') \gamma_5 u(p) \frac{i g}{q^2 - \mu^2 + i\epsilon} \tag{11}$$

---

## 4. $\phi(0)$ の運動量 $q$ 依存性の分析

式 (11) から、行列要素 $\langle N(p') | \phi(0) | N(p) \rangle$ の運動量 $q = p' - p$ に対する依存性が明確に示されています。

### (1) 伝播関数の極の構造
この行列要素は、仮想メソンの伝播関数 $\frac{i}{q^2 - \mu^2}$ を含んでいます。
したがって、運動量転送の二乗 $q^2 = (p'-p)^2$ の関数となっており、メソンが物理的な質量殻 $q^2 \to \mu^2$ に近づく極限において、この行列要素は**一次の極（ポール）**を持ちます。

### (2) 散乱振幅（LSZ）との接続
この行列要素から物理的な散乱振幅を取り出すには、LSZ簡約公式に従って、メソン場 $\phi(0)$ に対してクライン-ゴルドン演算子（運動量空間では $q^2 - \mu^2$ 因子）を掛けて極限 $q^2 \to \mu^2$ を取ります：
$$\text{Amplitude} = \lim_{q^2 \to \mu^2} (-i)(q^2 - \mu^2) \langle N(p') | \phi(0) | N(p) \rangle$$
これに式 (11) を代入すると：
$$\text{Amplitude} = \lim_{q^2 \to \mu^2} (-i)(q^2 - \mu^2) \left[ \bar{u}(p') \gamma_5 u(p) \frac{i g}{q^2 - \mu^2} \right] = g \bar{u}(p') \gamma_5 u(p)$$
これは、ツリーレベルにおける擬スカラー相互作用の物理的散乱振幅（オンシェル頂点）と完全に一致します。

### まとめ
* **$\phi(0)$ 自体の $q$ 依存性**: メソンの伝播関数を内包しているため、$\frac{1}{q^2 - \mu^2}$ に比例して変化します。
* **なぜ場の演算子にしたのか**: 場の演算子 $\phi$ のままで置いておくことで、メソンの伝播関数（オフシェルの効果）が自動的に行列要素の中に組み込まれ、運動量 $q^2$ を任意のオフシェル値に保ったまま議論できるようになるからです。
