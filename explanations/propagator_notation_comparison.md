# プロパゲータ表記 $\Delta_{F,0}$ と $D_F(x-y)$ の関係と係数の精査

## 1. 結論

結論から申し上げますと、**係数（虚数単位 $i$）を含めて完全には一致していません**。
具体的には、**$\Delta_{F,0}(x-y) = i D_F(x-y)$** という関係（因子 $i$ のズレ）があります。

---

## 2. 定義の比較と精査

### (1) 前問 (1)〜(3) における $D_F(x-y)$ の定義
前問では、$D_F(x-y)$ は微分方程式の解（グリーン関数）として次のように定義されています：

\[
(\partial^2 + m_0^2 - i\epsilon) D_F(x-y) = -\delta^4(x-y)
\]

運動量空間表示では以下のようになります：

\[
D_F(x-y) = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{e^{-ik\cdot(x-y)}}{k^2 - m_0^2 + i\epsilon}
\]

このとき、自由場の真空期待値（2点相関関数）との関係は**虚数単位 $i$ が付加**されます：

\[
\langle 0 | \mathrm{T} \hat{\phi}(x) \hat{\phi}^\dagger(y) | 0 \rangle = i D_F(x-y)
\]

---

### (2) 坂本本（第10章）における $\Delta_{F,0}(x-y)$ の定義
坂本眞人著『場の量子論(II)』第10章における $\Delta_{F,0}(x-y)$ は、**自由場の2点タイムオーダー積の真空期待値そのもの**として定義されています：

\[
\Delta_{F,0}(x-y) \equiv \langle 0 | \mathrm{T} \phi(x) \phi(y) | 0 \rangle_0
\]

運動量空間表示では：

\[
\Delta_{F,0}(x-y) = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{i}{k^2 - m_0^2 + i\epsilon} e^{-ik\cdot(x-y)}
\]

したがって、両者の間には以下の関係が成り立ちます：

\[
\Delta_{F,0}(x-y) = i D_F(x-y)
\]

---

## 3. Euclidean 空間（本問題 (5)）における扱い

問題 (5) は **「Euclidean spacetime における摂動展開」** を求めています。

Minkowski 空間から Euclidean 空間への Wick 回転（$t = -i\tau$, $\mathrm{d}^4x = -i \mathrm{d}^4x_E$）を行うと：

- Minkowski 空間の 2点相関関数 $\Delta_{F,0}(x-y) = i D_F(x-y)$ は、Euclidean 空間では実数かつ正定値のプロパゲータ **$G_0(x_E - y_E)$** に移行します。
- Euclidean 空間における 2点プロパゲータは以下で与えられます：

\[
G_0(x_E - y_E) = \int \frac{\mathrm{d}^4 k_E}{(2\pi)^4} \frac{e^{i k_E \cdot (x_E - y_E)}}{k_E^2 + m_0^2}
\]

---

## 4. レポート全体での表記の統一案

レポートの他問や引用元（坂本本）との整合性を保つため、以下のいずれかの方針で統一することが推奨されます：

1. **方針 A（Euclidean プロパゲータ $G_0(x-y)$ で統一）**:
   - 問題(5)が Euclidean 空間であることを重視し、$\Delta_{F,0}$ の代わりに **$G_0(x_1 - x_2)$** または **$G_0(x-y)$** を用いて記述する。（※前問(1)(2)の Euclidean 節での表記と完全に一致します）

2. **方針 B（$\Delta_{F,0}(x-y) = i D_F(x-y)$ の関係を冒頭で注記）**:
   - 坂本本の図・表記をそのまま活かしつつ、冒頭のリマークで「坂本本の $\Delta_{F,0}(x-y)$ は自由場の2点期待値 $\langle \mathrm{T}\phi(x)\phi(y)\rangle_0 = i D_F(x-y)$ （Euclidean 空間では $G_0(x-y)$）に対応する」と注記しておく。
