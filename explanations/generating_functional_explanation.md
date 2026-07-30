# 場の量子論における生成汎関数 $Z[J, J^*]$ の導出と物理的本質

## 1. なぜ $T$ 積の真空期待値（Green 関数）を考えたいのか？

場の量子論において、粒子散乱の断面積や崩壊率などの観測可能な物理量は、**S 行列（S-matrix）** から計算されます。LSZ 簡約公式（Lehmann-Symanzik-Zimmermann reduction formula）によれば、S 行列の要素は**ハイゼンベルク描像における場の演算子の時間順序積（$T$ 積）の真空期待値**（$n$ 点 Green 関数）に直結しています：

$$
\langle 0 | T \{ \hat{\phi}(x_1) \hat{\phi}(x_2) \cdots \hat{\phi}(x_n) \} | 0 \rangle
$$

ここで $T$ は時間順序積（Time-ordering operator）であり、時間が遅い演算子ほど左側に配置する操作です。量子場理論の散乱問題を解くという目的は、原理的には**あらゆる $n$ に対する $n$ 点 Green 関数を系統的に計算すること**に帰着されます。

---

## 2. $T$ 積真空期待値から生成汎関数 $Z[J]$ への導出

### 2.1 外部源 $J(x)$ の導入と定義

統計力学で外部磁場 $h$ を入れて自由エネルギーを微分するテクニックと同様に、量子場 $\hat{\phi}(x)$ に結合する古典的な**外源（source）** $J(x)$ を導入します。

外源 $J(x)$ が存在する体系の作用 $S[J]$ は次のように表されます：

$$
S[J] = S_0[\phi] + \int \mathrm{d}^4 x \, J(x) \hat{\phi}(x)
$$

このとき、**生成汎関数（Generating Functional）** $Z[J]$ を、外源 $J(x)$ が存在するもとでの「過去の真空（$|0, \mathrm{in}\rangle$）から未来の真空（$|0, \mathrm{out}\rangle$）への遷移振幅」として定義します：

$$
Z[J] \equiv \langle 0, \mathrm{out} | 0, \mathrm{in} \rangle_J = \langle 0 | T \exp\left( i \int \mathrm{d}^4 x \, J(x) \hat{\phi}(x) \right) | 0 \rangle
$$

### 2.2 汎関数微分による Green 関数の抽出

この $Z[J]$ を定義しておくと、$J(x)$ に関する**汎関数微分（functional derivative）** を行うことで、所望の $T$ 積真空期待値が自動的に「生成」されます。

指数関数を Taylor 展開すると：

$$
Z[J] = \sum_{n=0}^{\infty} \frac{i^n}{n!} \int \mathrm{d}^4 x_1 \cdots \mathrm{d}^4 x_n \, J(x_1) \cdots J(x_n) \, \langle 0 | T \{ \hat{\phi}(x_1) \cdots \hat{\phi}(x_n) \} | 0 \rangle
$$

したがって、$n$ 回汎関数微分して最後に $J=0$ とおくことで：

$$
\left. \frac{\delta^n Z[J]}{\delta J(x_1) \delta J(x_2) \cdots \delta J(x_n)} \right|_{J=0} = i^n \, \langle 0 | T \{ \hat{\phi}(x_1) \hat{\phi}(x_2) \cdots \hat{\phi}(x_n) \} | 0 \rangle
$$

が得られます。これが「生成汎関数」と呼ばれる本質的な理由です。

---

## 3. 演算子表現から経路積分（作用 $S$）への完全な導出（ギャップの解消）

「なぜ演算子の $T$ 積真空期待値から、ラグランジアン/作用 $S$ を含む経路積分が生えてくるのか？」という疑問に答えるため、演算子表現 $Z[J] = \langle 0 | T \exp\left(i \int \mathrm{d}^4x J \hat{\phi}\right) | 0 \rangle$ から経路積分へのつなぎ目を完全に可視化します。

---

### 3.1 Step 1: $T$ 積演算子と時間発展演算子の関係

相互作用描像における Dyson 級数の公式によれば、相互作用ハミルトニアン $\hat{H}_{\mathrm{int}}(t)$ による時間発展演算子 $\hat{U}(t_f, t_i)$ は次のように書けます：

$$
\hat{U}(t_f, t_i) = T \exp\left( -i \int_{t_i}^{t_f} \mathrm{d}t \, \hat{H}_{\mathrm{int}}(t) \right)
$$

ここで外源 $J(x)\hat{\phi}(x)$ を一種の相互作用ハミルトニアン $\hat{H}_{\mathrm{int}}(t) = -\int \mathrm{d}^3x \, J(t, \mathbf{x}) \hat{\phi}(\mathbf{x})$ とみなすと、生成汎関数の被期待値にある $T$ 積演算子は、**外源 $J(x)$ が存在するもとでの全ハミルトニアン $\hat{H}[J] = \hat{H}_0 - \int \mathrm{d}^3x J\hat{\phi}$ によるフル時間発展演算子** $\hat{U}_J(t_f, t_i)$ そのものになります：

$$
T \exp\left( i \int_{t_i}^{t_f} \mathrm{d}^4 x \, J(x) \hat{\phi}(x) \right) = \hat{U}_J(t_f, t_i) = e^{i \hat{H}_0 t_f} e^{-i \hat{H}[J](t_f - t_i)} e^{-i \hat{H}_0 t_i}
$$

基底状態（真空 $|0\rangle$）のエネルギーを $E_0 = 0$（すなわち $\hat{H}_0 |0\rangle = 0$）と規格化しておくと、$e^{\pm i \hat{H}_0 t} |0\rangle = |0\rangle$ となるため、真空期待値はシンプルに**ハミルトニアン $\hat{H}[J]$ による時間発展の真空期待値**に化けます：

$$
Z[J] = \langle 0 | T \exp\left( i \int \mathrm{d}^4 x \, J(x) \hat{\phi}(x) \right) | 0 \rangle = \langle 0 | e^{-i \hat{H}[J](t_f - t_i)} | 0 \rangle \quad (t_i \to -\infty, t_f \to +\infty)
$$

---

### 3.2 Step 2: 場の固有状態の完全系を挟んで「遷移振幅」を出す

次に、演算子表現の真空期待値 $\langle 0 | e^{-i \hat{H}[J](t_f - t_i)} | 0 \rangle$ に、始刻 $t_i$ と終刻 $t_f$ における「場の基底（固有状態）$|\phi_i\rangle, |\phi_f\rangle$」の完全性関係 $\int \mathcal{D}\phi_i \, |\phi_i\rangle \langle \phi_i| = 1$ を挿入します：

$$
\begin{aligned}
Z[J] &= \langle 0 | \left( \int \mathcal{D}\phi_f \, |\phi_f\rangle \langle \phi_f| \right) e^{-i \hat{H}[J](t_f - t_i)} \left( \int \mathcal{D}\phi_i \, |\phi_i\rangle \langle \phi_i| \right) | 0 \rangle \\
&= \int \mathcal{D}\phi_f \mathcal{D}\phi_i \, \langle 0 | \phi_f \rangle \, \underbrace{\langle \phi_f | e^{-i \hat{H}[J](t_f - t_i)} | \phi_i \rangle}_{\text{状態 } \phi_i \text{ から } \phi_f \text{ への遷移振幅 } \langle \phi_f, t_f | \phi_i, t_i \rangle_J} \, \langle \phi_i | 0 \rangle
\end{aligned}
$$

ここで初めて、**「状態 $\phi_i$ から $\phi_f$ への遷移振幅 $\langle \phi_f, t_f | \phi_i, t_i \rangle_J$」が自然に出現**します！

---

### 3.3 Step 3: 中間ステップの時間分割と作用 $S$ の出現（経路積分化）

ここで出現した遷移振幅 $\langle \phi_f | e^{-i \hat{H}[J](t_f - t_i)} | \phi_i \rangle$ の中に、中間時刻 $t_1, t_2, \cdots, t_{N-1}$ の完全系 $\int \mathcal{D}\phi_k \, |\phi_k\rangle \langle \phi_k| = 1$ を無数に挟み込みます：

1. **時間の細分化**:
   $$
   \langle \phi_f | e^{-i \hat{H}[J] (t_f - t_i)} | \phi_i \rangle = \int \mathcal{D}\phi_1 \cdots \mathcal{D}\phi_{N-1} \prod_{k=0}^{N-1} \langle \phi_{k+1} | e^{-i \hat{H}[J] \Delta t} | \phi_k \rangle
   $$
2. **共役運動量 $\pi$ の完全系とガウス積分**:
   1ステップの行列要素に共役運動量 $\hat{\pi}$ の完全系 $\int \mathcal{D}\pi_k \, |\pi_k\rangle\langle \pi_k| = 1$ を挟むと：
   $$
   \langle \phi_{k+1} | e^{-i \hat{H}[J] \Delta t} | \phi_k \rangle = \int \mathcal{D}\pi_k \, \exp\left( i \Delta t \int \mathrm{d}^3 x \left[ \pi_k \frac{\phi_{k+1} - \phi_k}{\Delta t} - \mathcal{H}(\phi_k, \pi_k) + J \phi_k \right] \right)
   $$
   標準的なハミルトニアン密度 $\mathcal{H}(\phi, \pi) = \frac{1}{2}\pi^2 + \frac{1}{2}(\nabla \phi)^2 + \frac{1}{2}m_0^2 \phi^2$ について $\pi_k$ で平方完成してガウス積分を行うと、運動量 $\pi$ が消去されて**ラグランジアン密度 $\mathcal{L}_0 = \frac{1}{2}(\partial_\mu \phi)^2 - \frac{1}{2}m_0^2 \phi^2$** が出現します：
   $$
   \langle \phi_{k+1} | e^{-i \hat{H}[J] \Delta t} | \phi_k \rangle \propto \exp\left( i \Delta t \int \mathrm{d}^3 x \left[ \mathcal{L}_0(\phi_k, \partial \phi_k) + J(t_k, \mathbf{x})\phi_k(\mathbf{x}) \right] \right)
   $$
3. **連続極限 $N \to \infty$**:
   すべてのステップを足し合わせると、指数関数の肩に**作用 $S[J] = \int \mathrm{d}^4 x (\mathcal{L}_0 + J\phi)$** が得られます：
   $$
   \langle \phi_f | e^{-i \hat{H}[J](t_f - t_i)} | \phi_i \rangle = \int \mathcal{D}\phi \, \exp\left( i \int_{t_i}^{t_f} \mathrm{d}^4 x \left[ \mathcal{L}_0(\phi, \partial \phi) + J(x)\phi(x) \right] \right)
   $$

---

### 3.4 Step 4: 真空射影（$i\epsilon$ 処方）による境界波動関数の消去と最終形

Step 2 で残っていた両端の真空波動関数 $\langle 0 | \phi_f \rangle$ と $\langle \phi_i | 0 \rangle$ は、時間を複素平面上に回転させる $t \to t(1 - i\epsilon)$（$i\epsilon$ 処方）を行うことで処理されます。

$$
e^{-i \hat{H} T (1-i\epsilon)} = e^{-i \hat{H} T} e^{-\epsilon \hat{H} T}
$$

$T = t_f - t_i \to \infty$ の極限で、基底状態（真空 $|0\rangle$）以外の励起状態 $E_n > 0$ はすべて $e^{-\epsilon E_n T} \to 0$ となって指数関数的に減衰・消去されます。
この結果、始状態・終状態の境界の詳細（波動関数の形）は単なる全体の定数倍（規格化定数 $\mathcal{N}$）に吸収され、次のように**作用 $S$ を含んだ全時空での経路積分 $Z[J]$** に帰着します：

$$
Z[J] = \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \, \exp\left( i \int \mathrm{d}^4 x \left[ \mathcal{L}_0 + J(x)\phi(x) + i\epsilon \phi^2 \right] \right)
$$

複素スカラー場 $\phi, \phi^*$ の場合は、これがそのまますべての場の自由度と源 $J, J^*$ の形になります：

$$
Z_0[J, J^*] = \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \mathcal{D}\phi^* \exp\left\{ i \int \mathrm{d}^4 x \left[ \partial_\mu \phi^* \partial^\mu \phi - m_0^2 \phi^* \phi + J^*\phi + J\phi^* + i\epsilon \phi^*\phi \right] \right\}
$$

これで、**演算子の $T$ 積真空期待値の定義から、作用 $S$ を含む汎関数積分表示への導出が1つのギャップもなく論理的につ起がりました**。

自由複素スカラー場 $\phi(x)$ の場合、ラグランジアン密度は：

$$
\mathcal{L}_0 = \partial_\mu \phi^* \partial^\mu \phi - m_0^2 \phi^* \phi
$$

であり、独立な自由度として $\phi$ と $\phi^*$、および対応する外源 $J$ と $J^*$ を導入します（$J^*\phi + J\phi^*$ の項で実数の作用を保つ）。

したがって、求める生成汎関数はまさに以下の形となります：

$$
Z_0[J, J^*] = \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \mathcal{D}\phi^* \exp\left\{ i \int \mathrm{d}^4 x \left[ \partial_\mu \phi^* \partial^\mu \phi - m_0^2 \phi^* \phi + J^*\phi + J\phi^* + i\epsilon \phi^*\phi \right] \right\}
$$

---

## 4. 自由場における具体的な高次計算（ガウス積分の平方完成の詳細）

生成汎関数が物理的にきわめて強力な理由は、自由場（二次形式の作用）において**ガウス積分として厳密に代数計算・平方完成ができる**からです。ここでは平方完成の具体的な導出ステップを細かく追います。

---

### 4.1 Step 1: 作用の二次形式表示と演算子の定義

自由複素スカラー場の作用に外源を加えた全作用 $S_0[J, J^*]$ は次のように与えられます：

$$
S_0[J, J^*] = \int \mathrm{d}^4 x \left[ \partial_\mu \phi^* \partial^\mu \phi - m_0^2 \phi^* \phi + i\epsilon \phi^* \phi + J^* \phi + J \phi^* \right]
$$

運動項を部分積分して境界項を捨て（$i\epsilon$ 処方により遠方で場が減衰するため正当化）、ダランベルシアン演算子 $\partial^2 = \partial_\mu \partial^\mu$ をまとめて整理します：

$$
S_0[J, J^*] = \int \mathrm{d}^4 x \left[ -\phi^*(x) (\partial^2 + m_0^2 - i\epsilon) \phi(x) + J^*(x)\phi(x) + J(x)\phi^*(x) \right]
$$

ここで、クライン-ゴルドン演算子を $\hat{K} \equiv -(\partial^2 + m_0^2 - i\epsilon)$ と定義します。

---

### 4.2 Step 2: ファインマン伝播関数（逆演算子）による場のシフト

演算子 $\hat{K}$ の逆演算子 $\hat{K}^{-1}$ に対応する時空表示（グリーン関数）が**ファインマン伝播関数 $D_F(x-y)$** です：

$$
(\partial^2 + m_0^2 - i\epsilon) D_F(x-y) = -\delta^{(4)}(x-y) \quad \iff \quad \hat{K}_x D_F(x-y) = \delta^{(4)}(x-y)
$$

この $D_F(x-y)$ は対称性 $D_F(x-y) = D_F(y-x)$ を持ちます。

1次元の平方完成 $a x^2 + b x = a(x + \frac{b}{2a})^2 - \frac{b^2}{4a}$ と全く同じ発想で、停留点（オイラー＝ラグランジュ方程式の解）に合わせて場 $\phi(x)$ をシフトします：

$$
\phi(x) = \phi_0(x) - \int \mathrm{d}^4 y \, D_F(x-y) J(y)
$$

$$
\phi^*(x) = \phi_0^*(x) - \int \mathrm{d}^4 z \, J^*(z) D_F(z-x)
$$

> **【補足: なぜ $\phi^*(x)$ の式で $D_F(z-x)$ と引数が反転するのか？】**  
> 1. **演算子のエルミート共役（転置）**: 演算子の核表示 $\phi = \hat{K}^{-1} J$ （つまり $\phi(x) = \int \mathrm{d}^4 y \, D_F(x-y) J(y)$）の複素共役をとると、行列の積の複素共役 $(AB)^\dagger = B^\dagger A^\dagger$ と同様に $\phi^\dagger = J^\dagger (\hat{K}^{-1})^\dagger$ となります。成分表示では演算子核の成分が転置されるため、$(D_F)_{xz} \to (D_F^\dagger)_{zx} = D_F(z-x)^*$ となり、左側から掛かる $J^*(z)$ と右側の位置 $x$ をつなぐため引数の順序が $z-x$ に反転します。
> 2. **伝播関数の対称性**: 伝播関数自体は偶関数 $D_F(z-x) = D_F(x-z)$ ですが、演算子としての「$z$ で作られた源 $J^*(z)$ が $x$ へ伝播する」という内積のつながりを明確にするために $D_F(z-x)$ と表記しています。

---

### 4.3 Step 3: シフトの代入と 1 次項の相殺

このシフトした $\phi(x), \phi^*(x)$ を作用の被積分関数に代入して計算します。

1. **運動項 $-\phi^* \hat{K} \phi$ の展開**:
   $$
   \begin{aligned}
   -\phi^*(x) \hat{K}_x \phi(x) &= -\left( \phi_0^*(x) + \int \mathrm{d}^4 z \, J^*(z) D_F(z-x) \right) \hat{K}_x \left( \phi_0(x) + \int \mathrm{d}^4 y \, D_F(x-y) J(y) \right) \\
   &= -\phi_0^*(x) \hat{K}_x \phi_0(x) - \phi_0^*(x) \underbrace{\hat{K}_x \int \mathrm{d}^4 y \, D_F(x-y) J(y)}_{= J(x)} - \left( \int \mathrm{d}^4 z \, J^*(z) D_F(z-x) \right) \hat{K}_x \phi_0(x) \\
   &\quad - \left( \int \mathrm{d}^4 z \, J^*(z) D_F(z-x) \right) \underbrace{\hat{K}_x \int \mathrm{d}^4 y \, D_F(x-y) J(y)}_{= J(x)}
   \end{aligned}
   $$
   グリーン関数の性質 $\hat{K}_x D_F(x-y) = \delta^{(4)}(x-y)$ により、$\hat{K}_x$ が積分の内側に入ってデルタ関数となり、積分が実行されて単なる $J(x)$ に化けます：
   $$
   -\phi^* \hat{K}_x \phi = -\phi_0^*(x) \hat{K}_x \phi_0(x) - \phi_0^*(x) J(x) - J^*(x) \phi_0(x) - \int \mathrm{d}^4 y \, J^*(x) D_F(x-y) J(y)
   $$

2. **源の項 $J^* \phi + J \phi^*$ の展開**:
   $$
   J^*(x)\phi(x) + J(x)\phi^*(x) = J^*(x)\phi_0(x) + J^*(x) \int \mathrm{d}^4 y \, D_F(x-y) J(y) + J(x)\phi_0^*(x) + J(x) \int \mathrm{d}^4 z \, J^*(z) D_F(z-x)
   $$

3. **足し合わせによる 1 次項の完全消去**:
   全作用の被積分関数 $-\phi^* \hat{K} \phi + J^* \phi + J \phi^*$ を足し合わせると、$\phi_0$ および $\phi_0^*$ に関する 1 次の項が**符号が反転して完全に打ち消し合って消滅**します！

   $$
   -\phi^*(x) \hat{K}_x \phi(x) + J^*(x)\phi(x) + J(x)\phi^*(x) = -\phi_0^*(x) \hat{K}_x \phi_0(x) + J^*(x) \int \mathrm{d}^4 y \, D_F(x-y) J(y)
   $$

---

### 4.4 Step 4: 測度の分離とガウス積分の評価

> **【疑問の解消: 時空 $x$ に依存するシフトなのに、なぜ汎関数積分から見て「定数」と言え、外にくくり出せるのか？】**  
> ここで最も混同しやすいのは **「時空に関する積分 $\int \mathrm{d}^4 x$」** と **「場の配置に関する汎関数積分 $\int \mathcal{D}\phi$」** の違いです。
> 1. **積分の変数**: 汎関数積分 $\int \mathcal{D}\phi_0$ の積分変数は、時空の各点における場の値 $\{\phi_0(x)\}_{x}$ です。一方で、外源 $J(y)$ はあらかじめ外部から与えられた固定された関数（背景場）であり、$\phi_0(x)$ とは全く独立です。
> 2. **ヤコビアンが 1 になる理由**: 多重積分で固定ベクトル $c = (c_1, \dots, c_N)$（各成分 $c_i$ は異なる値を持つ）を用いて $x'_i = x_i + c_i$ とシフトした際、各 $c_i$ が $i$ に依って変化しても $x$ に依存しないためヤコビ行列は単位行列 $\frac{\partial x'_i}{\partial x_j} = \delta_{ij}$ になり、ヤコビアンは 1 になります。場でも全く同じで、$\frac{\delta \phi(x)}{\delta \phi_0(y)} = \delta^{(4)}(x-y)$ （単位演算子）となるため汎関数ヤコビアンは 1 です：
>    $$
>    \mathcal{D}\phi \mathcal{D}\phi^* = \mathcal{D}\phi_0 \mathcal{D}\phi_0^*
>    $$
> 3. **積分の外にくくり出せる理由**: シフト代入後に現れた項 $i \int \mathrm{d}^4 x \, \mathrm{d}^4 y \, J^*(x) D_F(x-y) J(y)$ には、**積分変数 $\phi_0(x)$ が一切含まれていません**。普通の微積分で $\int e^{f(x) + C} \mathrm{d}x = e^C \int e^{f(x)} \mathrm{d}x$ と定数 $C$ を外に出せるのと全く同様に、$\phi_0$ を含まないこの項は汎関数積分 $\int \mathcal{D}\phi_0$ の外にそっくりそのまま括り出すことができます。

したがって、生成汎関数の経路積分は「$\phi_0$ に関する汎関数積分」と「$J, J^*$ だけに依る定数項」に**完全ファクタライズ（積の形に分離）** されます：

$$
\begin{aligned}
Z_0[J, J^*] &= \frac{1}{\mathcal{N}} \int \mathcal{D}\phi_0 \mathcal{D}\phi_0^* \, \exp\left( i \int \mathrm{d}^4 x \left[ -\phi_0^*(x) \hat{K}_x \phi_0(x) \right] \right) \\
&\quad \times \exp\left( i \int \mathrm{d}^4 x \, \mathrm{d}^4 y \, J^*(x) D_F(x-y) J(y) \right)
\end{aligned}
$$

第1項の $\phi_0$ に関する積分は、外源が一切存在しない自由場の真空遷移振幅 $Z_0[0, 0]$ そのものであり、規格化定数を $\mathcal{N} = \int \mathcal{D}\phi_0 \mathcal{D}\phi_0^* \, e^{i S_0[\phi_0]}$ と選んでおくことで $Z_0[0,0] = 1$ に正規化されます。

以上により、自由複素スカラー場の生成汎関数は以下の閉じた解を得ます：

$$
Z_0[J, J^*] = \exp\left( i \int \mathrm{d}^4 x \, \mathrm{d}^4 y \, J^*(x) D_F(x-y) J(y) \right)
$$

※ 注意: 先に定義した $D_F(x-y)$ は $(\partial^2+m_0^2-i\epsilon)D_F(x-y) = -\delta^{(4)}(x-y)$ を満たすため、作用の符号として $-i \int J^* D_F J$ と書くか、$i D_F$ を $T$ 積真空期待値 $\langle 0 | T \hat{\phi}(x) \hat{\phi}^\dagger(y) | 0 \rangle = i D_F(x-y)$ で置き換えて以下のように表現します：

$$
Z_0[J, J^*] = \exp\left( -\int \mathrm{d}^4 x \, \mathrm{d}^4 y \, J^*(x) \langle 0 | T \hat{\phi}(x) \hat{\phi}^\dagger(y) | 0 \rangle J(y) \right)
$$

この美しい指数関数形式によって、$J, J^*$ で汎関数微分するだけで、任意の $n$ 点 $T$ 積真空期待値（Wick の定理によるすべての組み合わせの伝播関数の積の和）が一挙に導出可能になります。

---

## 5. 統計力学の分配関数とのパラレル（物理的対応関係）

QFT の生成汎関数 $Z[J]$ と古典・量子統計力学の**分配関数（Partition Function）** $Z[h]$ は、数学的にも物理的にも完全に一対一で対応しています。

### 5.1 ウィック回転（Wick Rotation）による結びつき

実時間 $t$ を虚時間 $\tau = i t$ に解析接続する**ウィック回転**を行うと、ミンコフスキー空間の経路積分はユーグリッド空間の統計力学的な配置空間積分に化けます：

$$
e^{i S_\mathrm{Minkowski}} \xrightarrow{t \to -i\tau} e^{- S_\mathrm{Euclidean}}
$$

量子場理論における「量子揺らぎ（位相の干渉 $e^{iS/\hbar}$）」が、統計力学における「熱揺らぎ（ボルツマン因子 $e^{-\beta H}$）」に数学的に写し取られます。

### 5.2 概念の対比表

| 物理量 / 概念 | 場の量子論（QFT） | 統計力学（Statistical Mechanics） |
| :--- | :--- | :--- |
| **基本変数** | 量子場 $\phi(x)$ | スピン/場の配置 $s(x)$ や位置・運動量 |
| **外部応答の源** | 外源 $J(x)$ | 外部場 $h(x)$（例: 外部磁場） |
| **分配関数** | 生成汎関数 $Z[J] = \int \mathcal{D}\phi \, e^{i S[\phi, J]}$ | 大分配関数 $Z[h] = \sum e^{-\beta (H - h \cdot s)}$ |
| **確率重み** | 量子振幅位相 $e^{i S/\hbar}$ | ボルツマン因子 $e^{-\beta H}$ |
| **1点関数** | 真空期待値 $\langle 0 \| \hat{\phi}(x) \| 0 \rangle = \frac{-i}{Z} \frac{\delta Z}{\delta J(x)}$ | 平均磁化 $\langle s(x) \rangle = \frac{1}{\beta Z} \frac{\delta Z}{\delta h(x)}$ |
| **2点関数** | プロパゲータ/伝播関数 $D_F(x-y)$ | 2点スピン相関関数 $\langle s(x) s(y) \rangle$ |
| **連結汎関数** | $W[J] = -i \ln Z[J]$ (連結 Green 関数生成) | 自由エネルギー $F[h] = -k_B T \ln Z[h]$ |
| **有効作用** | 巨視的有効作用 $\Gamma[\phi_c]$（ルジャンドル変換） | ギブス自由エネルギー / 熱力学ポテンシャル |

### 5.3 直観的物理像の要約

1. **統計力学での視点**:
   外磁場 $h$ を少しいじった時の応答（応答関数・感受率・相関関数）を見るために $Z[h]$ を作り、$h$ で微分して最後に $h=0$ に戻す。
2. **QFTでの視点**:
   時空の各点 $x$ に仮想的な外源 $J(x)$（粒子を生成・消滅させる古典的な源）を置き、システムがどう応答するか（粒子がどのように伝播して散乱するか）を見るために $Z[J]$ を作り、$J$ で汎関数微分して最後に $J=0$ に戻す。

この意味で、**生成汎関数は「量子場の統計力学における分配関数そのもの」** であると言えます。
