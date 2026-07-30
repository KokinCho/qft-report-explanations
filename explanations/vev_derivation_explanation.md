# 複素スカラー場における $T$ 積真空期待値の微分の計算と物理的理由

## 1. 生成汎関数 $Z_0[J, J^*]$ からの微分計算（数学的理由）

(1) で導出した自由複素スカラー場の生成汎関数は以下の形をしています：

$$
Z_0[J, J^*] = \exp\left( -i \int \mathrm{d}^4 u \, \mathrm{d}^4 v \, J^*(u) D_F(u-v) J(v) \right)
$$

経路積分の定義より、場の演算子は外源 $J, J^*$ による汎関数微分で次のように置き換わります：

$$
\hat{\phi}(x) \longleftrightarrow \frac{\delta}{i \delta J^*(x)}, \qquad \hat{\phi}^*(x) \longleftrightarrow \frac{\delta}{i \delta J(x)}
$$

---

### (a) $\langle 0 | T \hat{\phi}(x) \hat{\phi}(x') | 0 \rangle = 0$ の直接計算

この真空期待値を求めるには、$Z_0[J, J^*]$ を **$J^*$ だけについて 2 回微分** します：

$$
\langle 0 | T \hat{\phi}(x) \hat{\phi}(x') | 0 \rangle = \left. \frac{1}{i^2} \frac{\delta^2 Z_0[J, J^*]}{\delta J^*(x) \delta J^*(x')} \right|_{J=J^*=0}
$$

1. **1 回目の微分 $\frac{\delta}{\delta J^*(x)}$**:
   積の肩にある $J^*(u)$ を微分すると $u = x$ に固定され、指数関数の微分規則により：

   $$
   \frac{\delta Z_0[J, J^*]}{\delta J^*(x)} = \left( -i \int \mathrm{d}^4 v \, D_F(x-v) J(v) \right) Z_0[J, J^*]
   $$

2. **2 回目の微分 $\frac{\delta}{\delta J^*(x')}$**:
   積の微分法則（Leibniz rule）を適用します。
   - カッコ内の項 $\left( -i \int \mathrm{d}^4 v \, D_F(x-v) J(v) \right)$ には **$J^*(x')$ が含まれていない** ため、$J^*(x')$ 微分はゼロになります。
   - 右側の $Z_0[J, J^*]$ 部分を微分すると、再び同じ形の項が降ってきます：

   $$
   \frac{\delta^2 Z_0[J, J^*]}{\delta J^*(x) \delta J^*(x')} = \left( -i \int \mathrm{d}^4 v \, D_F(x-v) J(v) \right) \left( -i \int \mathrm{d}^4 w \, D_F(x'-w) J(w) \right) Z_0[J, J^*]
   $$

3. **最後に $J = J^* = 0$ とおく**:
   両方のカッコ内に未微分の外源 $J(v)$ および $J(w)$ がそのまま残っているため、$J=0$ とおくと**全体が厳密にゼロ**になります：

   $$
   \left. \frac{\delta^2 Z_0}{\delta J^*(x) \delta J^*(x')} \right|_{J=J^*=0} = 0
   $$

---

### (b) 混合期待値 $\langle 0 | T \hat{\phi}(x) \hat{\phi}^*(x') | 0 \rangle = i D_F(x-x')$ の場合（比較）

一方で、異種の源 $J^*(x)$ と $J(x')$ で 1 回ずつ微分する場合を比較してみます：

1. 1回目 $\frac{\delta Z_0}{\delta J^*(x)} = \left( -i \int \mathrm{d}^4 v \, D_F(x-v) J(v) \right) Z_0[J, J^*]$
2. 2回目 $\frac{\delta}{\delta J(x')}$ を計算すると、カッコ内の $J(v)$ 自体が $\frac{\delta J(v)}{\delta J(x')} = \delta^{(4)}(v - x')$ と微分されて消滅します！

$$
\frac{\delta^2 Z_0}{\delta J^*(x) \delta J(x')} = -i D_F(x-x') \, Z_0[J, J^*] + (\text{$J$ が残る項})
$$

最後に $J=J^*=0$ とおくと、$J$ が消えて定数となった $-i D_F(x-x')$ だけが残り、係数 $1/i^2 = -1$ をかけることで：

$$
\langle 0 | T \hat{\phi}(x) \hat{\phi}^*(x') | 0 \rangle = \frac{-i D_F(x-x')}{-1} = i D_F(x-x') \neq 0
$$

と非ゼロのプロパゲータが得られます。

---

## 2. $U(1)$ 電荷保存則による直観的理由（物理的意味）

自由複素スカラー場の作用は、位相変換 $\phi \to e^{i\theta} \phi, \phi^* \to e^{-i\theta} \phi^*$ に対する **グローバル $U(1)$ 対称性** を持っています。

- 粒子場 $\hat{\phi}$ は $U(1)$ 電荷 **$+1$** を持ちます（粒子を生成、反粒子を消滅）。
- 反粒子場 $\hat{\phi}^*$ は $U(1)$ 電荷 **$-1$** を持ちます（反粒子を生成、粒子を消滅）。
- 真空 $|0\rangle$ の電荷は **$0$** です。

1. $\hat{\phi}(x) \hat{\phi}(x') |0\rangle$ という状態の全電荷は $+1 + 1 = +2$ です。電荷 $0$ の真空 $\langle 0 |$ との内積をとると、**電荷が保存しないため内積はゼロ** になります。
2. $\hat{\phi}(x) \hat{\phi}^*(x') |0\rangle$ の全電荷は $+1 - 1 = 0$ であり、真空と同じ電荷を持つため、非ゼロの遷移振幅（プロパゲータ）を持ちます。

生成汎関数の指数の中が常に $J^* J$ のペアになっているのは、この $U(1)$ 電荷保存則が指数関数の構造として組み込まれているためです。
