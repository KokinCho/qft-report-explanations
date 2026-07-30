# プロパゲーター記号 $G_0(p)$ と $G_0(0)$ の本質的解説および誤解解消ガイド

本ドキュメントは、場の量子論の摂動計算において混同しやすい **「運動量空間のプロパゲーター $G_0(p)$」** と **「タドポールループ積分 $G_0(0)$」** の記号（Notation）の違いと数学的・物理的意味を完全に整理したものです。

---

## 1. なぜ記号がややこしく感じられるのか？

数学的には、**同じ記号 $G_0$ を「位置空間」と「運動量空間」の2つの異なるドメインで兼用していること** が混同の原因です。

| 記号 | 属するドメイン | 意味 | 具体的な定義式 |
| :--- | :--- | :--- | :--- |
| **$G_0(x - y)$** | **位置空間 (Position space)** | 2点間の自由伝播関数（実空間プロパゲーター） | $G_0(x - y) = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{e^{ik \cdot (x - y)}}{k^2 + m_0^2}$ |
| **$G_0(0)$** | **位置空間 (Position space)** | **同じ時空点 ($x - y = 0$) での自セルフループ**（タドポール） | $G_0(0) \equiv \left. G_0(x - y) \right\|_{x-y=0} = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2}$ |
| **$G_0(p)$** | **運動量空間 (Momentum space)** | 運動量 $p$ を持って伝播する自由線 | $G_0(p) = \frac{1}{p^2 + m_0^2}$ |

---

## 2. $G_0(0)$ は「運動量 $p=0$」のことではない！

もっとも発生しやすい誤解は、**「$G_0(p) = \frac{1}{p^2+m_0^2}$ に $p=0$ を代入した $\frac{1}{m_0^2}$ のことか？」** という勘違いです。

* **誤り**: $G_0(0) \stackrel{?}{=} \frac{1}{0^2 + m_0^2} = \frac{1}{m_0^2}$
* **正しい**: $G_0(0)$ の `(0)` は **「時空点の差 $x - y = 0$」** を意味しています。

### 数学的な導出ステップ
位置空間における自由スカラー場のプロパゲーター $G_0(x-y) = \langle 0 | \mathrm{T} \phi(x) \phi^*(y) | 0 \rangle_0$ を運動量表示（フーリエ展開）すると：

$$G_0(x - y) = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{e^{ik \cdot (x - y)}}{k^2 + m_0^2}$$

ここで、頂点 $z$ から出て同じ頂点 $z$ に戻るタドポールループを考えると、始点と終点が同じであるため、**位置の差は $x - y = z - z = 0$** となります。

したがって、$x - y = 0$ を代入すると位相因子 $e^{ik \cdot 0} = 1$ となり：

$$G_0(0) \equiv G_0(x - x) = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{e^{ik \cdot 0}}{k^2 + m_0^2} = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2}$$

となります。これが、$G_0(0)$ がループ積分 $\int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2}$ そのものになる理由です。

---

## 3. 位置空間から運動量空間へのフーリエ変換の厳密な途中式計算

位置空間における 1次タドポール項を含む 2点関数は以下の通りです：

$$G^{(2)}(x, y) = G_0(x - y) - 4\lambda \int \mathrm{d}^4 z \, G_0(x - z) \underbrace{G_0(z - z)}_{= G_0(0)} G_0(z - y)$$

この式を運動量空間にフーリエ変換するステップを、途中式を含めて詳しく計算します。

### ステップ 1: 伝播関数 $G_0(x-z)$ および $G_0(z-y)$ のフーリエ表現の代入
それぞれの伝播関数をフーリエ表示で書き下します：

$$G_0(x - z) = \int \frac{\mathrm{d}^4 q_1}{(2\pi)^4} \frac{e^{iq_1 \cdot (x - z)}}{q_1^2 + m_0^2}$$

$$G_0(z - y) = \int \frac{\mathrm{d}^4 q_2}{(2\pi)^4} \frac{e^{iq_2 \cdot (z - y)}}{q_2^2 + m_0^2}$$

これらをタドポール項 $\int \mathrm{d}^4 z \, G_0(x - z) G_0(0) G_0(z - y)$ に代入します：

$$\int \mathrm{d}^4 z \, G_0(x-z) G_0(0) G_0(z-y) = G_0(0) \int \frac{\mathrm{d}^4 q_1}{(2\pi)^4} \frac{\mathrm{d}^4 q_2}{(2\pi)^4} \frac{e^{iq_1 \cdot x} e^{-iq_2 \cdot y}}{(q_1^2 + m_0^2)(q_2^2 + m_0^2)} \underbrace{\int \mathrm{d}^4 z \, e^{-i(q_1 - q_2) \cdot z}}_{= (2\pi)^4 \delta^4(q_1 - q_2)}$$

### ステップ 2: 頂点座標 $z$ の積分実行とデルタ関数の処理
頂点 $z$ の空間積分を実行すると、デルタ関数 $(2\pi)^4 \delta^4(q_1 - q_2)$ が出現します。
$q_2$ の積分をデルタ関数を用いて実行すると、$q_2 = q_1$ となり以下のように簡単化されます：

$$\int \mathrm{d}^4 z \, G_0(x-z) G_0(0) G_0(z-y) = G_0(0) \int \frac{\mathrm{d}^4 q_1}{(2\pi)^4} \frac{e^{iq_1 \cdot (x - y)}}{(q_1^2 + m_0^2)^2}$$

### ステップ 3: 相対座標 $r = x - y$ に対する全フーリエ変換
運動量空間での伝播関数 $G^{(2)}(p)$ は、相対座標 $r = x - y$ に関するフーリエ変換で定義されます：

$$G^{(2)}(p) = \int \mathrm{d}^4 (x - y) \, e^{-ip \cdot (x - y)} G^{(2)}(x, y)$$

1. **自由伝播項 $G_0(x-y)$ のフーリエ変換**:
   $$\int \mathrm{d}^4 (x - y) \, e^{-ip \cdot (x - y)} G_0(x - y) = \frac{1}{p^2 + m_0^2} = G_0(p)$$

2. **1次タドポール項のフーリエ変換**:
   $$\begin{aligned}
   &\int \mathrm{d}^4 (x - y) \, e^{-ip \cdot (x - y)} \left[ G_0(0) \int \frac{\mathrm{d}^4 q_1}{(2\pi)^4} \frac{e^{iq_1 \cdot (x - y)}}{(q_1^2 + m_0^2)^2} \right] \\
   &= G_0(0) \int \frac{\mathrm{d}^4 q_1}{(2\pi)^4} \frac{1}{(q_1^2 + m_0^2)^2} \underbrace{\int \mathrm{d}^4 (x - y) \, e^{i(q_1 - p) \cdot (x - y)}}_{= (2\pi)^4 \delta^4(q_1 - p)} \\
   &= G_0(0) \frac{1}{(p^2 + m_0^2)^2} = G_0(p)^2 G_0(0)
   \end{aligned}$$

---

### ステップ 4: 最終まとめ
以上の各項のフーリエ変換を組み合わせることにより、運動量空間における 2点関数の表現が厳密に導かれます：

$$G^{(2)}(p) = G_0(p) - 4\lambda G_0(p)^2 G_0(0) + \mathcal{O}(\lambda^2)$$

ここで：
- **$G_0(p) = \frac{1}{p^2+m_0^2}$** は、入線および出線を表す **運動量 $p$ の自由伝播関数**
- **$G_0(0) = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2+m_0^2}$** は、**時空差 $x-y=0$ で自己収縮した定数ループ積分**

---

## 4. レポートにおける明確化のための表記改善案

混乱を避けるため、TeX レポート内の該当箇所（問(6)および問(7)）に以下の注釈文を添えると、採点者にとっても非常に親切で誤解の余地がない完璧な記述になります。

```latex
(Note: Here, $G_0(p) = \frac{1}{p^2+m_0^2}$ denotes the free propagator in momentum space for momentum $p$, whereas $G_0(0) \equiv \left. G_0(x-y) \right|_{x-y=0} = \int \frac{\dd^4 k}{(2\pi)^4} \frac{1}{k^2+m_0^2}$ represents the position-space free propagator evaluated at zero spacetime separation $x-y=0$, which corresponds to the momentum-integral of the self-contracted 1-loop tadpole.)
```
