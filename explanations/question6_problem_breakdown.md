# 場の量子論 期末レポート Part B Question 1 (6) 問題要求の要約と解説

## 1. 問題文（原文）
> **(6)** Calculate the two-point functions and the four-point functions in Euclidean spacetime in momentum space to order $\lambda$ for the two-point functions and to order $\lambda^2$ for the four-point functions. Draw a Feynman diagram for each term in momentum space. Do not do the integrals!

---

## 2. 聞かれていること（3つの要点）

1. **計算対象と適用範囲**:
   - **ユークリッド空間（Euclidean spacetime）** の **運動量空間（momentum space）** において相関関数を求める。
   - **2点関数 $G^{(2)}(p)$**: 結合定数 $\lambda$ の **1次（$\mathcal{O}(\lambda)$）まで**。
   - **4点関数 $G^{(4)}(p_1, p_2, p_3, p_4)$**: 結合定数 $\lambda$ の **2次（$\mathcal{O}(\lambda^2)$）まで**。

2. **図示の指定**:
   - 運動量空間における各項に対応する **ファインマン・ダイアグラムを描く**（運動量保存則や外線運動量・内部ループ運動量を図中に明記する）。

3. **計算の到達レベル（積分の扱い）**:
   - **「Do not do the integrals!（積分は実行しないこと！）」** とあるため、ループ積分（$\int \frac{\mathrm{d}^4 k}{(2\pi)^4} \dots$）を評価して数値を出す必要はなく、**積分の式の形のまま書き下せばよい**。

---

## 3. 具体的な数式構成

### (1) 2点関数 $G^{(2)}(p)$ （$\mathcal{O}(\lambda)$ まで）
- **0次項（自由プロパゲータ）**: $G_0(p) = \frac{1}{p^2 + m_0^2}$
- **1次項（タドポール項）**: $-4\lambda G_0(p)^2 \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2 + m_0^2}$

### (2) 4点関数 $G^{(4)}(p_1, p_2, p_3, p_4)$ （$\mathcal{O}(\lambda^2)$ まで）
- **1次項（ツリー頂点）**: $-4\lambda \prod_{i=1}^4 G_0(p_i) \times (2\pi)^4 \delta^4(\sum p_i)$
- **2次項（1ループ連結項 $s, t, u$ チャンネル）**: 
  - $s$-channel 1ループバブル積分
  - $t$-channel 1ループバブル積分
  - $u$-channel 1ループバブル積分
