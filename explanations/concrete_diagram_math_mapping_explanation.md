# 1つの具体例で解き明かす：完全な数学の式とファインマン・ダイアグラムの一対一対応マッピング

「パーツの式を個別に出すのではなく、1つの具体例を持ち出して、完全な数学の式の中のどのパーツがダイアグラムのどこに対応しているか」を完全に可視化した解説です。

---

## 1. 題材とする具体例：4点相関関数の 1 次項 $\mathcal{O}(\lambda^1)$

複素スカラー場理論において、2粒子が流入して2粒子が流出する散乱に対応する **4点相関関数** を考えます：

$$
G^{(4)}(z_1, z_2, w_1, w_2) \equiv \langle 0 | \mathrm{T} \hat{\phi}(z_1) \hat{\phi}(z_2) \hat{\phi}^*(w_1) \hat{\phi}^*(w_2) | 0 \rangle
$$

生成汎関数 $Z[J, J^*]$ からの定義式は以下の通りです：

$$
G^{(4)}(z_1, z_2, w_1, w_2) = \left. \frac{1}{i^4} \frac{\delta^4 Z[J, J^*]}{\delta J^*(z_1) \delta J^*(z_2) \delta J(w_1) \delta J(w_2)} \right|_{J=J^*=0}
$$

---

## 2. マスター公式からの完全な数学的計算ステップ

### Step 1: マスター公式の 1 次（$\lambda^1$）展開
相互作用 $\mathcal{L}_{\text{int}} = -\lambda (\phi^* \phi)^2$ を持つマスター公式：

$$
Z[J, J^*] = \exp\left\{ -i \lambda \int \mathrm{d}^4x \left( \frac{\delta}{i \delta J(x)} \frac{\delta}{i \delta J^*(x)} \right)^2 \right\} Z_0[J, J^*]
$$

を $\lambda$ について 1 次まで Taylor 展開します：

$$
Z[J, J^*] \supset \left[ -i \lambda \int \mathrm{d}^4x \left( \frac{\delta}{i \delta J(x)} \right)^2 \left( \frac{\delta}{i \delta J^*(x)} \right)^2 \right] Z_0[J, J^*]
$$

---

### Step 2: 微分演算子を自由生成汎関数 $Z_0$ に作用させる
自由場の生成汎関数 $Z_0[J, J^*] = \exp\left( -i \int \mathrm{d}^4u \mathrm{d}^4v J^*(u) D_F(u-v) J(v) \right)$ に対し、計8個の微分演算子を作用させます：
- 外部点からの微分 4 個: $\frac{\delta}{\delta J^*(z_1)}, \frac{\delta}{\delta J^*(z_2)}, \frac{\delta}{\delta J(w_1)}, \frac{\delta}{\delta J(w_2)}$
- 頂点 $x$ からの微分 4 個: $\frac{\delta}{\delta J(x)}$ が2個、$\frac{\delta}{\delta J^*(x)}$ が2個

微分を実行して $J=J^*=0$ と置くと、すべての外源 $J$ が消去され、以下の**完全な数学的式**が得られます：

$$
G^{(4)}(z_1, z_2, w_1, w_2)_{\mathcal{O}(\lambda)} = (-i 4 \lambda) \int \mathrm{d}^4x \, \left[ i D_F(z_1 - x) \right] \left[ i D_F(z_2 - x) \right] \left[ i D_F(x - w_1) \right] \left[ i D_F(x - w_2) \right]
$$

---

## 3. 完全な数式とファインマン・ダイアグラムの「一対一マッピング」

この導出された**完全な数学的式**のパーツと、**ファインマン・ダイアグラムの図形**を1対1で対応させます：

$$
\underbrace{G^{(4)}}_{\text{4点相関関数}} = \underbrace{(-i 4 \lambda)}_{\text{頂点因子}} \underbrace{\int \mathrm{d}^4x}_{\text{頂点位置の積分}} \underbrace{\left[ i D_F(z_1 - x) \right]}_{\text{流出線 1}} \underbrace{\left[ i D_F(z_2 - x) \right]}_{\text{流出線 2}} \underbrace{\left[ i D_F(x - w_1) \right]}_{\text{流入線 1}} \underbrace{\left[ i D_F(x - w_2) \right]}_{\text{流入線 2}}
$$

### 対応表（マッピング図）

| 数式のパーツ / 因子 | 物理・数学的意味 | ファインマン・ダイアグラムの「絵」 |
| :--- | :--- | :--- |
| $\int \mathrm{d}^4x$ | 相互作用が起きる時空点 $x$ での全空間積分 | 4本の線が集まる**「中央の頂点の位置 $x$」** |
| $\mathbf{-i 4\lambda}$ | 相互作用強度 $(-i\lambda)$ $\times$ 微分の組換え数 $2! \times 2! = 4$ | 4点頂点に割り当てられる**「頂点因子（Vertex Factor）」** |
| $i D_F(x - w_1)$ | 外部点 $w_1$ から点 $x$（頂点）へ粒子が伝播 | 点 $w_1$ から頂点 $x$ へ向かう**「矢印付き直線（流入線）」** |
| $i D_F(x - w_2)$ | 外部点 $w_2$ から点 $x$（頂点）へ粒子が伝播 | 点 $w_2$ から頂点 $x$ へ向かう**「矢印付き直線（流入線）」** |
| $i D_F(z_1 - x)$ | 点 $x$（頂点）から外部点 $z_1$ へ粒子が伝播 | 頂点 $x$ から点 $z_1$ へ向かう**「矢印付き直線（流出線）」** |
| $i D_F(z_2 - x)$ | 点 $x$（頂点）から外部点 $z_2$ へ粒子が伝播 | 頂点 $x$ から点 $z_2$ へ向かう**「矢印付き直線（流出線）」** |

---

## 4. なぜ「ファインマン・ルール」が作られたのか？

上の比較から分かる通り、ファインマン・ルールとは単に：

> **「この複雑な汎関数微分と積分の計算を毎回愚直にやらなくても、右欄の『絵』を先に描いて、各パーツに対応する左欄の『数式』を機械的に書き並べるだけで、全く同じ完全な数学的式が数秒で書き下せるように作られたショートカット（翻訳辞書）」**

なのです！

- 愚直な方法: 汎関数微分を8回実行する $\to$ 微分の組み合わせを数える $\to$ 式を得る。
- ファインマン・ルール: 「頂点 $x$ を描く（$-i4\lambda$）」$\to$ 「$w_1, w_2$ から $x$ への矢印線を描く（$i D_F$）」$\to$ 「$x$ から $z_1, z_2$ への矢印線を描く（$i D_F$）」$\to$ 「$\int \mathrm{d}^4x$ をつける」 $\to$ **式が即座に完成！**

---

## 5. 演算子形式（Dyson 級数 ＋ Wick の定理）との完全パラレル対比

演算子形式（正典量子化）に親しんでいる方のために、演算子形式の「Wick の定理」と、経路積分形式の「汎関数微分」が**全く同じ数学的作業を行なっていること**を平行（パラレル）に並べて対比します。

### 5.1 演算子形式（Dyson 級数）での 4点相関関数の導出

演算子形式では、相互作用描像（Interaction Picture）における Dyson 級数の 1 次項を展開します：

$$
G^{(4)}(z_1, z_2, w_1, w_2)_{\mathcal{O}(\lambda)} = \langle 0 | \mathrm{T} \left\{ \hat{\phi}_I(z_1) \hat{\phi}_I(z_2) \hat{\phi}_I^\dagger(w_1) \hat{\phi}_I^\dagger(w_2) \, \left( -i \lambda \int \mathrm{d}^4x (\hat{\phi}_I^\dagger(x) \hat{\phi}_I(x))^2 \right) \right\} | 0 \rangle
$$

Wick の定理を適用し、すべての演算子の対（縮約 / Wick Contractions）を作ります：

1. **頂点 $x$ にある演算子**:
   $(\hat{\phi}_I^\dagger(x))^2$ （反粒子を2個生成/消滅） と $(\hat{\phi}_I(x))^2$ （粒子を2個生成/消滅）。
2. **縮約（ペアリング）の組み合わせ数（組み合わせ係数）**:
   - 外線 $\hat{\phi}_I(z_1)$ を頂点の 2 つの $\hat{\phi}_I^\dagger(x)$ のいずれかと縮約する $\to$ **2 通り**
   - 外線 $\hat{\phi}_I(z_2)$ を残った 1 つの $\hat{\phi}_I^\dagger(x)$ と縮約する $\to$ **1 通り**
   - 外線 $\hat{\phi}_I^\dagger(w_1)$ を頂点の 2 つの $\hat{\phi}_I(x)$ のいずれかと縮約する $\to$ **2 通り**
   - 外線 $\hat{\phi}_I^\dagger(w_2)$ を残った 1 つの $\hat{\phi}_I(x)$ と縮約する $\to$ **1 通り**
   - 合計で $2 \times 1 \times 2 \times 1 = \mathbf{2! \times 2! = 4}$ 通りの全く同等な縮約パターンが発生！
3. **縮約されたプロパゲータ**:
   各縮約ペア $\overline{\hat{\phi}_I(u) \hat{\phi}_I^\dagger(v)} = \langle 0 | \mathrm{T} \hat{\phi}_I(u) \hat{\phi}_I^\dagger(v) | 0 \rangle = i D_F(u-v)$。

したがって、演算子形式でも全く同じ完全な式が導かれます：

$$
= (-i 4\lambda) \int \mathrm{d}^4x \, \left[ i D_F(z_1 - x) \right] \left[ i D_F(z_2 - x) \right] \left[ i D_F(x - w_1) \right] \left[ i D_F(x - w_2) \right]
$$

---

### 5.2 二つの形式の完全パラレル対比表

| 導出ステップ / 概念 | 演算子形式（Canonical Quantization） | 経路積分形式（Path Integral） |
| :--- | :--- | :--- |
| **基本状態・変数** | 状態ベクトル $\|0\rangle$ と演算子 $\hat{\phi}_I(x)$ | c-number 場の配置 $\phi(x)$ と汎関数 $\int \mathcal{D}\phi$ |
| **相互作用項** | Dyson 級数 $T \exp\left( -i \int \mathcal{H}_{\text{int}} \mathrm{d}t \right)$ | マスター演算子 $\exp\left( -i \int \mathcal{L}_{\text{int}}(\frac{\delta}{i\delta J}) \mathrm{d}^4x \right)$ |
| **自由場の二点関数** | Wick 縮約 $\overline{\hat{\phi}_I(x) \hat{\phi}_I^\dagger(y)} = i D_F(x-y)$ | 汎関数微分 $\frac{\delta^2 Z_0}{i\delta J^*(x) i\delta J(y)} = i D_F(x-y)$ |
| **線の並べ替え重複度** | 演算子の縮約ペアの組み合わせ $2! \times 2! = 4$ | 汎関数微分の適用順序の組み合わせ $2! \times 2! = 4$ |
| **頂点因子** | $\langle 0 \| \text{頂点} \| 0 \rangle \to \mathbf{-i 4\lambda}$ | $-i \lambda \times (\text{重複度 } 4) \to \mathbf{-i 4\lambda}$ |
| **最終的な物理的結果** | **完全に同一のファインマン・ダイアグラムと振幅** | **完全に同一のファインマン・ダイアグラムと振幅** |

