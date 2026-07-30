# なぜオンシェル頂点関数は $\gamma_5$ だけで完結するのか？

このドキュメントでは、擬スカラー相互作用における頂点関数が、オンシェル射影（または外線スピノールで挟む操作）によってなぜ $\gamma_5$ というただ1つの行列構造だけに簡約化されるのか、その対称性とディラック代数に基づいた本質的な理由を解説します。

---

## 1. 理由の結論

オンシェルにおいて行列構造が $\gamma_5$ だけに完結する理由は、以下の2つの物理的・数学的性質の組み合わせによるものです：

1. **パリティ保存（物理的対称性）**:
   元の相互作用が擬スカラー（$i g \bar{\psi}\gamma_5\psi\phi$）でありパリティを保存するため、1PI三点関数 $\widetilde{\Gamma}'$ もパリティ奇（擬スカラー的）な行列構造しか持てない。
2. **ディラック代数のオンシェル退化（代数的性質）**:
   ディラック方程式（$\not p \to m$）とガンマ行列の反交換関係（$\{\gamma^\mu, \gamma_5\} = 0$）により、一見独立に見える「パリティ奇の行列構造（$\gamma_5 \not p, \gamma_5 \not p'$ など）」は、すべてオンシェル上で $\gamma_5$ そのものに比例する形に潰れてしまう。

---

## 2. ディラック代数による具体的な証明

外線スピノールで挟まれた量、あるいはそれと等価なオンシェル射影された量：
$$(\not p' + m) \widetilde{\Gamma}'(p', p, q) (\not p + m) \Big|_{p^2 = p'^2 = m^2}$$
を考えます。

ディラック代数の基本基底（16個の行列）と利用可能な運動量 $p^\mu, p'^\mu$ から作られる構造のうち、パリティ奇（擬スカラー的）なものとして考えられる代表的な候補は以下の通りです：
- $\gamma_5$
- $\gamma_5 \not p$
- $\gamma_5 \not p'$
- $\sigma^{\mu\nu} p_\mu p'_\nu \gamma_5$ （これは $\frac{1}{2}(\not p' \not p - \not p \not p') \gamma_5$ と書けます）

これらが、オンシェル射影（ディラック方程式の適用）によってどのように変化するかを1つずつ計算してみます。

### (A) $\gamma_5 \not p$ の場合
$\gamma_5$ と $\not p = p_\mu \gamma^\mu$ は反交換する（$\gamma_5 \not p = - \not p \gamma_5$）という性質を利用します。
これを右側の射影演算子 $(\not p + m)$ に作用させると：
$$\begin{aligned}
\gamma_5 \not p (\not p + m) &= \gamma_5 (p^2 + m \not p) \\
&= \gamma_5 (m^2 + m \not p) \quad (\because p^2 = m^2) \\
&= m \gamma_5 (m + \not p) \\
&= m (\not p + m) \gamma_5 \quad (\because \gamma_5 \text{ と } \not p \text{ の反交換で順番を入れ替える})
\end{aligned}$$
したがって、
$$(\not p' + m) (\gamma_5 \not p) (\not p + m) = m (\not p' + m) \gamma_5 (\not p + m)$$
となり、$\gamma_5$ の項に完全に吸収されます。

あるいは、外線スピノール $u(p)$ を用いて右側から掛ける形で見ると、より直感的に分かります：
$$(\gamma_5 \not p) u(p) = - \not p \gamma_5 u(p) = -m \gamma_5 u(p) \quad (\because \text{ディラック方程式より} \not p u = m u)$$
これも、ただの定数（$-m$）と $\gamma_5$ の積になります。

### (B) $\gamma_5 \not p'$ の場合
同様に、左側の $\gamma_5 \not p'$ を左側の射影演算子 $(\not p' + m)$ と作用させます（あるいは左からスピノール $\bar{u}(p')$ を掛けます）：
$$\bar{u}(p') (\gamma_5 \not p') = \bar{u}(p') (\not p' \gamma_5) = m \bar{u}(p') \gamma_5 \quad (\because \bar{u}(p') \not p' = m \bar{u}(p'))$$
これも、定数 $m$ と $\gamma_5$ の積に退化します。

### (C) $\sigma^{\mu\nu} p_\mu p'_\nu \gamma_5$ の場合
この構造は、ディラック行列の積を用いて以下のように書けます：
$$\sigma^{\mu\nu} p_\mu p'_\nu \gamma_5 \propto (\not p' \not p - p \cdot p') \gamma_5$$
これを右側のスピノール $u(p)$ に作用させてみます：
$$\begin{aligned}
(\not p' \not p - p \cdot p') \gamma_5 u(p) &= \gamma_5 (\not p' \not p - p \cdot p') u(p) \quad (\because \gamma_5 \text{ は2つのガンマ行列と反交換するので2回符号が変わり、符号は不変}) \\
&= \gamma_5 (\not p' m - p \cdot p') u(p) \quad (\because \not p u = m u)
\end{aligned}$$
ここで、さらに左側から $\bar{u}(p')$ を掛けると：
$$\bar{u}(p') \gamma_5 (m \not p' - p \cdot p') u(p) = \bar{u}(p') \gamma_5 (m^2 - p \cdot p') u(p)$$
$p \cdot p'$ はただのスカラー値なので、この複雑な構造も、結局はただのスカラー係数 $(m^2 - p \cdot p')$ と $\bar{u}(p') \gamma_5 u(p)$ の積に潰れてしまいます。

---

## 3. もし他の理論だったらどうなるか？

$\gamma_5$ が選ばれたのは、元の相互作用が「擬スカラー結合（パリティ奇）」だからです。もし理論が異なれば、生き残る行列構造も変わります。

### (1) スカラー結合理論（例： $g \bar{\psi} \psi \phi$）
- **対称性**: パリティ偶（スカラー）
- **オンシェルで生き残る構造**: 単位行列 $I$ のみ。
- **結果**:
  $$(\not p' + m) \widetilde{\Gamma}'(p', p, q) (\not p + m) \Big|_{\text{on-shell}} = (\not p' + m) I (\not p + m) G(q^2)$$
  （単位行列 $I$ だけで完結します）

### (2) パリティ非保存理論（例：弱い相互作用 $g \bar{\psi} (1 - \gamma_5) \psi \phi$）
- **対称性**: パリティは保存しない（スカラーと擬スカラーの混合）
- **オンシェルで生き残る構造**: $I$ と $\gamma_5$ の **2つの独立な構造**。
- **結果**:
  $$(\not p' + m) \widetilde{\Gamma}'(p', p, q) (\not p + m) \Big|_{\text{on-shell}} = (\not p' + m) \left[ G_1(q^2) I + G_2(q^2) \gamma_5 \right] (\not p + m)$$
  この場合は、1つではなく2つの独立なスカラー関数 $G_1(q^2), G_2(q^2)$ が必要になり、繰り込み条件も2つ必要になります。

### (3) ベクトル結合理論（例：QED $e \bar{\psi} \gamma^\mu \psi A_\mu$）
- **対称性**: ベクトル結合（パリティ保存）
- **オンシェルで生き残る構造**:
  有名な**ゴードン分解（Gordon Decomposition）**により、オンシェル上で $\gamma^\mu$ と $\sigma^{\mu\nu} q_\nu$ の **2つの独立な構造**に簡約化されます（これらが電子の電荷と異常磁気モーメントに対応します）。

---

## 4. まとめ

$\gamma_5$ が特別なのは、**「擬スカラーメソン結合（パリティ奇）の理論」において、オンシェル条件とディラック代数を適用した結果、すべての可能な行列構造が最終的に $\gamma_5$ というただ1つの基本構造に退化（収束）してしまうから**です。
これこそが、理論の対称性とディラック方程式がもたらす美しい物理的帰結です。
