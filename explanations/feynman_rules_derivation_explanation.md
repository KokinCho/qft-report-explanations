# 相互作用生成汎関数からのファインマン・ルール導出の完全解説

## 1. マスター公式と摂動展開（Taylor 展開）

相互作用 $\mathcal{L}_{\text{int}} = -\lambda (\phi^* \phi)^2$ を持つ複素スカラー場理論の生成汎関数マスター公式は次の通りです：

$$
Z[J, J^*] = \exp\left\{ -i \lambda \int \mathrm{d}^4x \left( \frac{\delta}{i \delta J(x)} \frac{\delta}{i \delta J^*(x)} \right)^2 \right\} Z_0[J, J^*]
$$

この公式の指数関数演算子を結合定数 $\lambda$ について Taylor 展開します：

$$
Z[J, J^*] = \sum_{V=0}^{\infty} \frac{1}{V!} \left[ -i \lambda \int \mathrm{d}^4x \left( \frac{\delta}{i \delta J(x)} \frac{\delta}{i \delta J^*(x)} \right)^2 \right]^V Z_0[J, J^*]
$$

この展開式の各要素が、ファインマン・ダイアグラムの構成要素（頂点・線・外線）に直接対応しています。

---

## 2. ファインマン・ルールの各要素の微視的導出

### 2.1 頂点因子（Vertex Factor）の導出

展開式の第 $V$ 次の項には、$V$ 個の時空点 $x_1, x_2, \dots, x_V$ における積分が現れます。
各時空点 $x$ における基本的な微分演算子の固まりは以下の通りです：

$$
-i \lambda \int \mathrm{d}^4x \left( \frac{\delta}{i \delta J(x)} \right)^2 \left( \frac{\delta}{i \delta J^*(x)} \right)^2
$$

1. **演算子の構造**:
   - $\phi^*(x)$ に対応する $\frac{\delta}{i \delta J(x)}$ が **2 個**
   - $\phi(x)$ に対応する $\frac{\delta}{i \delta J^*(x)}$ が **2 個**
   時空点 $x$ から計 4 本の線（伝播関数）が出入りする **4 点頂点** を形成します。

2. **同等な繋ぎ方の重複度（対称性係数）**:
   頂点 $x$ において、2 つの流入線（$\phi^*$ 由来）の繋ぎ替え（入れ替え）が $2! = 2$ 通り、2 つの流出線（$\phi$ 由来）の繋ぎ替えが $2! = 2$ 通り存在します。
   これらは全く同等なダイアグラムを与えるため、係数として **$2! \times 2! = 4$** 倍のファクターが生じます。

3. **頂点値の確定**:
   したがって、ミンコフスキー時空における 1 つの 4 点頂点の重み（Vertex Factor）は：

   $$
   (-i \lambda) \times 4 = \mathbf{-i 4\lambda}
   $$

   となります。
   （ユークリッド時空では、作用の位相が $- S_{E, \text{int}} = -\int \lambda (\phi_E^* \phi_E)^2$ となるため、頂点値は $\mathbf{-4\lambda}$ となります。）

---

### 2.2 伝播関数（Propagator / 矢印線）の導出

自由生成汎関数の具体的な形は以下の通りです：

$$
Z_0[J, J^*] = \exp\left\{ -i \int \mathrm{d}^4u \, \mathrm{d}^4v \, J^*(u) D_F(u-v) J(v) \right\}
$$

頂点演算子中の $\frac{\delta}{i \delta J^*(x)}$ と別の頂点演算子中の $\frac{\delta}{i \delta J(y)}$ が $Z_0[J, J^*]$ に作用してペア（縮約 / Wick 縮約）を作るとき：

$$
\left. \frac{\delta^2 Z_0[J, J^*]}{i \delta J^*(x) i \delta J(y)} \right|_{J=J^*=0} = i D_F(x-y)
$$

1. **内積と伝播関数の表示**:
   この微分演算によって、時空点 $y$ と時空点 $x$ を結ぶ因子 **$i D_F(x-y)$** （運動量空間では $\frac{i}{p^2 - m_0^2 + i\epsilon}$）が切り出されます。

2. **矢印（電荷のフロー）の向き**:
   - $J(y)$（$\phi^*(y)$ の源）から微分され、$J^*(x)$（$\phi(x)$ の源）へと微分が作用するため、伝播関数は **$y$ から $x$ へ向かう有向線（矢印付きの線）** として描かれます。
   - これは複素スカラー場における $U(1)$ 電荷（または粒子数）の流れる方向を物理的に表しています。

---

### 2.3 外線（External lines）とダイアグラムの連結性

$n$ 点相関関数 $\langle 0 | T \hat{\phi}(z_1) \dots \hat{\phi}^*(w_1) \dots | 0 \rangle$ を計算する際は、生成汎関数 $Z[J, J^*]$ に対して外部位置 $z_1, w_1$ で汎関数微分を行い、最後に $J = J^* = 0$ とおきます。

1. **外線の付着**:
   外部からの微分 $\frac{\delta}{i \delta J^*(z)}$ は外線 $\phi(z)$ に対応し、$Z_0$ 内の源 $J$ を微分して頂点または他の外線と結びつくプロパゲータ $i D_F(z-x)$ を生み出します。
2. **ダイアグラムの完成**:
   未微分の $J$ や $J^*$ が残っている項は $J=J^*=0$ で全て消滅するため、外線および頂点の間がプロパゲータで完全に繋がれた **ファインマン・ダイアグラムの和** のみが生存します。

---

## 3. まとめ：導出操作の対比フロー

$$
\begin{aligned}
\text{全生成汎関数 } Z[J, J^*] &\xrightarrow{\text{相互作用演算子の引き出し}} \exp\left( -i \lambda \int \left(\frac{\delta}{i\delta J}\frac{\delta}{i\delta J^*}\right)^2 \right) Z_0[J, J^*] \\
&\xrightarrow{\lambda \text{ の Taylor 展開}} \sum_{V=0}^{\infty} \frac{(-i\lambda)^V}{V!} \int \left[ \text{頂点演算子} \right]^V Z_0[J, J^*] \\
&\xrightarrow{Z_0 \text{ への微分と Wick 縮約}} \sum \text{(頂点因子 } -i4\lambda \text{)} \times \text{(伝播関数 } i D_F \text{)} \times \text{(同相性ファクター)}
\end{aligned}
$$

この操作手順が、任意の場の理論において作用汎関数からファインマン・ルールが代数的に自動導出されるメカニズムです。
