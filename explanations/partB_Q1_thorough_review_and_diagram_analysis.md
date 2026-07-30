# Part B 第1問の詳細精査および4点相関関数 $\mathcal{O}(\lambda^2)$ ダイアグラム解析報告書

本ドキュメントは、`Kokin_Cho_QFT_term_paper.tex` の Part B 第1問（複素スカラー場 $\lambda(\phi^*\phi)^2$ 理論の摂動論とファインマンダイアグラム）の解答全体に対する精査結果、およびユーザーから指摘された **(5) 以降での 4点関数の 2次 ($\mathcal{O}(\lambda^2)$) 展開における省略（other disconnected, internal loop insertion, vacuum bubble terms の扱い）の妥当性と修正方針** を詳細にまとめたものです。

---

## 1. Part B 第1問 全体精査サマリー ((1) ～ (10))

| 小問 | 内容・テーマ | 評価・精査結果 |
| :--- | :--- | :--- |
| **(1)** | 自由場の生成機能 $Z_0[J, J^*]$ の導出 (Minkowski / Euclidean) | **【完成度：高・正しい】** <br> 正方完成、コンターの $i\epsilon$ 処方、Wick回転が論理的かつ厳密に展開されています。 |
| **(2)** | 自由場の 2点 time-ordered product の計算 | **【完成度：高・正しい】** <br> $U(1)$ 電荷保存による $\langle \phi\phi \rangle = \langle \phi^*\phi^* \rangle = 0$ の証明と、実スカラー場への分解による $\langle \phi\phi^* \rangle = G_0$ の導出が明快です。 |
| **(3)** | 相互作用理論の生成機能 $Z[J, J^*]$ とファインマンルールの導出 | **【完成度：高・正しい】** <br> 機能的微分演算子の外出し式、頂点因子 (Minkowski: $-i 4\lambda$, Euclidean: $-4\lambda$)、伝播関数の向き（$U(1)$ 電荷の流れる方向）が正しく定式化されています。 |
| **(4)** | 真空ダイアグラムの相殺証明 | **【完成度：高・正しい】** <br> $Z[J, J^*] = Z_{\mathrm{connected}}[J, J^*] \cdot Z_{\mathrm{vacuum}}$ のファクタライズにより、規格化分母 $Z[0,0]$ との相殺が簡潔・厳密に証明されています。 |
| **(5)** | 位置空間における (a)真空, (b)2点, (c)4点関数の $\mathcal{O}(\lambda^2)$ 展開と真空相殺の検証 | **【要修正・精査必要箇所】** <br> 4点関数の 2次展開で `+ (other disconnected, internal loop insertion, and vacuum bubble terms)` と一括して省略されています。位置空間での全相関関数の定義および真空相殺の検証という問題要求に対し、**ダイアグラムの分類と数式表現の補強が必要**です。 |
| **(6)** | 運動量空間での 2点 ($\mathcal{O}(\lambda)$) および 4点 ($\mathcal{O}(\lambda^2)$) 関数の計算 | **【論理的に正解】** <br> 4点関数の connected 1PI 散乱部分で $s, t, u$ チャンネルのバブル図のみが残る数式が正しく書かれています。(5) からの論理的ステップ（散乱振幅 / 1PI 頂点への移行）を明記するとより完全になります。 |
| **(7)** | Self-energy $\Sigma(p)$ と有効質量 $m$ の 1次計算 | **【完成度：高・正しい】** <br> ダイソン方程式を用いた $m^2 = m_0^2 + 4\lambda G_0(0)$ の導出と、質量が **renormalized up** される物理的理由（ポテンシャルエネルギーの上昇および仮想粒子クラウドによる慣性増加）の記述が非常に優れています。 |
| **(8)** | 有効結合定数 $g \equiv \Gamma^{(4)}(0,0,0,0)$ の導出 | **【完成度：高・正しい】** <br> ゼロ運動量極限 $s=t=u=0$ における $g = 4\lambda - 48\lambda^2 V(0)$ が正しく導出されています。 |
| **(9)** | Wick回転と虚時間解析接続の幾何学的・物理的意味 | **【完成度：高・正しい】** <br> 複素 $k_0$ 平面における極の位置（第2・第4象限）とコンター回帰の可否、Euclidean時空の性質が明快に解説されています。 |
| **(10)** | 次元正則化 ($D$ 次元) による発散の解析と孤立極の証明 | **【完成度：高・正しい】** <br> $\Gamma(1 - D/2)$ による 2点関数の $D \ge 2$ 発散、および $\Gamma(2 - D/2)$ による 4点関数の $D \ge 4$ 発散と対称点での定式化が極めて正確です。 |

---

## 2. ユーザーの懸念（ (5) における 4点関数省略の妥当性 ）に対する詳細解析

### 2.1. 質問の要点と評価
> **ユーザーの質問:**  
> 「(5)以降での4点相関関数の2次までの議論で other disconnected, internal loop insertion, and vacuum bubble terms を入れずに、s,t,u ch だけを議論するのは大丈夫かどうか。`n=4,k=2.png`（実スカラー $\phi^4$ の図）を見ても矢印が加わることによって減る項はあれど、数式に起こしていないけど残るものもあるような気がします。」

### 2.2. 精査結果：設問 (5) と 設問 (6)/(8) での扱いの違い

この懸念は **理論物理的に極めて鋭く、かつ正当な指摘** です。結論から言うと、**設問 (5) と 設問 (6)/(8) とでは、考慮すべきダイアグラムの範囲が異なります**。

1. **設問 (5) の立場（全相関関数の位置空間展開と真空バブル相殺の検証）:**
   - 設問 (5) で問われているのは、**「フル 4点相関関数 $G^{(4)}(x_1,x_2,x_3,x_4) = \langle 0 | \mathrm{T} \phi(x_1)\phi(x_2)\phi^*(x_3)\phi^*(x_4) | 0 \rangle$ の位置空間における $\lambda^2$ までの摂動展開式」** です。
   - したがって、(5) の段階では **Disconnected 項**（2点関数の積）や **Connected 1PR 項**（タドポール/外線ループ挿入）も本来は相関関数の一部として存在します。
   - これらを `+ (other disconnected...)` と端折ってしまうと、「(5) の問題で要求されている全ダイアグラムの分類と真空バブルの相殺処理の明示」という観点から、**不十分な解答と判断されるリスク**があります。

2. **設問 (6) および (8) の立場（1PI 頂点関数 / 散乱振幅）:**
   - (6) や (8) では、物理的な **connected 1PI 散乱振幅** や **1PI 頂点関数 $\Gamma^{(4)}$** を議論します。
   - この段階になると：
     - **真空バブル (Vacuum Bubbles)**: (4) で証明した規格化分母 $Z[0,0]$ により完全相殺される。
     - **非連結項 (Disconnected Terms)**: 4粒子散乱の connected 行列要素には寄与しない。
     - **1PR タドポール挿入 (1PR Internal Loop Insertions)**: 外線の質量・波動関数再規格化（self-energy $\Sigma$）に吸収されるか、1PI 頂点関数の定義から除外される。
   - したがって、** (6) や (8) の運動量空間での散乱振幅においては、純粋な Connected 1PI ダイアグラムである $s, t, u$ チャンネルのバブル図のみが寄与する** という議論で**完全に正しく、数学的にも正当化されます**。

---

## 3. 複素スカラー場 $\lambda(\phi^*\phi)^2$ における $\mathcal{O}(\lambda^2)$ 4点関数の完全ダイアグラム分類

実スカラー場（$\phi^4$ 理論、`n=4,k=2.png`）と複素スカラー場（$\lambda(\phi^*\phi)^2$ 理論）の最大の違いは、**$U(1)$ 電荷保存規則による伝播関数の向き（矢印）** です。

各頂点には **2つの incoming 線 ($\phi$)** と **2つの outgoing 線 ($\phi^*$)** が必ず接続します。

非ゼロの4点相関関数 $\langle 0 | \mathrm{T} \phi(x_1)\phi(x_2)\phi^*(x_3)\phi^*(x_4) | 0 \rangle$ における $\mathcal{O}(\lambda^2)$ ダイアグラムの分類は以下の 4 カテゴリーに大別されます。

### (I) Connected 1PI Diagrams (s, t, u channels)
4点散乱の主寄与となる連結 1粒子既約図です。

1. **s-channel bubble diagram**:
   - 構造: 外線 $x_1, x_2 (\phi)$ が頂点 $y_1$ に入り、$y_1$ から $y_2$ へ 2本の内部伝播関数（ともに $y_1 \to y_2$）、$y_2$ から外線 $x_3, x_4 (\phi^*)$ へ出る。
   - 数式表現:
     $$4 \lambda^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, G_0(x_1 - y_1) G_0(x_2 - y_1) \left[ G_0(y_1 - y_2) \right]^2 G_0(y_2 - x_3) G_0(y_2 - x_4)$$
2. **t-channel bubble diagram**:
   - 構造: 頂点 $y_1$ に $x_1$ が入り $x_3$ へ出る。頂点 $y_2$ に $x_2$ が入り $x_4$ へ出る。$y_1$ と $y_2$ の間に 2本の内部線（1本は $y_1 \to y_2$、1本は $y_2 \to y_1$）。
   - 数式表現:
     $$4 \lambda^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, G_0(x_1 - y_1) G_0(y_1 - x_3) G_0(y_2 - y_1) G_0(y_1 - y_2) G_0(x_2 - y_2) G_0(y_2 - x_4)$$
3. **u-channel bubble diagram**:
   - 構造: 頂点 $y_1$ に $x_1$ が入り $x_4$ へ出る。頂点 $y_2$ に $x_2$ が入り $x_3$ へ出る。$y_1$ と $y_2$ の間に 2本の内部線（$y_1 \leftrightarrow y_2$）。
   - 数式表現:
     $$4 \lambda^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, G_0(x_1 - y_1) G_0(y_1 - x_4) G_0(y_2 - y_1) G_0(y_1 - y_2) G_0(x_2 - y_2) G_0(y_2 - x_3)$$

### (II) Connected 1PR Diagrams (External line loop insertions / Tadpoles)
外線に 1次のタドポール（セルフループ）が挿入された連結 1粒子可約図です。

- 構造: 1次の樹木構造頂点 $y_1$（$x_1, x_2 \to y_1 \to x_3, x_4$）のいずれかの脚（例: $x_1 \to y_1$）に、別の頂点 $y_2$ でのタドポール $G_0(0) = \langle \phi(y_2)\phi^*(y_2) \rangle_0$ が挿入される。
- 4つの外線それぞれに対して 1種類ずつ（計 4項）存在します。
- 代表項の数式表現 ($x_1$ 脚への挿入):
  $$4 \lambda^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 \, G_0(x_1 - y_2) G_0(0) G_0(y_2 - y_1) G_0(x_2 - y_1) G_0(y_1 - x_3) G_0(y_1 - x_4)$$

### (III) Disconnected Diagrams (非連結項)
外線 4本が 2つの独立した 2点関数の積に分裂するダイアグラム群です。

1. **$\mathcal{O}(\lambda^2)$ 2点関数 $\times$ 自由2点関数**:
   - 例: 2点関数の 2次補正（サンセット図 $G^{(2)}_{\text{sunset}}$ や ダブルタドポール図 $G^{(2)}_{\text{double-tadpole}}$）$\times$ 自由伝播関数 $G_0$。
   - 代表項: $G^{(2)}_{\text{sunset}}(x_1, x_3) G_0(x_2, x_4) + G^{(2)}_{\text{sunset}}(x_2, x_4) G_0(x_1, x_3) + (x_3 \leftrightarrow x_4 \text{ permutations})$
2. **$\mathcal{O}(\lambda^1)$ 2点関数 $\times$ $\mathcal{O}(\lambda^1)$ 2点関数**:
   - 例: 1次タドポール補正を受けた 2点関数どうしの積。
   - 代表項: $G^{(2)}_{\text{tadpole}}(x_1, x_3) G^{(2)}_{\text{tadpole}}(x_2, x_4) + (x_3 \leftrightarrow x_4)$

### (IV) Vacuum Bubble Diagrams (真空バブル項)
全体に掛け合わされる閉じた真空ループです。

1. **自由4点関数 $\times$ $\mathcal{O}(\lambda^2)$ 真空バブル**:
   - $G^{(4)}_0(x_1,x_2,x_3,x_4) \times \left[ (\text{Figure-8})^2 + (\text{Sunset bubble}) + (\text{Double bubble}) \right]$
2. **$\mathcal{O}(\lambda^1)$ 連結4点関数 $\times$ $\mathcal{O}(\lambda^1)$ 真空バブル**:
   - $G^{(4)}_{\lambda^1,\text{tree}}(x_1,x_2,x_3,x_4) \times (\text{Figure-8 bubble})$

---

## 4. 真空バブルの相殺メカニズムの明示

Part B Q1 (4) で示されたように、物理的な $n$ 点相関関数は規格化された生成機能微分で定義されます：
$$\langle \mathrm{T} \phi(x_1)\phi(x_2)\phi^*(x_3)\phi^*(x_4) \rangle = \frac{1}{Z[0,0]} \left. \frac{\delta^4 Z[J,J^*]}{\delta J^*(x_1) \delta J^*(x_2) \delta J(x_3) \delta J(x_4)} \right|_{J=0}$$

ここで、$Z[J,J^*] = Z_{\mathrm{connected+disconnected}}[J,J^*] \times Z_{\mathrm{vacuum}}$ であり、分子の $Z_{\mathrm{vacuum}} = Z[0,0]$ と分母の $Z[0,0]$ が**完全相殺**します。

その結果：
- **真空バブル項 (IV)** は分子分母の相殺により**完全に消滅**します。
- 真空相殺後に残るのは **(I) Connected 1PI + (II) Connected 1PR + (III) Disconnected** のみとなります。
- さらに、S行列振幅（散乱振幅）や 1PI 頂点関数 $\Gamma^{(4)}$ の導出（設問 (6), (8)）においては、LSZ簡約処方および外線再規格化により (II) と (III) が除外され、**純粋な (I) Connected 1PI (s, t, u チャンネル) のみが残る**ことになります。

---

## 5. `Kokin_Cho_QFT_term_paper.tex` への具体改訂提案

TeXファイルの (5) および (6) の記述を、上記を踏まえてより厳密かつ分かりやすく修正するためのコード案です。

### 5.1. (5) の 4点関数記述の改訂案 (Lines 800–858 付近)

```latex
\subparagraph*{Order $\lambda^2$ ($k=2$)}\mbox{}\par
In the expansion of the full four-point function $G^{(4)}(x_1, x_2, x_3, x_4) = \langle 0 | \mathrm{T} \phi(x_1)\phi(x_2)\phi^*(x_3)\phi^*(x_4) | 0 \rangle$ at order $\lambda^2$, the diagrams are classified into four distinct topological categories:
\begin{enumerate}
    \item \textbf{Connected 1PI diagrams ($s, t, u$ channels)}:
    \begin{align*}
    G^{(4)}_{k=2, \mathrm{1PI}}(x_1, x_2, x_3, x_4) = 4\lambda^2 \int \mathrm{d}^4 y_1 \mathrm{d}^4 y_2 &\left[ G_0(x_1-y_1) G_0(x_2-y_1) (G_0(y_1-y_2))^2 G_0(y_2-x_3) G_0(y_2-x_4) \right. \\
    &\;\; + G_0(x_1-y_1) G_0(y_1-x_3) G_0(y_2-y_1) G_0(y_1-y_2) G_0(x_2-y_2) G_0(y_2-x_4) \\
    &\;\; \left. + G_0(x_1-y_1) G_0(y_1-x_4) G_0(y_2-y_1) G_0(y_1-y_2) G_0(x_2-y_2) G_0(y_2-x_3) \right].
    \end{align*}
    \item \textbf{Connected 1PR diagrams (Tadpole loop insertion on external lines)}:
    Diagrams where a first-order tree 4-point vertex has a tadpole loop $G_0(0)$ inserted on one of its external legs (4 permutations for the 4 legs).
    \item \textbf{Disconnected diagrams}:
    Products of two independent 2-point functions, e.g., $G^{(2)}_{\lambda^2}(x_1, x_3) G_0(x_2, x_4) + G^{(2)}_{\lambda^1}(x_1, x_3) G^{(2)}_{\lambda^1}(x_2, x_4) + (x_3 \leftrightarrow x_4)$.
    \item \textbf{Vacuum bubble terms}:
    Terms factoring into lower-order 4-point functions multiplied by disconnected vacuum bubbles (such as the figure-8 squared bubble or sunset vacuum bubble).
\end{enumerate}

\paragraph{(d) Factorization and Verification of Vacuum Diagram Cancellation}
As proven in part (4), the full path-integral expression factors into $Z[J, J^*] = Z_{\mathrm{no-vac}}[J, J^*] \times Z[0,0]$. Dividing by the partition function $Z[0,0]$ in the definition of physical correlation functions cancels out all vacuum bubble diagrams in category (4) identically. 

Consequently, the physical four-point correlation function after vacuum cancellation consists strictly of the connected (1PI + 1PR) and disconnected correlation parts:
\begin{equation}
G^{(4)}_{\mathrm{phys}}(x_1, x_2, x_3, x_4) = G^{(4)}_{k=2, \mathrm{1PI}} + G^{(4)}_{k=2, \mathrm{1PR}} + G^{(4)}_{k=2, \mathrm{disc}} + \mathcal{O}(\lambda^3).
\end{equation}
```

### 5.2. (6) の冒頭での追記補足案 (Line 865 付近)

```latex
\begin{proofbox}
When passing to momentum space to compute the scattering amplitude / 1PI four-point vertex function $\Gamma^{(4)}(p_1, p_2; p_3, p_4)$, the disconnected terms do not contribute to connected scattering processes, and the 1PR tadpole insertions are absorbed into the external line mass and wave-function renormalizations. Therefore, only the connected 1PI diagrams ($s, t, u$ channels) contribute to the amputated 4-point vertex function.
```

---

## 6. 結論・アドバイスまとめ

1. **ユーザーの直感・疑問は100% 正解です。**  
   (5) の設問において `+ (other disconnected...)` と書くのは省略しすぎであり、全相関関数の摂動展開と真空バブル相殺を体系的に説明するためには、4つのカテゴリー（1PI Connected, 1PR Connected, Disconnected, Vacuum Bubble）への全分類を明記すべきです。

2. **(6), (8) で $s, t, u$ チャンネルのみになる理由は論理的に完璧に説明可能です。**  
   運動量空間での S行列散乱振幅 / 1PI 頂点関数では、真空バブルが相殺され、Disconnected 項が除外され、1PR 項が質量再規格化に吸収されるため、$s, t, u$ チャンネルのバブル図のみが生き残ります。この理由を文脈として一言書き添えることで、解答の説得力と完成度が最高レベルに達します。
