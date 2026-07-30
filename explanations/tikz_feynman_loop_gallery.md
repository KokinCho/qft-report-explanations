# `tikz-feynman` における各種ループ・ダイアグラムのテスト・検証ギャラリー

`tikz-feynman` を用いて、QFT の計算で登場する各種ループ・ダイアグラム（1ループ散乱、スイカ型真空ダイアグラム、タッドポール等）をコンパイル検証した結果です。

---

## 1. 1ループ 4点散乱ダイアグラム ($s$-channel 1-loop)

2つの頂点 $z_1, z_2$ の間に 2 本の伝播関数がループを形成する $s$ チャンネル散乱ダイアグラムです。

![s-channel 1-loop 散乱ダイアグラム](file:///Users/chokokin/.gemini/antigravity-ide/brain/2942c40c-bbc3-4c74-aeba-e16e37b72ac4/test_tikz_feynman_all_loops_out-4.png)

### TikZ コード
```latex
\begin{tikzpicture}
  \begin{feynman}
    \vertex (w1) {$w_1$};
    \vertex [below=2cm of w1] (w2) {$w_2$};
    \vertex [right=1.2cm of w1] (dummy1);
    \vertex [below=1cm of dummy1] (z1) [label=left:$z_1$];
    \vertex [right=1.5cm of z1] (z2) [label=right:$z_2$];
    \vertex [right=1.2cm of z2] (dummy2);
    \vertex [above=1cm of dummy2] (f1) {$z_1'$};
    \vertex [below=1cm of dummy2] (f2) {$z_2'$};
    \diagram* {
      (w1) -- [fermion] (z1),
      (w2) -- [fermion] (z1),
      (z1) -- [fermion, bend left=50] (z2),
      (z1) -- [anti fermion, bend right=50] (z2),
      (z2) -- [fermion] (f1),
      (z2) -- [fermion] (f2),
    };
  \end{feynman}
\end{tikzpicture}
```

---

## 2. スイカ型 / Sunset 真空ダイアグラム ($\mathcal{O}(\lambda^2)$ 真空ループ)

時空点 $x$ と $y$ の間に 4 本の伝播関数が走る 2 次の真空バブルダイアグラムです。

![Sunset 真空ダイアグラム](file:///Users/chokokin/.gemini/antigravity-ide/brain/2942c40c-bbc3-4c74-aeba-e16e37b72ac4/test_tikz_feynman_all_loops_out-2.png)

### TikZ コード
```latex
\begin{tikzpicture}
  \begin{feynman}
    \vertex (x) [label=left:$x$];
    \vertex [right=2cm of x] (y) [label=right:$y$];
    \diagram* {
      (x) -- [fermion, bend left=75] (y),
      (x) -- [fermion, bend left=25] (y),
      (y) -- [fermion, bend left=25] (x),
      (y) -- [fermion, bend left=75] (x),
    };
  \end{feynman}
\end{tikzpicture}
```

---

## 3. 検証結論

`tikz-feynman` においては、`bend left` や `bend right` オプションを活用することで、複雑な多元ループや自己ループ（Bubble / Sunset / Tadpole / Box）も非常にエレガントに描画できることが確認されました。
