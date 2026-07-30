# LaTeXにおけるファインマン・ダイアグラム描画パッケージ比較・検証レポート

LaTeX でファインマン・ダイアグラムを綺麗かつ効率的に描くためのパッケージを実際にコンパイルし、出力画像を含めて比較検証しました。

---

## 1. 比較検証結果まとめ

| パッケージ名 | 美しさ・描画品質 | 使いやすさ | コンパイラ互換性 | 総合評価 |
| :--- | :---: | :---: | :---: | :---: |
| **`tikz-feynman`** (推奨) | ★★★★★ (極めて美麗) | ★★★★★ (直感的・短文) | `lualatex` 推奨 (`pdflatex`可) | **第 1 位（圧倒的最高品質）** |
| **Vanilla `TikZ` + `decorations`** | ★★★★☆ (カスタマイズ可) | ★★★☆☆ (位置手動調整) | 全環境 (`uplatex`, `pdflatex`等) | **第 2 位（完全エンジン非依存）** |
| **`feynmp-auto` / `feynmf`** | ★★★☆☆ (クラシック) | ★★☆☆☆ (MetaPost設定難) | 古い環境向け | 第 3 位（現代では非推奨） |

---

## 2. 実効比較と生成された画像

### 【第 1 位】`tikz-feynman` パッケージ

最もモダンで、物理の論文・レポートで標準的に用いられているパッケージです。

- **長所**: 矢印の配置、波線、ドット（頂点）の位置決めが最もエレガント。`a -- [fermion] b` のような直感的な構文で書けます。
- **実証コンパイル画像**:

![tikz-feynman 樹状図テスト画像](file:///Users/chokokin/.gemini/antigravity-ide/brain/2942c40c-bbc3-4c74-aeba-e16e37b72ac4/test_tikz_feynman_out-1.png)

#### コード例
```latex
\usepackage[compat=1.1.0]{tikz-feynman}

\begin{tikzpicture}
  \begin{feynman}
    \diagram [horizontal=a to b] {
      i1 [particle=$w_1$] -- [anti fermion] a [dot] -- [fermion] i2 [particle=$w_2$],
      a -- [photon, edge label=$p$] b [dot],
      f1 [particle=$z_1$] -- [fermion] b -- [anti fermion] f2 [particle=$z_2$],
    };
  \end{feynman}
\end{tikzpicture}
```

---

### 【第 2 位】Vanilla `TikZ` + `decorations`

標準の `TikZ` パッケージのみを使い、マクロでフェルミオン矢印や光子波線を定義する方法です。

- **長所**: 追加の特殊パッケージや Lua 依存がなく、`uplatex + dvipdfmx` や `pdflatex` など **どんな環境でも 100% コンパイルが通る** のが最大の強みです。
- **実証コンパイル画像**:

![Vanilla TikZ 4点頂点画像](file:///Users/chokokin/.gemini/antigravity-ide/brain/2942c40c-bbc3-4c74-aeba-e16e37b72ac4/test_vanilla_tikz_out-1.png)

#### コード例
```latex
\usepackage{tikz}
\usetikzlibrary{decorations.pathmorphing, decorations.markings}

\tikzset{
  fermion/.style={postaction={decorate}, decoration={markings, mark=at position 0.55 with {\arrow{stealth}}}},
  photon/.style={decorate, decoration={snake, amplitude=2pt, segment length=5pt}},
  vertex/.style={circle, fill=black, inner sep=1.5pt}
}

\begin{tikzpicture}
  \node[vertex, label=above:$x$] (v) at (0,0) {};
  \draw[fermion] (-1.5, 1) -- (v);
  \draw[fermion] (-1.5,-1) -- (v);
  \draw[fermion] (v) -- (1.5, 1);
  \draw[fermion] (v) -- (1.5,-1);
\end{tikzpicture}
```

---

## 3. 結論とおすすめの使い分け

1. **品質と書きやすさ最優先（超おすすめ）**:
   - **`tikz-feynman`** を使用し、`lualatex` または `pdflatex` でコンパイルするのがベストです。
2. **既存の `uplatex + dvipdfmx` 環境を変更せず安全に動かしたい場合**:
   - **Vanilla `TikZ` + `decorations`** をスタイル定義して使うのが最も確実です。
