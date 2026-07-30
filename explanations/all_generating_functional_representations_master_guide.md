# 場の量子論における生成汎関数 $Z[J]$ の全同値表現マスターガイド

場の量子論において、生成汎関数 $Z[J]$ は目的・視点（演算子形式・経路積分・相互作用描像・ユークリッド空間・熱力学対比）に応じて**さまざまな同値な数学的表現**で書き直されます。

以下にすべての代表的同値表現を体系的に網羅・分類して列挙します。

---

## 1. 演算子形式（正準量子化）における表現

### ① $T$ 積真空期待値表示（基本定義）
ハイゼンベルク描像の場の演算子 $\hat{\phi}_H(x)$ と古典外源 $J(x)$ の積の時間順序積の真空期待値：

$$
Z[J] = \langle 0 | \mathrm{T} \exp\left( i \int \mathrm{d}^4x \, J(x) \hat{\phi}_H(x) \right) | 0 \rangle
$$

*(複素スカラー場: $Z[J, J^*] = \langle 0 | \mathrm{T} \exp\left( i \int \mathrm{d}^4x [J^* \hat{\phi}_H + J \hat{\phi}_H^\dagger] \right) | 0 \rangle$)*

### ② 真空ー真空遷移振幅表示（In-Out 振幅）
過去の真空 $|0, \text{in}\rangle$ から未来の真空 $|0, \text{out}\rangle$ への外源 $J$ 存在下での S 行列要素：

$$
Z[J] = \langle 0, \text{out} | 0, \text{in} \rangle_J
$$

### ③ フルハミルトニアン $\hat{H}[J]$ による時間発展表示
外源ハミルトニアン $\hat{H}[J] = \hat{H}_0 - \int \mathrm{d}^3x J\hat{\phi}$ によるフル時間発展演算子の期待値：

$$
Z[J] = \lim_{t_f \to \infty(1-i\epsilon), t_i \to -\infty(1-i\epsilon)} \langle 0 | e^{i \hat{H}_0 t_f} e^{-i \hat{H}[J](t_f - t_i)} e^{-i \hat{H}_0 t_i} | 0 \rangle
$$

---

## 2. 相互作用描像（Interaction Picture）における表現

### ④ 相互作用演算子の $T$ 積表示（Gell-Mann–Low 型）
自由場の演算子 $\hat{\phi}_I(x)$ と相互作用ハミルトニアン $\mathcal{H}_{\text{int}}^I$ による規格化表示：

$$
Z[J] = \frac{\langle 0 | \mathrm{T} \exp\left( -i \int \mathrm{d}^4x \, \mathcal{H}_{\text{int}}^I(x) + i \int \mathrm{d}^4x \, J(x) \hat{\phi}_I(x) \right) | 0 \rangle}{\langle 0 | \mathrm{T} \exp\left( -i \int \mathrm{d}^4x \, \mathcal{H}_{\text{int}}^I(x) \right) | 0 \rangle}
$$

### ⑤ マスター微分演算子表示（相互作用項の引き出し）
相互作用ラグランジアン $\mathcal{L}_{\text{int}}$ の場 $\phi$ を微分演算子 $\frac{\delta}{i\delta J}$ に置換して積分の外に出した表現：

$$
Z[J] = \exp\left\{ i \int \mathrm{d}^4x \, \mathcal{L}_{\text{int}}\left( \frac{\delta}{i\delta J(x)} \right) \right\} Z_0[J]
$$

*(複素スカラー $\lambda(\phi^*\phi)^2$ 理論: $Z[J, J^*] = \exp\left\{ -i \int \mathrm{d}^4x \, \lambda \left( \frac{\delta}{i\delta J(x)} \frac{\delta}{i\delta J^*(x)} \right)^2 \right\} Z_0[J, J^*]$)*

---

## 3. 経路積分形式（ミンコフスキー時空）における表現

### ⑥ 全作用 $S[\phi]$ による汎関数積分表示
時空全体の古典場の全配置にわたる位相ファクター $e^{iS}$ の積分：

$$
Z[J] = \frac{1}{\mathcal{N}} \int \mathcal{D}\phi \, \exp\left\{ i \int \mathrm{d}^4x \left( \mathcal{L}_0(\phi) + \mathcal{L}_{\text{int}}(\phi) + J(x)\phi(x) + i\epsilon \phi^2 \right) \right\}
$$

### ⑦ 自由場（$\mathcal{L}_{\text{int}}=0$）の平方完成表示（閉じた解）
ガウス汎関数積分を平方完成して厳密に求積した解（ファインマン伝播関数 $D_F$ を用いた表示）：

- 実スカラー場:
  $$ Z_0[J] = \exp\left( -\frac{i}{2} \int \mathrm{d}^4x \, \mathrm{d}^4y \, J(x) D_F(x-y) J(y) \right) $$
- 複素スカラー場:
  $$ Z_0[J, J^*] = \exp\left( -i \int \mathrm{d}^4x \, \mathrm{d}^4y \, J^*(x) D_F(x-y) J(y) \right) $$

### ⑧ 2点 $T$ 積真空期待値（プロパゲータ）代入表示
$i D_F(x-y) = \langle 0 | \mathrm{T} \hat{\phi}(x) \hat{\phi}^\dagger(y) | 0 \rangle$ を用いて期待値で書き直した表現：

$$
Z_0[J, J^*] = \exp\left( -\int \mathrm{d}^4x \, \mathrm{d}^4y \, J^*(x) \langle 0 | \mathrm{T} \hat{\phi}(x) \hat{\phi}^\dagger(y) | 0 \rangle J(y) \right)
$$

---

## 4. ユークリッド時空（虚時間 $\tau = i t$）における表現

### ⑨ ユークリッド汎関数積分表示
ウィック回転により統計力学的な正定値ボルツマン因子形式に化けた表現：

$$
Z_E[J] = \frac{1}{\mathcal{N}_E} \int \mathcal{D}\phi_E \, \exp\left\{ - \int \mathrm{d}^4x_E \left( \mathcal{L}_{0,E}(\phi_E) + \mathcal{L}_{\text{int},E}(\phi_E) - J_E(x_E)\phi_E(x_E) \right) \right\}
$$

### ⑩ ユークリッド自由場表示（解）
ユークリッド・プロパゲータ $G_0(x_E - y_E)$ による求積解：

$$
Z_{0,E}[J, J^*] = \exp\left( \int \mathrm{d}^4x_E \, \mathrm{d}^4y_E \, J^*(x_E) G_0(x_E - y_E) J(y_E) \right)
$$

### ⑪ ユークリッド・マスター微分演算子表示

$$
Z_E[J, J^*] = \exp\left\{ - \int \mathrm{d}^4x_E \, \lambda \left( \frac{\delta}{\delta J(x_E)} \frac{\delta}{\delta J^*(x_E)} \right)^2 \right\} Z_{0,E}[J, J^*]
$$

---

## 5. 相関関数・連結関数・有効作用との関係表現

### ⑫ モーメント展開（全 $n$ 点関数の Taylor 級数）表示
微分によって $n$ 点関数を取り出す構造の Taylor 展開：

$$
Z[J] = \sum_{n=0}^{\infty} \frac{i^n}{n!} \int \mathrm{d}^4x_1 \dots \mathrm{d}^4x_n \, J(x_1) \dots J(x_n) \, \langle 0 | \mathrm{T} \hat{\phi}(x_1) \dots \hat{\phi}(x_n) | 0 \rangle
$$

### ⑬ 連結生成汎関数 $W[J]$ による表示
非連結なバブルダイアグラムを除去し、連結ダイアグラムのみを生成する汎関数 $W[J]$ による表現：

$$
Z[J] = \exp\left( i W[J] \right) \qquad \iff \qquad W[J] = -i \ln Z[J]
$$

### ⑭ 有効作用 $\Gamma[\phi_c]$（1PI 既約ダイアグラム）のルジャンドル変換表示
古典場期待値 $\phi_c(x) \equiv \frac{\delta W[J]}{\delta J(x)}$ に対するルジャンドル変換：

$$
Z[J] = \exp\left\{ i \Gamma[\phi_c] + i \int \mathrm{d}^4x \, J(x) \phi_c(x) \right\}
$$

---

## 全対応の要約マップ

```
【定義】 Z[J] = <0| T exp(i ∫ J φ) |0>  [① 演算子定義]
   ∥ (Dyson/Gell-Mann-Low)
【相互作用描像】 Z[J] = <0| T exp(-i ∫ H_int + i ∫ J φ_I) |0> / <0| T exp(-i ∫ H_int) |0>  [④]
   ∥ (時間分割・完全系挿入)
【経路積分】 Z[J] = ∫ Dφ exp(i S[φ] + i ∫ J φ)  [⑥ 作用表示]
   ∥ (λ=0 の平方完成)
【自由場解】 Z0[J] = exp(-i ∫ J D_F J) = exp(- ∫ J <0|T φ φ†|0> J)  [⑦, ⑧]
   ∥ (相互作用項の引き出し)
【マスター公式】 Z[J] = exp(i ∫ L_int(δ/iδJ)) Z0[J]  [⑤]
   ∥ (ウィック回転 t → -iτ)
【ユークリッド】 ZE[J] = ∫ DφE exp(- S_E + ∫ J_E φ_E)  [⑨]
   ∥ (対数・ルジャンドル変換)
【連結・有効作用】 Z[J] = exp(i W[J]) = exp(i Γ[φ_c] + i ∫ J φ_c)  [⑬, ⑭]
```
