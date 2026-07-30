# 相互作用描像の時間発展演算子等式 $T \exp\left(i \int J\hat{\phi}\right) = e^{i H_0 t_f} e^{-i H[J](t_f-t_i)} e^{-i H_0 t_i}$ の数学的完全証明

質問：
$$
T \exp\left( i \int_{t_i}^{t_f} \mathrm{d}^4 x \, J(x) \hat{\phi}(x) \right) = e^{i \hat{H}_0 t_f} e^{-i \hat{H}[J](t_f - t_i)} e^{-i \hat{H}_0 t_i}
$$
「この等式はどうやって示されるのか？定義なのか？BCH公式を使うのか？」

---

## 1. 結論

この等式は「単なる公理的定義」でも「BCH公式による展開」でもなく、**「微分方程式の解の唯一性（Schrödinger 方程式 / Tomonaga-Schwinger 方程式）」** を用いて数学的に厳密に代数証明されます。

---

## 2. 厳密な導出証明ステップ

### 設定と定義

1. 自由ハミルトニアン： $\hat{H}_0$
2. 外源ハミルトニアン（シュレディンガー描像）： $\hat{H}_{\text{int}}^S(t) = -\int \mathrm{d}^3x \, J(t, \mathbf{x}) \hat{\phi}_S(\mathbf{x})$
3. フルハミルトニアン： $\hat{H}[J](t) = \hat{H}_0 + \hat{H}_{\text{int}}^S(t)$
4. 相互作用描像での演算子：
   $$
   \hat{\phi}_I(t, \mathbf{x}) = e^{i \hat{H}_0 t} \hat{\phi}_S(\mathbf{x}) e^{-i \hat{H}_0 t}
   $$
   $$
   \hat{H}_{\text{int}}^I(t) = e^{i \hat{H}_0 t} \hat{H}_{\text{int}}^S(t) e^{-i \hat{H}_0 t} = -\int \mathrm{d}^3x \, J(t, \mathbf{x}) \hat{\phi}_I(t, \mathbf{x})
   $$

---

### Step 1: 左辺（$T$ 積演算子）が満たす微分方程式

左辺の演算子を $\hat{U}_I(t, t_i) \equiv \mathrm{T} \exp\left( -i \int_{t_i}^t \mathrm{d}t' \, \hat{H}_{\text{int}}^I(t') \right)$ とおきます。

時間順序積 $\mathrm{T}$ の微分法則（Dyson 級数の微分の定義）により、$\hat{U}_I(t, t_i)$ は以下の **Tomonaga-Schwinger（朝永-シュウィンガー）方程式** を満たします：

$$
\frac{\mathrm{d}}{\mathrm{d}t} \hat{U}_I(t, t_i) = -i \hat{H}_{\text{int}}^I(t) \hat{U}_I(t, t_i) \qquad \text{（初期条件: } \hat{U}_I(t_i, t_i) = \mathbb{I} \text{）} \tag{1}
$$

---

### Step 2: フル時間発展演算子 $\hat{U}_{\text{full}}(t, t_i)$ が満たす微分方程式

シュレディンガー描像での全ハミルトニアン $\hat{H}[J](t) = \hat{H}_0 + \hat{H}_{\text{int}}^S(t)$ によるフル時間発展演算子 $\hat{U}_{\text{full}}(t, t_i) = e^{-i \hat{H}[J](t - t_i)}$ は、通常の Schrödinger 方程式を満たします：

$$
\frac{\mathrm{d}}{\mathrm{d}t} \hat{U}_{\text{full}}(t, t_i) = -i \hat{H}[J](t) \hat{U}_{\text{full}}(t, t_i) = -i (\hat{H}_0 + \hat{H}_{\text{int}}^S(t)) \hat{U}_{\text{full}}(t, t_i) \qquad \text{（初期条件: } \hat{U}_{\text{full}}(t_i, t_i) = \mathbb{I} \text{）} \tag{2}
$$

---

### Step 3: 右辺の演算子 $\hat{W}(t, t_i)$ の $t$ 微分の直接計算

右辺の形の演算子を $\hat{W}(t, t_i) \equiv e^{i \hat{H}_0 t} \hat{U}_{\text{full}}(t, t_i) e^{-i \hat{H}_0 t_i}$ と定義し、時刻 $t$ で直接微分（積の微分法則）を行います：

$$
\begin{aligned}
\frac{\mathrm{d}}{\mathrm{d}t} \hat{W}(t, t_i) &= \frac{\mathrm{d}}{\mathrm{d}t} \left[ e^{i \hat{H}_0 t} \hat{U}_{\text{full}}(t, t_i) e^{-i \hat{H}_0 t_i} \right] \\
&= \left( \frac{\mathrm{d}}{\mathrm{d}t} e^{i \hat{H}_0 t} \right) \hat{U}_{\text{full}}(t, t_i) e^{-i \hat{H}_0 t_i} + e^{i \hat{H}_0 t} \left( \frac{\mathrm{d}}{\mathrm{d}t} \hat{U}_{\text{full}}(t, t_i) \right) e^{-i \hat{H}_0 t_i} \\
&= \left( i \hat{H}_0 e^{i \hat{H}_0 t} \right) \hat{U}_{\text{full}}(t, t_i) e^{-i \hat{H}_0 t_i} + e^{i \hat{H}_0 t} \left( -i (\hat{H}_0 + \hat{H}_{\text{int}}^S(t)) \hat{U}_{\text{full}}(t, t_i) \right) e^{-i \hat{H}_0 t_i}
\end{aligned}
$$

第 2 項を展開します：

$$
= i \hat{H}_0 e^{i \hat{H}_0 t} \hat{U}_{\text{full}} e^{-i \hat{H}_0 t_i} - i \hat{H}_0 e^{i \hat{H}_0 t} \hat{U}_{\text{full}} e^{-i \hat{H}_0 t_i} - i e^{i \hat{H}_0 t} \hat{H}_{\text{int}}^S(t) \hat{U}_{\text{full}}(t, t_i) e^{-i \hat{H}_0 t_i}
$$

見事に第 1 項と第 2 項の $i \hat{H}_0$ の項が**相殺して消滅**します！

残った項の中間に 恒等演算子 $\mathbb{I} = e^{-i \hat{H}_0 t} e^{i \hat{H}_0 t}$ を挿入します：

$$
\begin{aligned}
\frac{\mathrm{d}}{\mathrm{d}t} \hat{W}(t, t_i) &= -i \left( e^{i \hat{H}_0 t} \hat{H}_{\text{int}}^S(t) e^{-i \hat{H}_0 t} \right) \left( e^{i \hat{H}_0 t} \hat{U}_{\text{full}}(t, t_i) e^{-i \hat{H}_0 t_i} \right) \\
&= -i \hat{H}_{\text{int}}^I(t) \hat{W}(t, t_i) \tag{3}
\end{aligned}
$$

さらに初期条件を確認すると：
$$
\hat{W}(t_i, t_i) = e^{i \hat{H}_0 t_i} \mathbb{I} e^{-i \hat{H}_0 t_i} = \mathbb{I} \tag{4}
$$

---

### Step 4: 唯一性による等式の完了

(1) 式と (3) 式、および初期条件 (4) 式を比較すると、演算子 $\hat{U}_I(t, t_i)$ と $\hat{W}(t, t_i)$ は：
1. **全く同一の一階線形演算子微分方程式** $\frac{\mathrm{d}}{\mathrm{d}t} \hat{X}(t) = -i \hat{H}_{\text{int}}^I(t) \hat{X}(t)$ を満たす。
2. **全く同一の初期条件** $\hat{X}(t_i) = \mathbb{I}$ を満たす。

一階微分方程式の解の唯一性定理により、すべての時刻 $t = t_f$ において両者は恒等的に一致します：

$$
\mathrm{T} \exp\left( -i \int_{t_i}^{t_f} \mathrm{d}t' \, \hat{H}_{\text{int}}^I(t') \right) = e^{i \hat{H}_0 t_f} e^{-i \hat{H}[J](t_f - t_i)} e^{-i \hat{H}_0 t_i}
$$

相互作用描像のハミルトニアン $\hat{H}_{\text{int}}^I(t') = -\int \mathrm{d}^3x \, J(t', \mathbf{x}) \hat{\phi}_I(t', \mathbf{x})$ を代入することで、示したい等式が完全に証明されました：

$$
\mathrm{T} \exp\left( i \int_{t_i}^{t_f} \mathrm{d}^4 x \, J(x) \hat{\phi}(x) \right) = e^{i \hat{H}_0 t_f} e^{-i \hat{H}[J](t_f - t_i)} e^{-i \hat{H}_0 t_i}
$$
