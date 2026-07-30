# 問 (5) 解答の不足箇所・不備の完全監査レポートと修正方針

問題文の要求：
> "(5) Use the Feynman rules that you derived in (1) of this exercise to obtain the perturbation theory expansion in Euclidean spacetime for
> (a) the vacuum diagrams,
> (b) the two-point functions,
> (c) the four-point functions,
> in position space and up to and including all terms up to second order in the coupling constant $\lambda$. Assign a Feynman diagram to each term. Give an explicit formula for each term, including the multiplicity factors. Do not do the integrals! Verify the cancellation of the vacuum diagrams."

現在の TeX 文書 (`Kokin_Cho_QFT_term_paper.tex` L712–L776) を上記要求と照らし合わせた結果、**不足・不備・省略されている点が 4 点**存在します。以下に全て洗い出します。

---

## 1. 不足点 1：真空ダイアグラム $Z[0, 0]$ (a) の分類不足と多重度（対称性因子）導出の省略

### 現状の問題点
- $\mathcal{O}(\lambda^2)$ の真空ダイアグラムとして 2 種類（three-bubble と sunset）しか書かれておらず、分類が不完全です。
- 各項の係数（対称性因子 / 重複度 $S$）がなぜその数値になるのか、微分の組み合わせ計算 $\frac{1}{V!} (-4\lambda)^V \times \text{(組換え数)}$ の説明が全くありません。

### 必要な補訂内容
1. **$\mathcal{O}(\lambda^1)$ (1頂点)**:
   Figure-8 ダイアグラム（1頂点 $x$ 内での 2 つの同点自己縮約）。
   - 頂点演算子: $\frac{1}{1!} (-4\lambda) \int \mathrm{d}^4x \left(\frac{\delta}{\delta J(x)}\right)^2 \left(\frac{\delta}{\delta J^*(x)}\right)^2$
   - 縮約パターン数: $\phi^*(x)$ 2つの同点縮約 $\to 1$ 通り、$\phi(x)$ 2つの同点縮約 $\to 1$ 通り。さらに $x$ と $y$ の同点ペア $\to 2! = 2$ 通り。
   - 係数: $(-4\lambda) \times \frac{1}{2} = -2\lambda$。
   $$ V_1 = -2\lambda \int \mathrm{d}^4x \, G_0(0)^2 $$

2. **$\mathcal{O}(\lambda^2)$ (2頂点 $x, y$) の 3 つの独立ダイアグラムへの完全分類**:
   - **(a) Disconnected figure-8 (分離した 2 つの figure-8)**:
     $$ V_{2a} = \frac{1}{2!} V_1^2 = 2 \lambda^2 \left( \int \mathrm{d}^4x \, G_0(0)^2 \right)^2 $$
   - **(b) Connected figure-8 / Double-bubble (頂点 $x, y$ が 2 本の線で繋がれた figure-8)**:
     頂点 $x$ と $y$ にそれぞれ自己ループが 1 つずつあり、 $x$ と $y$ の間が 2 本のプロパゲータで結ばれる。
     $$ V_{2b} = 8 \lambda^2 \int \mathrm{d}^4x \, \mathrm{d}^4y \, G_0(0) G_0(x-y)^2 G_0(0) $$
   - **(c) Sunset / Watermelon (頂点 $x, y$ 間が 4 本の線で結ばれたスイカ型)**:
     $$ V_{2c} = 4 \lambda^2 \int \mathrm{d}^4x \, \mathrm{d}^4y \, G_0(x-y)^4 $$

---

## 2. 不足点 2：真空ダイアグラムの相殺（Verify the cancellation）の具体過程の欠落

### 現状の問題点
問題文は **「Verify the cancellation of the vacuum diagrams (真空ダイアグラムが相殺されることを具体的に検証せよ)」** を明確に求めていますが、現在の TeX では最後に 1 行「分母で割れば消えます」と文章で書いているだけで、数学的な展開式の相殺計算が示されていません。

### 必要な補訂内容
1. **未正規化の全 2 点関数 $G^{(2)}_{\text{full}}(x, y)$ を書き下す**:
   $$ G^{(2)}_{\text{full}}(x, y) = \left[ G_0(x-y) + G^{(2)}_{1,\text{conn}}(x, y) + G^{(2)}_{2,\text{conn}}(x, y) + \dots \right] \times \left[ 1 + V_1 + V_2 + \dots \right] $$
2. **正規化因子 $Z[0, 0]^{-1}$ の Taylor 展開**:
   $$ \frac{1}{Z[0, 0]} = \frac{1}{1 + V_1 + V_2 + \dots} = 1 - V_1 + (V_1^2 - V_2) + \dots $$
3. **割り算（掛け算）を実行して $\mathcal{O}(\lambda^1), \mathcal{O}(\lambda^2)$ で真空項 $V_1, V_2$ が引き算で完全に相殺消去される代数計算ステップを提示する**！

---

## 3. 不足点 3：4点関数 (c) での交叉項（$s, t, u$ チャンネル）と非連結項の省略

### 現状の問題点
TeX 内で `+ (cross terms)` と記述して計算を省略しています。問題文は「all terms up to second order」を要求しているため、クロス項（$s, t, u$ チャンネル）および非連結成分を明記する必要があります。

### 必要な補訂内容
1. **$\mathcal{O}(\lambda^2)$ 1-loop 連結 4点関数の 3 チャンネル明記**:
   - $s$-channel: $\int \mathrm{d}^4z_1 \mathrm{d}^4z_2 \, G_0(x_1-z_1) G_0(x_2-z_1) \left[ G_0(z_1-z_2)^2 \right] G_0(z_2-y_1) G_0(z_2-y_2)$
   - $t$-channel: $x_1 \to z_1 \to y_1$ および $x_2 \to z_2 \to y_2$ を繋ぐループ
   - $u$-channel: $x_1 \to z_1 \to y_2$ および $x_2 \to z_2 \to y_1$ を繋ぐループ
   これら 3 項の和を明示する。
2. **非連結成分（Disconnected components）の明記**:
   外線 2 本が自由伝播し、残り 2 本がタッドポールや頂点で散乱する項。

---

## 4. 不足点 4：ファインマン・ダイアグラムの視覚的図示（TikZ または説明図）の欠落

### 現状の問題点
問題文の「Assign a Feynman diagram to each term」に対し、テキスト名（"figure-8 diagram" など）で済ませており、図形が存在しません。

---

## 5. `tikz-feynman` テスト完了と問 (5) TeX 改訂の完全実行方針

事前に `tikz-feynman` パッケージを用いて、樹状図・Figure-8・タッドポール・Sunset（スイカ型）・1ループ 4点散乱（$s$ チャンネル）などの全パターンの描画をコンパイル検証し、出版クオリティで非常に美麗に出力されることを画像レベルで確認いたしました。

これを踏まえ、`Kokin_Cho_QFT_term_paper.tex` の問 (5) を以下の 4 つの柱で完全に改訂・強化します：

### 方針 1: 真空ダイアグラム $Z[0, 0]$ (a) の完全展開と `tikz-feynman` 図示
- $\mathcal{O}(\lambda^1)$: Figure-8 ダイアグラム（1頂点 $x$）
  ```latex
  \begin{tikzpicture}
    \begin{feynman}
      \vertex (v) [dot, label=below:$x$];
      \diagram* {
        (v) -- [fermion, out=45, in=135, min distance=1.5cm] (v),
        (v) -- [anti fermion, out=-45, in=-135, min distance=1.5cm] (v),
      };
    \end{feynman}
  \end{tikzpicture}
  ```
  数式: $V_1 = -2\lambda \int \mathrm{d}^4x \, G_0(0)^2$ （重複度 $S=2$ の微分組み合わせ根拠を明記）。

- $\mathcal{O}(\lambda^2)$: 3 つの全真空ダイアグラムを網羅
  1. **分離 Figure-8**: $V_{2a} = 2\lambda^2 \left(\int \mathrm{d}^4x G_0(0)^2\right)^2$
  2. **連結 Double-bubble**: $V_{2b} = 8\lambda^2 \int \mathrm{d}^4x \mathrm{d}^4y G_0(0) G_0(x-y)^2 G_0(0)$
  3. **Sunset (スイカ型)**: $V_{2c} = 4\lambda^2 \int \mathrm{d}^4x \mathrm{d}^4y G_0(x-y)^4$
  ```latex
  \begin{tikzpicture}
    \begin{feynman}
      \vertex (x) [dot, label=left:$x$];
      \vertex [right=1.8cm of x] (y) [dot, label=right:$y$];
      \diagram* {
        (x) -- [fermion, bend left=75] (y),
        (x) -- [fermion, bend left=25] (y),
        (y) -- [fermion, bend left=25] (x),
        (y) -- [fermion, bend left=75] (x),
      };
    \end{feynman}
  \end{tikzpicture}
  ```

### 方針 2: 2点関数 (b) での代数的な「真空バブル相殺（Verify Cancellation）」の提示
- 未規格化の全 2 点関数 $G^{(2)}_{\text{full}}(x, y) = G^{(2)}_{\text{conn}}(x, y) [1 + V_1 + V_2 + \dots]$ と、規格化分母 $Z[0, 0]^{-1} = 1 - V_1 + (V_1^2 - V_2) + \dots$ の掛け算代数展開を直接提示し、$V_1, V_2$ が引き算で完全相殺消去されて $G^{(2)}_{\text{conn}}(x, y)$ のみが生き残る計算プロセスを直接示す。

### 方針 3: 4点関数 (c) での交叉項（$s, t, u$ チャンネル）と非連結項の完全明記
- 1-loop 連結 4点関数における $s, t, u$ チャンネルの 3 項（$G_0(z_1-z_2)^2$ 等）を全て省略せずに明記し、それぞれに対応する `tikz-feynman` ダイアグラムを割り当てる。

### 方針 4: コンパイルの安定性確保
- ルート文書のプリアンブルに `\usepackage[compat=1.1.0]{tikz-feynman}` を追加し、本文中に各ダイアグラムの TikZ 環境を埋め込むことで、本文と図が完全に一体化したプロレベルのレポートに仕上げます。

