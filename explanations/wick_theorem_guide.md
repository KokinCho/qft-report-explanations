# Wickの定理（4点相関関数）の証明の解説と別方針

レポートの小問 (1.4) における **Wickの定理（4点ガウス期待値の公式）** の証明について、現在の解答の行間の解説および、別の方針による証明の解説をまとめました。

---

## 1. 現在の解答の行間解説（cumulantを用いた方法）

現在の解答は、統計力学や場の量子論で非常に強力な道具である**「連結自由エネルギー（連結相関関数の生成母関数）」**の性質を利用しています。

### 分配関数と期待値の定義
まず、補助場 $b$ を導入した分配関数 $Z(b)$ を定義します：
$$
Z(b) \coloneqq \int_{-\infty}^{\infty} \dd{^N x} e^{-\frac{1}{2} x^{\mathrm{T}} A x + b^{\mathrm{T}} x} = Z(0) e^{\frac{1}{2} b^{\mathrm{T}} A^{-1} b}
$$
この $Z(b)$ を $b$ の各成分で偏微分すると、被積分関数に $x$ の各成分が挿入されます。したがって、求める 4 点期待値は次のように $b=0$ での 4 階偏微分として得られます：
$$
\expval{x_i x_j x_k x_l} = \frac{1}{Z(0)} \left. \frac{\partial^4 Z(b)}{\partial b_i \partial b_j \partial b_k \partial b_l} \right|_{b=0}
$$

### $Z(b) = e^{W(b)}$ の関係と積の微分
ここで、連結母関数 $W(b) \coloneqq \ln Z(b)$ を導入します：
$$
W(b) = \ln Z(0) + \frac{1}{2} b^{\mathrm{T}} A^{-1} b = \ln Z(0) + \frac{1}{2} \sum_{a,c} (A^{-1})_{ac} b_a b_c
$$
$Z(b) = e^{W(b)}$ の両辺を $b$ の成分で順次微分していきます（積の微分公式（Leibniz則）を適用します）。

1. **1階微分**
   $$
   \frac{\partial Z}{\partial b_i} = \frac{\partial W}{\partial b_i} Z
   $$
2. **2階微分**
   $$
   \frac{\partial^2 Z}{\partial b_i \partial b_j} = \left( \frac{\partial^2 W}{\partial b_i \partial b_j} + \frac{\partial W}{\partial b_i}\frac{\partial W}{\partial b_j} \right) Z
   $$
3. **3階微分**
   $$
   \frac{\partial^3 Z}{\partial b_i \partial b_j \partial b_k} = \left( \frac{\partial^3 W}{\partial b_i \partial b_j \partial b_k} + \frac{\partial^2 W}{\partial b_i \partial b_j}\frac{\partial W}{\partial b_k} + \frac{\partial^2 W}{\partial b_j \partial b_k}\frac{\partial W}{\partial b_i} + \frac{\partial^2 W}{\partial b_k \partial b_i}\frac{\partial W}{\partial b_j} + \frac{\partial W}{\partial b_i}\frac{\partial W}{\partial b_j}\frac{\partial W}{\partial b_k} \right) Z
   $$
4. **4階微分**
   さらにこれを $b_l$ で微分し、最後に $b=0$ とおきます。

### ガウス分布の持つ強力な性質
$W(b)$ は $b$ の**二次式**であるため、以下の極めて単純な性質を持ちます：
- $\left. \frac{\partial W}{\partial b_a} \right|_{b=0} = \left. (A^{-1} b)_a \right|_{b=0} = 0$ （1階微分は $b=0$ で消える）
- $\frac{\partial^2 W}{\partial b_a \partial b_c} = (A^{-1})_{ac}$ （2階微分は定数）
- $\frac{\partial^n W}{\partial b_a \partial b_c \cdots} = 0 \quad (n \ge 3)$ （3階以上の微分はすべて恒等的に $0$）

したがって、4階微分の展開式において $b=0$ とおいたとき、**「1階微分 $\frac{\partial W}{\partial b}$」や「3階以上の微分 $\frac{\partial^3 W}{\partial b^3}$」を含むすべての項が $0$ になって消失**します。

結果として、**「2階微分どうしの積」の項だけが生き残り**ます。インデックス $\{i, j, k, l\}$ を2ペアに分ける組み合わせは以下の3通りなので、生き残る項はこれらのみになります：
$$
\left. \frac{\partial^4 Z(b)}{\partial b_i \partial b_j \partial b_k \partial b_l} \right|_{b=0} = \left( \frac{\partial^2 W}{\partial b_i \partial b_j}\frac{\partial^2 W}{\partial b_k \partial b_l} + \frac{\partial^2 W}{\partial b_i \partial b_k}\frac{\partial^2 W}{\partial b_j \partial b_l} + \frac{\partial^2 W}{\partial b_i \partial b_l}\frac{\partial^2 W}{\partial b_j \partial b_k} \right) Z(0)
$$
両辺を $Z(0)$ で割り、前問の結果である $\frac{\partial^2 W}{\partial b_a \partial b_c} = (A^{-1})_{ac} = \expval{x_a x_c}$ を代入すると、ただちに Wick の定理：
$$
\expval{x_i x_j x_k x_l} = \expval{x_i x_j}\expval{x_k x_l} + \expval{x_i x_k}\expval{x_j x_l} + \expval{x_i x_l}\expval{x_j x_k}
$$
が導かれます。

---

## 2. 別方針A：補助場 $b$ を用いた直接的な4階微分

$W = \ln Z$ のような対数関数を経由せず、前問で求めた $Z(b) = Z(0) e^{\frac{1}{2} b^{\mathrm{T}} A^{-1} b}$ を直接微分していく方針です。

$f(b) \coloneqq \frac{1}{2} b^{\mathrm{T}} A^{-1} b$ とおくと、$Z(b) = Z(0) e^{f(b)}$ です。

1. **1階微分**：
   $$
   \frac{\partial Z(b)}{\partial b_l} = Z(0) \frac{\partial f}{\partial b_l} e^{f(b)} \quad \qty( \text{ただし } \frac{\partial f}{\partial b_l} = \sum_{m} (A^{-1})_{lm} b_m )
   $$
2. **2階微分**：
   $$
   \frac{\partial^2 Z(b)}{\partial b_k \partial b_l} = Z(0) \left( \frac{\partial^2 f}{\partial b_k \partial b_l} + \frac{\partial f}{\partial b_k} \frac{\partial f}{\partial b_l} \right) e^{f(b)} \quad \qty( \text{ただし } \frac{\partial^2 f}{\partial b_k \partial b_l} = (A^{-1})_{kl} )
   $$
3. **3階微分**：
   $$
   \frac{\partial^3 Z(b)}{\partial b_j \partial b_k \partial b_l} = Z(0) \left( (A^{-1})_{kl} \frac{\partial f}{\partial b_j} + (A^{-1})_{jl} \frac{\partial f}{\partial b_k} + (A^{-1})_{jk} \frac{\partial f}{\partial b_l} + \frac{\partial f}{\partial b_j}\frac{\partial f}{\partial b_k}\frac{\partial f}{\partial b_l} \right) e^{f(b)}
   $$
4. **4階微分（$b=0$ での評価）**：
   これを $b_i$ で偏微分し、最後に $b=0$ とおきます。
   やはり $\left. \frac{\partial f}{\partial b_a} \right|_{b=0} = 0$ となるため、$\frac{\partial f}{\partial b}$ を奇数個含む項はすべて消え、2階微分のペア（定数）だけが生き残ります：
   $$
   \left. \frac{\partial^4 Z(b)}{\partial b_i \partial b_j \partial b_k \partial b_l} \right|_{b=0} = Z(0) \left( (A^{-1})_{kl} (A^{-1})_{ij} + (A^{-1})_{jl} (A^{-1})_{ik} + (A^{-1})_{jk} (A^{-1})_{il} \right)
   $$
   両辺を $Z(0)$ で割れば、Wickの定理が得られます。特別な概念を一切使わないため、数学的に最もストレートです。

---

## 3. 別方針B：直交対角化による証明

行列 $A$ を対角化し、問題を**「互いに独立な1次元ガウス期待値の積」**に完全に分解する方針です。幾何学的な見通しが非常に良い方法です。

### 変数変換
実対称正定値行列 $A$ を直交行列 $O$ によって対角化し、$x = Oy$（成分では $x_i = \sum_{\alpha} O_{i\alpha} y_{\alpha}$）と変数変換します。
これにより、$y_{\alpha}$ はそれぞれ平均 0、分散 $\expval{y_{\alpha}^2} = 1/\lambda_{\alpha}$ の**互いに独立なガウス分布**に従います。

独立性より、異なるモード間の期待値は常に積に分解されて $0$ になります：
$$
\alpha \neq \beta \text{ のとき } \expval{y_{\alpha} y_{\beta}} = \expval{y_{\alpha}}\expval{y_{\beta}} = 0
$$

### 4点相関関数の計算
4点期待値 $\expval{x_i x_j x_k x_l}$ を変数変換して展開します：
$$
\expval{x_i x_j x_k x_l} = \sum_{\alpha, \beta, \gamma, \delta} O_{i\alpha} O_{j\beta} O_{k\gamma} O_{l\delta} \expval{y_{\alpha} y_{\beta} y_{\gamma} y_{\delta}}
$$
ここで、期待値 $\expval{y_{\alpha} y_{\beta} y_{\gamma} y_{\delta}}$ が $0$ にならないのは、インデックスがすべてペアになっている場合のみです。具体的には以下の関係が成り立ちます（Wickの定理の1次元独立版）：
$$
\expval{y_{\alpha} y_{\beta} y_{\gamma} y_{\delta}} = \expval{y_{\alpha} y_{\beta}}\expval{y_{\gamma} y_{\delta}} + \expval{y_{\alpha} y_{\gamma}}\expval{y_{\beta} y_{\delta}} + \expval{y_{\alpha} y_{\delta}}\expval{y_{\beta} y_{\gamma}}
$$
*（検証：すべて同じなら左辺は $3\expval{y_{\alpha}^2}^2$、右辺も $\expval{y_{\alpha}^2}^2 \times 3$ で一致。ペアが2つなら右辺の3項中1項だけが生き残り、両辺ともに一致します。）*

この関係式を上の展開式に代入し、各項を逆変換 $y \to x$ で戻すと、
$$
\sum_{\alpha, \beta, \gamma, \delta} O_{i\alpha} O_{j\beta} O_{k\gamma} O_{l\delta} \left[ \expval{y_{\alpha} y_{\beta}}\expval{y_{\gamma} y_{\delta}} + \cdots \right] = \expval{x_i x_j}\expval{x_k x_l} + \expval{x_i x_k}\expval{x_j x_l} + \expval{x_i x_l}\expval{x_j x_k}
$$
となり、やはり Wick の定理が導かれます。
ガウス積分のもつ「回転して独立にできる」という性質そのものに着目した、物理的に極めて自然な証明方法です。
