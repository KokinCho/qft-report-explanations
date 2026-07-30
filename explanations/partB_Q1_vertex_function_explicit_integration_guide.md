# 4 点頂点関数 $\Gamma^{(4)}$ とバブル積分 $V(q)$ の具体的大系計算ガイド

本ドキュメントは、**「$V(q)$ の Feynman パラメータ積分の実行難易度」**、**「次元正則化 $D = 4 - 2\epsilon$ における $V(q)$ の具体的な展開結果」**、および **「1PI 4 点頂点関数 $\Gamma^{(4)}$ に代入して得られる物理的・有限な最終結果」** を完全網羅した解説ドキュメントです。

---

## 1. 積分 $V(q)$ を実行するのは大変か？

**結論：難易度は高くありません（非常に標準的かつ明快です）。**

$D = 4 - 2\epsilon$ （$\epsilon \to 0^+$）の次元正則化のもとで、積分：

$$V(q) = \frac{\Gamma\left( 2 - \frac{D}{2} \right)}{(4\pi)^{D/2}} \mu^{4-D} \int_0^1 \mathrm{d}x \left[ m^2 + x(1-x)q^2 \right]^{D/2 - 2}$$

（※ 任意質量スケール $\mu$ は無次元化のための標準的な調整因子）を計算する際、指数の部分が：

$$\frac{D}{2} - 2 = \frac{4 - 2\epsilon}{2} - 2 = -\epsilon$$

となるため、極限 $\epsilon \to 0$ での展開式 $A^{-\epsilon} = e^{-\epsilon \ln A} = 1 - \epsilon \ln A + \mathcal{O}(\epsilon^2)$ が適用できます。

---

## 2. $V(q)$ の具体例・ステップバイステップ計算

### ステップ 1: ガンマ関数 $\Gamma(\epsilon)$ の Laurent 展開
オイラーのガンマ関数は $\epsilon \to 0$ で以下の極展開を持ちます：

$$\Gamma(\epsilon) = \frac{1}{\epsilon} - \gamma + \mathcal{O}(\epsilon) \quad (\gamma \approx 0.5772 \text{ は Euler-Mascheroni 定数})$$

### ステップ 2: 被積分関数の展開
$$(4\pi)^{-D/2} \mu^{2\epsilon} \left[ m^2 + x(1-x)q^2 \right]^{-\epsilon} = \frac{1}{16\pi^2} \left[ 1 + \epsilon \ln(4\pi) + \epsilon \ln\mu^2 - \epsilon \ln\left( m^2 + x(1-x)q^2 \right) + \mathcal{O}(\epsilon^2) \right]$$

### ステップ 3: 積分の組み合わせ
以上を掛け合わせると、$\frac{1}{\epsilon}$ の高次項を無視して以下の綺麗な展開が得られます：

$$V(q) = \frac{1}{16\pi^2} \left[ \frac{1}{\epsilon} - \gamma - \ln(4\pi) - \int_0^1 \mathrm{d}x \ln\left( \frac{m^2 + x(1-x)q^2}{\mu^2} \right) \right] + \mathcal{O}(\epsilon)$$

---

## 3. 4 点頂点関数 $\Gamma^{(4)}$ への代入結果

問 (6) および (8) で得られた 1PI 4 点頂点関数：

$$\Gamma^{(4)}(p_1, p_2; p_3, p_4) = 4\lambda - 8\lambda^2 V(s) - 16\lambda^2 V(t) - 16\lambda^2 V(u) + \mathcal{O}(\lambda^3)$$

へ $V(s), V(t), V(u)$ の表現式を愚直に代入します（$8 + 16 + 16 = 40$）。

### 3.1. 裸の結合定数 $\lambda$ を用いた表示（紫外発散 $\frac{1}{\epsilon}$ を含む）

$$\begin{aligned}
\Gamma^{(4)}(p_1, p_2; p_3, p_4) &= 4\lambda - \frac{40\lambda^2}{16\pi^2} \left[ \frac{1}{\epsilon} - \gamma - \ln(4\pi) \right] \\
&\quad + \frac{\lambda^2}{2\pi^2} \int_0^1 \mathrm{d}x \left[ \ln\left(\frac{m^2+x(1-x)s}{\mu^2}\right) + 2\ln\left(\frac{m^2+x(1-x)t}{\mu^2}\right) + 2\ln\left(\frac{m^2+x(1-x)u}{\mu^2}\right) \right]
\end{aligned}$$

---

### 3.2. 再規格化結合定数 $g$ を用いた表示（無限大が消えた完全有限物理量！）

問 (8) の定義 $g \equiv \frac{1}{4} \Gamma^{(4)}(0,0,0,0)$ を用いて発散項 $\frac{1}{\epsilon}$ を $g$ に吸収（繰り込み）させます。
ゼロ運動量極限でのバブル積分：

$$V(0) = \frac{1}{16\pi^2} \left[ \frac{1}{\epsilon} - \gamma - \ln(4\pi) - \ln\left(\frac{m^2}{\mu^2}\right) \right]$$

より、結合定数 $g$ は：

$$g = \lambda - 10\lambda^2 V(0) \implies \lambda = g + 10g^2 V(0) + \mathcal{O}(g^3)$$

これを原式の $\lambda$ に代入すると、**発散項 $\frac{1}{\epsilon}$、定数 $\gamma, \ln(4\pi)$、スケール $\mu$ が完全に相互相殺して消滅します！**

最終的に得られる繰り込まれた 4 点頂点関数 $\Gamma^{(4)}_R$ は、**完全に有限な運動量依存性のみ**で表されます：

$$\Gamma^{(4)}_R(p_1, p_2; p_3, p_4) = 4g + \frac{2g^2}{\pi^2} \int_0^1 \mathrm{d}x \left[ \ln\left( 1 + \frac{x(1-x)s}{m^2} \right) + 2\ln\left( 1 + \frac{x(1-x)t}{m^2} \right) + 2\ln\left( 1 + \frac{x(1-x)u}{m^2} \right) \right]$$

---

## 4. この結果の物理的意味（感動ポイント）

1. **発散の完全消滅**:
   裸の理論では爆発していた $\frac{1}{\epsilon}$ の無限大が、再規格化結合定数 $g$ の定義によって綺麗に相殺されました。
2. **対数補正（Logarithmic Corrections）の出現**:
   高エネルギー・大運動量領域（$s, t, u \gg m^2$）において、頂点強度が $\ln(s/m^2)$ のように対数的に成長する物理的挙動（量子補正）が明確に読み取れます。
