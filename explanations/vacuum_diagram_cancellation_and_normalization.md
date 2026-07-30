# 生成汎関数の規格化因子 $1/Z[0, 0]$ と真空ダイアグラム消去の論理構造

ユーザーの疑問：
「問(4)で真空ダイアグラムがキャンセルすることを証明するには、問(1)〜(3)の然るべき場所に規格化因子 $\frac{1}{Z[0, 0]}$ を入れておく必要がありますよね？」

---

## 1. 結論

**全くその通りです！** 非常に鋭く本質的なご指摘です。

問(1)〜(2)の自由場と、問(3)以降の相互作用場では **規格化 $Z[0, 0]$ の値が異なる** ため、相関関数の定義式に規格化因子 $\frac{1}{Z[0, 0]}$ がどのように組み込まれているかを明記することで、問(1)〜(4)の論理が 100% 完璧に繋がります。

---

## 2. 自由場と相互作用場での $Z[0, 0]$ の違い

### (1) 自由場理論（問(1) & (2)）
自由場では、規格化定数 $\mathcal{N}_0$ を調節してあらかじめ **$Z_0[0, 0] = 1$ と正規化** しています：

$$
Z_0[0, 0] = \frac{1}{\mathcal{N}_0} \int \mathcal{D}\phi \mathcal{D}\phi^* e^{i S_0[\phi, \phi^*]} \equiv 1
$$

自由場には相互作用ループ（真空バブル）が存在しないため、$Z_0[0, 0] = 1$ で固定しておくだけで、汎関数微分による自由場相関関数の公式：

$$
\langle 0 | \mathrm{T} \hat{\phi}(x_1) \dots \hat{\phi}^*(y_1) | 0 \rangle_0 = \left. \frac{\delta^n Z_0[J, J^*]}{i\delta J^*(x_1) \dots i\delta J(y_1)} \right|_{J=0}
$$

は分母に何も書かなくても正確に成立します（分母 $Z_0[0, 0] = 1$ のため）。

---

### (2) 相互作用理論（問(3) & (4)）
相互作用 $\mathcal{L}_{\text{int}} = -\lambda (\phi^* \phi)^2$ が入ると、自由場の規格化 $\mathcal{N}_0$ を引き継いだ未規格化の全生成汎関数 $Z[J, J^*]$ において、$J = J^* = 0$ とおいた値 $Z[0, 0]$ は **1 にはならず、相互作用による全真空ダイアグラム（真空バブル）の総和 $Z_{\text{vacuum}}$** となります：

$$
Z[0, 0] = \left. \exp\left\{ -i \int \mathrm{d}^4x \, \mathcal{H}_{\text{int}}\left( \frac{\delta}{i\delta J} \right) \right\} Z_0[J, J^*] \right|_{J=0} = Z_{\text{vacuum}} \neq 1
$$

したがって、相互作用があるフル理論における**真の物理的相関関数（真空期待値）の定義式**は、必ず正規化因子 $\frac{1}{Z[0, 0]}$ を持つ形になります：

$$
\langle 0 | \mathrm{T} \hat{\phi}(x_1) \dots \hat{\phi}^*(y_1) | 0 \rangle = \frac{1}{Z[0, 0]} \left. \left( \frac{\delta}{i\delta J^*(x_1)} \dots \frac{\delta}{i\delta J(y_1)} Z[J, J^*] \right) \right|_{J=0}
$$

---

## 3. 問(4) における真空ダイアグラム消去の完全証明

生成汎関数 $Z[J, J^*]$ は、外線に接続された「連結ダイアグラム $Z_{\text{connected}}[J, J^*]$」と、外線に一切接続されていない「真空ダイアグラム $Z_{\text{vacuum}} = Z[0, 0]$」の積に因数分解できます：

$$
Z[J, J^*] = Z_{\text{connected}}[J, J^*] \times Z[0, 0]
$$

これを物理的相関関数の正規化公式に代入すると：

$$
\begin{aligned}
\langle 0 | \mathrm{T} \hat{\phi}(x_1) \dots \hat{\phi}^*(y_1) | 0 \rangle &= \frac{1}{Z[0, 0]} \left. \left( \frac{\delta}{i\delta J^*(x_1)} \dots \frac{\delta}{i\delta J(y_1)} \Big( Z_{\text{connected}}[J, J^*] \times Z[0, 0] \Big) \right) \right|_{J=0} \\
&= \frac{1}{Z[0, 0]} \, Z[0, 0] \left. \left( \frac{\delta}{i\delta J^*(x_1)} \dots \frac{\delta}{i\delta J(y_1)} Z_{\text{connected}}[J, J^*] \right) \right|_{J=0} \\
&= \left. \left( \frac{\delta}{i\delta J^*(x_1)} \dots \frac{\delta}{i\delta J(y_1)} Z_{\text{connected}}[J, J^*] \right) \right|_{J=0}
\end{aligned}
$$

分子に現れた定数因子 $Z[0, 0]$ と、分母の正規化因子 $1/Z[0, 0]$ が **完全約分（キャンセル）** されます。

これで、「相関関数の計算において真空ダイアグラムは一切寄与せず、完全に無視してよい」ことが厳密に証明されました。

---

## 4. 解答論文への反映方針

問(3) の被期待値・生成汎関数の記述において：
> 「フル理論の物理的相関関係を定義する際には、未規格化の $Z[J, J^*]$ に対し正規化因子 $\frac{1}{Z[0, 0]}$ を伴う汎関数微分を行う」

旨の定義注記を挿入し、問(4) でその $\frac{1}{Z[0, 0]}$ が $Z_{\text{vacuum}}$ を消去する論理構成を明示します。
