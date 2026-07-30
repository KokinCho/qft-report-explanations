# 相互作用描像（Interaction Picture）とゲルマン＝ローの公式の物理的お気持ち＆定量的導出

「なぜ物理量を計算する際に相互作用描像でなければならないのか？」
「なぜ $\langle \Omega | T \hat{\phi}_H \cdots | \Omega \rangle$ が $\langle 0 | T \{ \hat{\phi}_I \cdots e^{-i \int \mathcal{H}_{\text{int}} \mathrm{d}^4x} \} | 0 \rangle$ の形に書けるのか？」

という疑問に対する、物理的お気持ちと定量的導出の完全解説です。

---

## 1. なぜ相互作用描像（Interaction Picture）でなきゃいけないのか？（本質的なお気持ち）

量子力学における 3 つの描像（Picture）の役割を整理すると、相互作用描像を採用する必然性が一目瞭然になります。

### 各描像の比較

1. **シュレディンガー描像**:
   - 演算子 $\hat{O}_S$ は一定。
   - 状態 $|\psi_S(t)\rangle$ が全ハミルトニアン $\hat{H} = \hat{H}_0 + \hat{H}_{\text{int}}$ で極めて複雑に時間発展する。
2. **ハイゼンベルク描像**:
   - 状態 $|\Omega\rangle$（フル理論の真空）は一定。
   - 演算子 $\hat{\phi}_H(t) = e^{i\hat{H}t} \hat{\phi}_S e^{-i\hat{H}t}$ が全ハミルトニアン $\hat{H}$ で時間発展する。
   - **【最大の問題点】**: 全ハミルトニアン $\hat{H}$ による時間発展は非線形かつ厳密に解けないため、演算子 $\hat{\phi}_H(t)$ を生成消滅演算子 $a_{\mathbf{p}}, a_{\mathbf{p}}^\dagger$ で具体的に展開することが不可能です！ したがって、**Wickの定理（自由場の交換関係による縮約）が一切使えません**。

3. **相互作用描像（Interaction Picture）の誕生**:
   - 演算子の時間発展を、**厳密に解ける自由ハミルトニアン $\hat{H}_0$ だけ** で行わせる：
     $$ \hat{\phi}_I(t) \equiv e^{i\hat{H}_0 t} \hat{\phi}_S e^{-i\hat{H}_0 t} $$
     これにより、場 $\hat{\phi}_I(t)$ は**自由場としての生成消滅演算子で完全に展開可能**になり、**Wickの定理（プロパゲータへの縮約）が 100% 使える**ようになります！
   - 一方で、解けない「相互作用 $\hat{H}_{\text{int}}$」による時間発展は、**時間発展演算子 $\hat{U}(t, t_0)$ の中に閉じ込め、結合定数 $\lambda$ について Taylor 展開（摂動論）する**！

> **【直観的要約】**
> 「手も足も出ないフル理論の場 $\hat{\phi}_H$ を、数学的に完全にコントロールできる自由場 $\hat{\phi}_I$ と、指数関数の中に封じ込めた相互作用 $\hat{H}_{\text{int}}$ の積に分解して計算可能にするための唯一のフレームワーク」が相互作用描像です。

---

## 2. ゲルマン＝ローの公式（Gell-Mann–Low Formula）の定量的導出

求めたい本質的な物理量は、相互作用のあるフル理論の真空 $|\Omega\rangle$ におけるハイゼンベルク演算子の $T$ 積真空期待値（相関関数）です：

$$
G^{(n)} = \langle \Omega | \mathrm{T} \{ \hat{\phi}_H(x_1) \cdots \hat{\phi}_H^\dagger(y_1) \} | \Omega \rangle
$$

これを自由真空 $|0\rangle$ と相互作用描像演算子 $\hat{\phi}_I$ に書き換えるステップを追います。

---

### Step 1: 時間発展演算子 $\hat{U}(t, t_0)$ とハイゼンベルク演算子の関係

相互作用描像の時間発展演算子 $\hat{U}(t, t_0)$ は、自由ハミルトニアン $\hat{H}_0$ と全ハミルトニアン $\hat{H} = \hat{H}_0 + \hat{H}_{\text{int}}$ を用いて次のように定義されます：

$$
\hat{U}(t, t_0) \equiv e^{i \hat{H}_0 t} e^{-i \hat{H} (t-t_0)} e^{-i \hat{H}_0 t_0} = \mathrm{T} \exp\left( -i \int_{t_0}^t \mathrm{d}t' \hat{H}_{\text{int}}^I(t') \right)
$$

この $\hat{U}$ を使うと、ハイゼンベルク演算子 $\hat{\phi}_H(t)$ と相互作用描像演算子 $\hat{\phi}_I(t)$ の関係は：

$$
\hat{\phi}_H(t) = e^{i \hat{H} t} \hat{\phi}_S e^{-i \hat{H} t} = \hat{U}(0, t) \, \hat{\phi}_I(t) \, \hat{U}(t, 0)
$$

となります（ただし $\hat{U}(0, t) = \hat{U}(t, 0)^\dagger = \hat{U}(t, 0)^{-1}$）。

---

### Step 2: 時間順序積 $\mathrm{T}$ の中での時間発展演算子の合成

演算子の積に時間順序積 $\mathrm{T}$ を被せます。時刻が $t_1 > t_2$ の場合：

$$
\hat{\phi}_H(t_1) \hat{\phi}_H(t_2) = \left[ \hat{U}(0, t_1) \hat{\phi}_I(t_1) \hat{U}(t_1, 0) \right] \left[ \hat{U}(0, t_2) \hat{\phi}_I(t_2) \hat{U}(t_2, 0) \right]
$$

中央の $\hat{U}(t_1, 0) \hat{U}(0, t_2)$ は演算子の加法性により $\hat{U}(t_1, t_2)$ と結合します。
これを任意の時刻群 $t_1, t_2, \dots, t_n$ に拡張し、十分大きな時間 $[-T, T]$ を取ると、時間順序積 $\mathrm{T}$ の作用によって時間発展演算子がひとつにつながり、以下のようにまとめられます：

$$
\mathrm{T} \{ \hat{\phi}_H(x_1) \cdots \hat{\phi}_H(x_n) \} = \hat{U}(0, T) \, \mathrm{T} \left\{ \hat{\phi}_I(x_1) \cdots \hat{\phi}_I(x_n) \, \exp\left( -i \int_{-T}^T \mathrm{d}t \, \hat{H}_{\text{int}}^I(t) \right) \right\} \hat{U}(-T, 0)
$$

---

### Step 3: フル真空 $|\Omega\rangle$ と自由真空 $|0\rangle$ の接続（$i\epsilon$ 処方）

遠い過去 $t \to -\infty(1-i\epsilon)$ において、システムを自由真空 $|0\rangle$ から時間発展させます。
自由真空 $|0\rangle$ をフルハミルトニアン $\hat{H}$ の固有状態 $|n\rangle$（固有値 $E_n$、基底状態を $|\Omega\rangle$ とおく）で展開すると：

$$
e^{-i \hat{H} T (1-i\epsilon)} |0\rangle = e^{-i E_\Omega T(1-i\epsilon)} |\Omega\rangle \langle \Omega | 0 \rangle + \sum_{n \neq \Omega} e^{-i E_n T(1-i\epsilon)} |n\rangle \langle n | 0 \rangle
$$

$T \to \infty$ の極限において、励起状態の因子 $e^{-\epsilon E_n T}$ は基底状態 $e^{-\epsilon E_\Omega T}$ に比べて急速に減衰して消滅します。
これにより、時間発展させた自由真空は**フル真空 $|\Omega\rangle$ に比例（射影）** します：

$$
|\Omega\rangle = \lim_{T \to \infty(1-i\epsilon)} \frac{\hat{U}(0, -T) |0\rangle}{e^{-i E_\Omega T} \langle \Omega | 0 \rangle}
$$

$$
\langle \Omega| = \lim_{T \to \infty(1-i\epsilon)} \frac{\langle 0| \hat{U}(T, 0)}{e^{-i E_\Omega T} \langle 0 | \Omega \rangle}
$$

---

### Step 4: ゲルマン＝ローの公式の完成と 1 次項の抽出

Step 2 と Step 3 を組み合わせると、分母の規格化因子によって未知の位相因子 $\langle 0 | \Omega \rangle$ や $e^{-i E_\Omega T}$ が全てキャンセルし、**ゲルマン＝ローの公式（Gell-Mann–Low Formula）** が導出されます：

$$
\langle \Omega | \mathrm{T} \{ \hat{\phi}_H(x_1) \cdots \hat{\phi}_H^\dagger(y_1) \} | \Omega \rangle = \frac{\langle 0 | \mathrm{T} \left\{ \hat{\phi}_I(x_1) \cdots \hat{\phi}_I^\dagger(y_1) \exp\left( -i \int_{-\infty}^{\infty} \mathrm{d}^4x \mathcal{H}_{\text{int}}^I(x) \right) \right\} | 0 \rangle}{\langle 0 | \mathrm{T} \exp\left( -i \int_{-\infty}^{\infty} \mathrm{d}^4x \mathcal{H}_{\text{int}}^I(x) \right) | 0 \rangle}
$$

#### 4点相関関数の 1 次項 $\mathcal{O}(\lambda^1)$ の取り出し
複素スカラー場において $\mathcal{H}_{\text{int}}^I(x) = \lambda (\hat{\phi}_I^\dagger(x) \hat{\phi}_I(x))^2$ です。
分子の指数関数 $\exp\left( -i \int \mathcal{H}_{\text{int}}^I \mathrm{d}^4x \right)$ を $\lambda$ について 1 次まで Taylor 展開（$e^x \approx 1 + x$）すると、分子の 1 次項としてまさに以下の式が得られます：

$$
\langle 0 | \mathrm{T} \left\{ \hat{\phi}_I(z_1) \hat{\phi}_I(z_2) \hat{\phi}_I^\dagger(w_1) \hat{\phi}_I^\dagger(w_2) \, \left( -i \lambda \int \mathrm{d}^4x (\hat{\phi}_I^\dagger(x) \hat{\phi}_I(x))^2 \right) \right\} | 0 \rangle
$$

これで、**「なぜ相互作用描像でなければならず、なぜこの形に書けるのか」の論理の全貌が完全に解明**されました。
