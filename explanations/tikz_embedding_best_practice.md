# LaTeX における TikZ 図の埋め込み方式比較と推奨ベストプラクティス

質問：
「元のレポートにそのまま TikZ をベタ打ち（インライン記述）するのと、別ファイルで作ってから画像/PDF として `\includegraphics` で埋め込むのはどちらが良いか？」

---

## 1. 2つの方式の完全比較表

| 評価項目 | 方式 A: 別ファイルで作って埋め込み (`\includegraphics`) | 方式 B: メイン文書に TikZ をベタ打ち |
| :--- | :--- | :--- |
| **メイン文書のコンパイル速度** | **圧倒的に高速 (0.1秒)** | 毎回 TikZ が再描画され**重い (数秒〜十数秒)** |
| **エラーの分離・デバッグのしやすさ** | **極めて容易** (図単体でエラー修正可能) | 図のエラーで**メイン文書全体のコンパイルが停止** |
| **自動コンパイル環境との相性** | **最高** (保存ごとの自動再コンパイルが爆速) | 低い (保存のたびに待たされる) |
| **ファイル管理** | `figures/` フォルダが必要 | `.tex` 1ファイルで完結 |
| **フォントの一貫性** | PDF化なら100%完全一致 | 100%完全一致 |

---

## 2. 結論：【方式 A（別ファイル作製＋埋め込み）】が圧倒的に推奨されます！

特に、ユーザー様が現在お使いの **「編集・保存したら自動でコンパイルされる環境」** においては、**方式 A が圧倒的に快適かつ安全** です。

### 方式 A を推奨する 3 つの決定的な理由

1. **自動コンパイルが重くならない（爆速を維持できる）**:
   TikZ や `tikz-feynman` をメイン文書に数十個ベタ打ちすると、保存するたびに LaTeX がすべての図のノード計算と波線・矢印の描画処理をやり直すため、ビルド待ち時間が発生します。
   図を独立した PDF/PNG として `figures/` に作っておけば、メイン文書は画像をロードするだけなので、保存後が一瞬（0.1秒）で終わります。

2. **コンパイルエラーの完全分離**:
   図の座標の微調整やタイポでエラーが起きた際、独立した図ファイルだけを修正すればよいため、メイン論文全体のビルドが壊れるリスクがゼロになります。

3. **レイアウト調整のしやすさ**:
   `\includegraphics[width=0.25\textwidth]{figures/figure8.pdf}` のように、文章中での図の大きさや配置の調整が数値をいじるだけで極めて直感的に行えます。

---

## 3. 推奨されるフォルダ・ファイル構成とコード例

```
場の量子論/
├── Kokin_Cho_QFT_term_paper.tex  (メインレポート)
└── figures/                     (図専用フォルダ)
    ├── fig_figure8.tex          (standalone TikZ ソース)
    ├── fig_figure8.pdf          (コンパイル済み PDF)
    ├── fig_sunset.tex
    ├── fig_sunset.pdf
    ├── fig_tadpole.tex
    └── fig_tadpole.pdf
```

### 図ファイル `figures/fig_figure8.tex` の書き方
```latex
\documentclass[tikz,border=5pt]{standalone}
\usepackage[compat=1.1.0]{tikz-feynman}
\begin{document}
\begin{tikzpicture}
  \begin{feynman}
    \vertex (v) [dot, label=below:$x$];
    \diagram* {
      (v) -- [fermion, out=45, in=135, min distance=1.5cm] (v),
      (v) -- [anti fermion, out=-45, in=-135, min distance=1.5cm] (v),
    };
  \end{feynman}
\end{tikzpicture}
\end{document}
```

### メイン文書 `Kokin_Cho_QFT_term_paper.tex` での埋め込み方
```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.25\linewidth]{figures/fig_figure8.pdf}
  \caption{Figure-8 vacuum diagram at $\mathcal{O}(\lambda^1)$.}
  \label{fig:figure8}
\end{figure}
```
