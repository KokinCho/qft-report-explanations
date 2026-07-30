# Part B 第1問 (6) のダイアグラム選定および係数の厳密導出解説

本ドキュメントは、複素スカラー場 $\lambda(\phi^*\phi)^2$ 理論における **(6) 運動量空間での 2点関数および 4点関数の摂動展開と係数（Symmetry / Combinatorial factors）の完全な修正・解説** です。

---

## 1. 設問 (6) で使用するダイアグラムの選定

### Q: (6) で使うダイアグラムは何ですか？ 1PI のものだけですか？

**回答:**
1. **2点関数 $G^{(2)}(p)$ (order $\lambda$ まで):**
   - **0次 (tree level)**: 自由伝播関数 $G_0(p) = \frac{1}{p^2 + m_0^2}$
   - **1次 ($\mathcal{O}(\lambda^1)$)**: **タドポール図 (Tadpole diagram)**
     - 頂点から出る 1つのセルフループ $G_0(0) = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{k^2+m_0^2}$ を持つ図。

2. **4点関数 $G^{(4)}(p_1, p_2; p_3, p_4)$ (order $\lambda^2$ まで):**
   - 物理的な散乱振幅（S行列要素）および **1PI 4点頂点関数 $\Gamma^{(4)}$**（Connected Amputated 4-point function）においては、以下の理由により **1PI ダイアグラム（$s, t, u$ チャンネルの 1ループバブル図）のみが寄与** します：
     - **真空バブル (Vacuum bubbles)**: Part B (4) の通り、規格化分母 $Z[0,0]$ で完全にキャンセル消滅。
     - **非連結項 (Disconnected terms)**: 粒子相互作用を伴わない自由伝播過程であり、連結 4点関数 $G^{(4)}_{\mathrm{conn}}$ から除外。
     - **1PR タドポール外線挿入項 (1-Particle Reducible tadpoles)**: 外線の質量および波動関数再規格化（self-energy $\Sigma$）に吸収されるため、1PI 頂点関数の定義から除外。
   - したがって、4点頂点関数 $\Gamma^{(4)}$ の計算で考慮する 2次ダイアグラムは **純粋な Connected 1PI である $s, t, u$ チャンネルのバブル図のみ** となります。

---

## 2. 係数（Symmetry Factors）の厳密導出

### 2.1. 2点関数の 1次係数 ($\mathcal{O}(\lambda^1)$)

作用の相互作用項は $-\lambda \int \mathrm{d}^4 z (\phi^* \phi)^2 = -\lambda \int \mathrm{d}^4 z \, \phi^* \phi^* \phi \phi$ です。
2点相関関数 $\langle \mathrm{T} \phi(x) \phi^*(y) \rangle$ の 1次補正における Wick 収縮の組合せ数：
- 外線 $\phi(x)$ が頂点の $\phi^*(z)$ 2つのうち 1つと収縮 $\to 2$ 通り
- 外線 $\phi^*(y)$ が頂点の $\phi(z)$ 2つのうち 1つと収縮 $\to 2$ 通り
- 頂点に残った $\phi(z)$ と $\phi^*(z)$ が自セルフループ（タドポール）を形成 $\to 1$ 通り

**合計収縮数 = $2 \times 2 \times 1 = 4$ 通り**

位置空間:
$$-4\lambda \int \mathrm{d}^4 z \, G_0(x-z) G_0(0) G_0(z-y)$$

運動量空間（2本外線 $G_0(p)$ を含む）:
$$G^{(2)}(p) = G_0(p) - 4\lambda G_0(p)^2 G_0(0) + \mathcal{O}(\lambda^2)$$

**2点関数の 1次までの係数は $-4\lambda$ です。**

---

### 2.2. 4点関数の 1次・2次係数 ($\mathcal{O}(\lambda^1)$ & $\mathcal{O}(\lambda^2)$)

ユーザー様の手書き図 `n=4,k=2_complex.png` における収縮数（Symmetry factors）から運動量空間の式を導出します。

#### (A) 1次 ($\mathcal{O}(\lambda^1)$) 樹木頂点
- 入線 2本 ($\phi$) $\times$ 頂点 $\phi^*$ 2本 $\to 2! = 2$ 通り
- 出線 2本 ($\phi^*$) $\times$ 頂点 $\phi$ 2本 $\to 2! = 2$ 通り
- 収縮数 = $2 \times 2 = 4$ 通り。
- 1次頂点: **$-4\lambda$**

#### (B) 2次 ($\mathcal{O}(\lambda^2)$) 1PI チャンネル別係数
展開係数 $\frac{1}{2!} (-\lambda)^2 = \frac{1}{2}\lambda^2$ に手書き図の収縮数を掛け合わせます。

1. **s-channel 1PI bubble**:
   - 手書き図の収縮数 = **8**
   - 係数 = $\frac{1}{2}\lambda^2 \times 8 = \mathbf{4\lambda^2}$
   - 寄与: $+4\lambda^2 V(s)$

2. **t-channel 1PI bubble**:
   - 手書き図の収縮数 = **16**
   - 係数 = $\frac{1}{2}\lambda^2 \times 16 = \mathbf{8\lambda^2}$
   - 寄与: $+8\lambda^2 V(t)$

3. **u-channel 1PI bubble**:
   - 手書き図の収縮数 = **16**
   - 係数 = $\frac{1}{2}\lambda^2 \times 16 = \mathbf{8\lambda^2}$
   - 寄与: $+8\lambda^2 V(u)$

---

## 3. 運動量空間 4点関数の最終確定式 (設問 (6))

$$G^{(4)}_{\text{conn, 1PI}}(p_1, p_2; p_3, p_4) = (2\pi)^4 \delta^4(p_1+p_2-p_3-p_4) \left[ -4\lambda + 4\lambda^2 V(s) + 8\lambda^2 V(t) + 8\lambda^2 V(u) \right] \prod_{i=1}^4 G_0(p_i)$$

ここで、ループ積分 $V(q)$ は以下で定義されます：
$$V(q) = \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{(k^2+m_0^2)((k-q)^2+m_0^2)}$$

### 補足：設問 (8) 有効結合定数 $g$ への影響
ゼロ運動量極限 $p_i = 0$ ($s=t=u=0$) において：
$$g \equiv \Gamma^{(4)}(0,0,0,0) = 4\lambda - (4 + 8 + 8)\lambda^2 V(0) = 4\lambda - 20\lambda^2 V(0) + \mathcal{O}(\lambda^3)$$
(8) の式もこれに伴い $48\lambda^2 \to 20\lambda^2$ へ正しく修正されます！
