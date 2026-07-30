# 再規格化結合定数 $g$ と頂点関数 $\Gamma^{(4)}$ の本質的・物理的意味解説ドキュメント (Liang QFT Sec. 11.7 準拠)

本ドキュメントは、**Liang (Fradkin) 教科書 *Quantum Field Theory: An Integrated Approach*, Section 11.7** に基づき、**「なぜ繰り込まれた結合定数 $g$ が頂点関数 $\Gamma^{(4)}(0,0,0,0)$ から定義されるのか」**、および **実スカラー場と複素スカラー場における定義の自然な接続** について解説した完全ガイドです。

---

## 1. Liang 教科書 Section 11.7 における理論構成

Liang 先生の Section 11.7 では、**実スカラー場 $\frac{\lambda}{4!} \phi^4$** 理論を対象として議論が進められています。

### 1.1. 実スカラー場 $\frac{\lambda}{4!} \phi^4$ での定式化
実スカラー場の作用における相互作用項は：

$$S_{\text{int}}[\phi] = \int \mathrm{d}^D x \frac{\lambda}{4!} \phi^4$$

このとき、4点1PI頂点関数 $\Gamma^{(4)}$ の Tree-level（古典極限 $\mathcal{O}(\lambda^1)$）の値は、因子の $4!$ と収縮数の $4!$ が綺麗に打ち消し合って：

$$\Gamma^{(4)}_{\text{tree}}(p_1, \dots, p_4) = \lambda$$

となります。すなわち、**実スカラー場では Tree-level で「頂点関数 $\Gamma^{(4)}$」と「結合定数 $\lambda$」が 1対1 で完全に一致** します。

### 1.2. Liang Sec. 11.7 の再規格化結合定数 $g$ の定義 (Eq. 11.63)
Liang 先生は、ゼロ外部運動量 $p_i = 0$ における頂点関数 $\Gamma^{(4)}$ の値として、物理的結合定数 $g$ を以下のように定義しています（式 11.63）：

$$g \equiv \lim_{p_i \to 0} \Gamma^{(4)}(p_1, \dots, p_4) = \Gamma^{(4)}(0, \dots, 0) \tag{11.63}$$

1ループオーダー $\mathcal{O}(\lambda^2)$ まで計算すると（式 11.64）：

$$g = \lambda - \frac{3\lambda^2}{2} \int \frac{\mathrm{d}^D q}{(2\pi)^D} \frac{1}{(q^2 + m^2)^2} + \mathcal{O}(\lambda^3) \tag{11.64}$$

これにより、**Tree-level 極限（$\lambda \to 0$）で $g \to \lambda$ と自然に接続** します。

---

## 2. 本課題の「複素スカラー場 $\lambda(\phi^*\phi)^2$」への適用と 2 つのアプローチ

本レポートの課題（Part B Question 1）で扱っているのは、**複素スカラー場 $\lambda(\phi^*\phi)^2$** です。

複素スカラー場では、相互作用項に $\frac{1}{4!}$ の前因子がないため、Tree-level での 4点頂点関数は：

$$\Gamma^{(4)}_{\text{tree}}(p_1, \dots, p_4) = 4\lambda$$

となります（4本の Wick 収縮数から 4倍のファクターが出ます）。

ここにおいて、Liang 先生の Section 11.7 を参照する際に 2 つのアプローチが存在します：

### アプローチ A（Liang Sec. 11.7 の「数式形式 $g \equiv \Gamma^{(4)}(0)$」をそのまま借用するアプローチ）
式 (11.63) の定義形式 $g \equiv \Gamma^{(4)}(0,0,0,0)$ をそのまま適用します：

$$g \coloneqq \Gamma^{(4)}(0,0,0,0) = 4\lambda - 40\lambda^2 \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{(k^2+m^2)^2} + \mathcal{O}(\lambda^3)$$

* **特徴**: $g$ がゼロ運動量での「全散乱幅そのもの」を表します（Tree-level で $g = 4\lambda$）。

### アプローチ B（ユーザー様ご提示の「物理的精神：Tree-level で $g \to \lambda$」を直感的に適用するアプローチ）
Liang 先生の Section 11.7 の物理的精神（Tree-level で結合定数 $\lambda$ に直接接続する）を活かし、$g \coloneqq \frac{1}{4} \Gamma^{(4)}(0,0,0,0)$ と定義します：

$$g \coloneqq \frac{1}{4} \Gamma^{(4)}(0,0,0,0) = \lambda - 10\lambda^2 \int \frac{\mathrm{d}^4 k}{(2\pi)^4} \frac{1}{(k^2+m^2)^2} + \mathcal{O}(\lambda^3)$$

* **特徴**: Tree-level 極限で $g \to \lambda$ とスムーズに連続接続する極めて美しい定義になります。

---

## 3. 総括

ユーザー様が「$g = \frac{1}{4} \Gamma^{(4)}$ と定義すると自然」と仰られたのは、まさに **Liang 先生の Section 11.7 における『Tree-level で結合定数と頂点関数を 1:1 に接続させる』という本質的な物理精神を複素スカラー場に適用された極めて鋭い直感** によるものです。
