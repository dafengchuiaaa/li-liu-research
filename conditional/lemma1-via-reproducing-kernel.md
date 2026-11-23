# Lemma 1：修正后的 Cauchy 边界局部化与连续核主项

- **对应仓库路径**：`conditional/lemma1-via-reproducing-kernel.md`
- **状态**：已独立核对 Li–Liu 原论文式 (2.6)、(2.9)–(2.17) 与 Theorem 6.1，解析证明已闭合（依赖 $\mathrm{GRH}(2p)$）
- **原始文献**：Jiamin Li & Jianya Liu, *A Conditional Proof of the Goldbach Conjecture* (2026-11-13)

---

## 1. Li–Liu 原论文定义与公式核对

设 $N$ 为偶数（本文取 $N = 2p$，$p \to \infty$ 为奇素数），$L = \log(2p)$。记 $X_N^-$ 为模 $N$ 的奇 Dirichlet 特征族（对 $N=2p$，$|X_{2p}^-| = \frac{p-1}{2}$）。双变量记为 $(s, z)$，设 $w = s + z$。

1. **算术核、对角项与奇异级数**（原论文式 (2.6)、(2.10)–(2.11)）：
   $$\mathscr{P}_N(s, z) = \frac{2}{\varphi(N)} \sum_{\chi \in X_N^-} \frac{L'}{L}\!\left(\frac{1}{2}+s, \chi\right)\frac{L'}{L}\!\left(\frac{1}{2}+z, \bar{\chi}\right), \qquad \mathscr{D}_N(w) = \sum_{\substack{n \ge 1 \\ (n, N) = 1}} \frac{\Lambda^2(n)}{n^{1+w}},$$
   $$\mathfrak{S}(N) = 2C_2 \prod_{\substack{\ell \mid N \\ \ell > 2}} \frac{\ell - 1}{\ell - 2}, \qquad C_2 = \prod_{\ell > 2}\left(1 - \frac{1}{(\ell - 1)^2}\right), \qquad \mathscr{S}_N(w) = \sum_{k \ge 1} \frac{\mathfrak{S}(kN)}{k^w}.$$
   由 $k \mapsto \mathfrak{S}(kN)/\mathfrak{S}(N)$ 的积性（对奇素数 $\ell \mid N$ 取值 $1$；对奇素数 $\ell \nmid N$ 及 $a \ge 1$ 取值 $1 + \frac{1}{\ell-2}$），得完整无限 Euler 乘积：
   $$\mathscr{S}_N(w) = \mathfrak{S}(N)\zeta(w)P_N(w), \qquad P_N(w) = \prod_{\substack{\ell > 2 \\ \ell \nmid N}} \left(1 + \frac{\ell^{-w}}{\ell - 2}\right) \qquad (\Re w > 0).$$
   对 $N = 2p$，即 $P_{2p}(w) = \prod_{\ell > 2,\, \ell \ne p}(1 + \frac{\ell^{-w}}{\ell - 2})$。

2. **连续核 $\mathscr{K}_N(s, z)$**（原论文式 (2.9)、(2.11)–(2.12)）：
   $$K_-(s, z) = B\!\left(\frac{1}{2}-s, s+z\right) + B\!\left(\frac{1}{2}-z, s+z\right) - B\!\left(\frac{1}{2}-s, \frac{1}{2}-z\right), \qquad \mathscr{K}_N(s, z) = N^{-s-z}\mathscr{S}_N(s+z)K_-(s, z).$$
   利用 $\Gamma(u)\Gamma(1-u) = \pi/\sin(\pi u)$、$\sin A + \sin B - \sin(A+B) = 4\sin\frac{A}{2}\sin\frac{B}{2}\sin\frac{A+B}{2}$、Legendre 倍角公式及 $\zeta$ 函数方程，可精确化简为：
   $$\mathscr{K}_N(s, z) = \mathfrak{S}(N)\left(\frac{\pi}{N}\right)^{s+z} P_N(s+z)\,\zeta(1 - s - z)\,\mathcal{X}_1(s)\,\mathcal{X}_1(z), \qquad \mathcal{X}_1(s) = \frac{\Gamma\!\left(\frac{3/2 - s}{2}\right)}{\Gamma\!\left(\frac{3/2 + s}{2}\right)}.$$
   该核在 $0 < \Re s, \Re z < 3/2$ 上无条件全纯。算术余项核定义为
   $$\mathscr{E}_N(s, z) = \mathscr{P}_N(s, z) - \mathscr{D}_N(s+z) - \mathscr{K}_N(s, z),$$
   且满足共轭对称 $\mathscr{E}_N(s, \bar{z}) = \overline{\mathscr{E}_N(z, \bar{s})}$。

3. **Hardy 空间 $\mathcal{H}_N$ 与算子 $T_N$**（原论文式 (2.14)–(2.17)）：
   $$\alpha_N = \frac{1}{\log N}, \qquad \beta = \frac{1}{8}, \qquad S_N = \{s \in \mathbb{C} : \alpha_N < \Re s < \beta\}, \qquad \Gamma_N = (\alpha_N + i\mathbb{R}) \sqcup (\beta + i\mathbb{R}).$$
   内积定义为 $\langle h, g \rangle_{\mathcal{H}_N} = \int_{\Gamma_N} h(s)\overline{g(s)}\,|\mathrm{d}s|$（两条边界均取正弧长测度，无 $1/(2\pi)$ 因子）。算子定义为
   $$(T_N h)(s) = \int_{\Gamma_N} \frac{\mathscr{E}_N(s, \bar{z})}{(1+s)(1+\bar{z})} h(z)\,|\mathrm{d}z|.$$
   在 $\mathrm{GRH}(N)$ 下，$T_N$ 是 $\mathcal{H}_N$ 上的紧自伴 Hilbert–Schmidt 算子。

---

## 2. 修正 Lemma 1 的陈述

**Lemma 1.** 设 $p \to \infty$ 为奇素数，$N = 2p$，$L = \log(2p)$，假设 $\mathrm{GRH}(2p)$ 成立。对任意固定 $c > 1$，定义
$$M_{2p}(c) := \int_{\mathbb{R}} \frac{e^{-t^2}}{\sqrt{\pi}}\,\mathscr{P}_{2p}\!\left(\frac{c}{L} + it, \frac{c}{L} - it\right)\mathrm{d}t.$$
则当 $p$ 充分大时，无需任何先验均方上界，有定量估计
$$\frac{M_{2p}(c)}{L^2} = \frac{1 - e^{-2c}}{4c^2} + O_c\!\left(\frac{\|T_{2p}\|}{L} + L^{-1/4}\right).$$
特别地，若 $\|T_{2p}\| = o(L)$，则对一切 $c > 1$ 有
$$\lim_{p \to \infty} \frac{M_{2p}(c)}{L^2} = \frac{1 - e^{-2c}}{4c^2} = \int_0^\infty e^{-2cy}\min(y, 1)\,\mathrm{d}y.$$

---

## 3. 完整证明

### 步骤 1：对角项与连续核主项的一致渐近

令 $H_{2p}(w) := \mathfrak{S}(2p)P_{2p}(w)/\zeta(1+w)$。展开每个素数因子得
$$H_{2p}(w) = 2(1 - 2^{-1-w}) \cdot \frac{p - p^{-w}}{p - 1} \prod_{\substack{\ell > 2 \\ \ell \ne p}} \frac{\ell(\ell - 2)}{(\ell - 1)^2}(1 - \ell^{-1-w})\left(1 + \frac{\ell^{-w}}{\ell - 2}\right).$$
直接代入 $w = 0$ 可见每个素数因子均为 $1$，故 $H_{2p}(0) = 1$ 恒成立。在 $|w| \le 1/4$ 上，
$$\left|\frac{\mathrm{d}}{\mathrm{d}w}\log\!\left((1 - \ell^{-1-w})\left(1 + \frac{\ell^{-w}}{\ell - 2}\right)\right)\right| = \left|\ell^{-w}\log\ell \cdot \frac{2(\ell^{-w}-1)}{(\ell-\ell^{-w})(\ell-2+\ell^{-w})}\right| \ll \frac{|w|(\log\ell)^2}{\ell^{7/4}},$$
且 $|\frac{\mathrm{d}}{\mathrm{d}w}\log\frac{p - p^{-w}}{p - 1}| = |\frac{p^{-w}\log p}{p - p^{-w}}| \ll p^{-3/4}\log p$。因此 $H_{2p}(w)$ 在 $|w| \le 1/4$ 上一致解析且 $H_{2p}(2c/L) = 1 + O_c(1/L)$。

结合 $\zeta(1 + 2c/L) = \frac{L}{2c} + O(1)$、$\zeta(1 - 2c/L) = -\frac{L}{2c} + O(1)$ 以及 $(\frac{\pi}{2p})^{2c/L} = e^{-2c}(1 + O_c(1/L))$，得
$$\mathfrak{S}(2p)\left(\frac{\pi}{2p}\right)^{2c/L} P_{2p}\!\left(\frac{2c}{L}\right)\zeta\!\left(1 - \frac{2c}{L}\right) = -\frac{e^{-2c}}{4c^2}L^2 + O_c(L).$$

再估计 $\mathcal{X}_1(c/L + it_0)\mathcal{X}_1(c/L - it_0) = |\mathcal{X}_1(c/L + it_0)|^2$。由 $\overline{\Gamma(u)} = \Gamma(\bar{u})$，对 $\sigma = c/L \in (0, 1/2]$ 及任意 $t_0 \in \mathbb{R}$：
$$\log|\mathcal{X}_1(\sigma + it_0)|^2 = 2\Re\!\left[\log\Gamma\!\left(\frac{3/2 - \sigma + it_0}{2}\right) - \log\Gamma\!\left(\frac{3/2 + \sigma + it_0}{2}\right)\right].$$
对 $u \in [1/2, 1]$，有 $|\frac{\Gamma'}{\Gamma}(u + it_0/2)| \ll \log(2 + |t_0|)$ 且 $\Re\frac{\Gamma'}{\Gamma}(u + it_0/2) \ge -C$。由中值定理，对所有 $t_0 \in \mathbb{R}$ 一致有 $|\mathcal{X}_1(c/L + it_0)|^2 \ll 1$ 及
$$\left|\,|\mathcal{X}_1(c/L + it_0)|^2 - 1\,\right| \ll_c \frac{\log(2 + |t_0|)}{L}.$$
由此得对所有 $t_0 \in \mathbb{R}$ 一致成立：
$$\mathscr{K}_{2p}\!\left(\frac{c}{L} + it_0, \frac{c}{L} - it_0\right) = -\frac{e^{-2c}}{4c^2}L^2 + O_c\!\left(L\log(2 + |t_0|)\right).$$

对对角项 $\mathscr{D}_{2p}(2c/L)$，由 $(\frac{\zeta'}{\zeta})'(1 + w) = \sum_{n \ge 1}\frac{\Lambda(n)\log n}{n^{1+w}} = \frac{1}{w^2} + O(1)$（$\Re w > 0, |w| \le 1$），去掉 $k \ge 2$ 的素数幂及 $2^k, p^k$ 仅产生 $O(1)$ 误差，故
$$\mathscr{D}_{2p}\!\left(\frac{2c}{L}\right) = \frac{L^2}{4c^2} + O(1).$$
合并并在高斯权重下积分，得
$$\int_{\mathbb{R}} \frac{e^{-t_0^2}}{\sqrt{\pi}}\left(\mathscr{D}_{2p}\!\left(\frac{2c}{L}\right) + \mathscr{K}_{2p}\!\left(\frac{c}{L} + it_0, \frac{c}{L} - it_0\right)\right)\mathrm{d}t_0 = \frac{1 - e^{-2c}}{4c^2}L^2 + O_c(L). \tag{1.1}$$

### 步骤 2：Cauchy 边界局部化与双边界围道平移

记 $\varepsilon = c - 1 > 0$，定义测试向量
$$h(s) = h_{\varepsilon, t_0}(s) := \frac{\sqrt{\varepsilon\alpha_N}}{s - z_0}, \qquad z_0 := (1 - \varepsilon)\alpha_N + it_0.$$
因 $\Re z_0 < \alpha_N$，故 $h \in \mathcal{H}_{2p}$，且直接积分得
$$\|h\|_{\mathcal{H}_{2p}}^2 = \pi + \frac{\pi\varepsilon\alpha_N}{\beta - (1 - \varepsilon)\alpha_N} = \pi + O_\varepsilon\!\left(\frac{1}{L}\right) \le 2\pi \qquad (p \text{ 充分大}).$$
因此 $|\langle T_{2p}h, h\rangle_{\mathcal{H}_{2p}}| \le 2\pi\|T_{2p}\|$。

因 $T_{2p}$ 为 Hilbert–Schmidt 算子，二重积分绝对收敛，按 $\Gamma_N = L_N \sqcup R_N$（其中 $L_N = \alpha_N + i\mathbb{R}$，$R_N = \beta + i\mathbb{R}$）拆分为
$$\langle T_{2p}h, h\rangle_{\mathcal{H}_{2p}} = I_{LL} + I_{LR} + I_{RL} + I_{RR}, \qquad I_{RL} = \overline{I_{LR}}. \tag{1.2}$$

#### (a) 左边界自作用项 $I_{LL}$

在 $L_N$ 上，$\bar{z} = 2\alpha_N - z$，$\bar{s} = 2\alpha_N - s$，从而
$$\overline{h(s)} = -\frac{\sqrt{\varepsilon\alpha_N}}{s - s_1}, \qquad s_1 := c\alpha_N + it_0 = \frac{c}{L} + it_0.$$
在 $\mathrm{GRH}(2p)$ 下，对任意 $0 < \Re s < 3/2$，函数 $w \mapsto \mathscr{E}_{2p}(s, w)$ 在 $0 < \Re w < 3/2$ 全纯，故 $z \mapsto \mathscr{E}_{2p}(s, 2\alpha_N - z)$ 在 $2\alpha_N - 3/2 < \Re z < 2\alpha_N$ 全纯。将内层 $z$-围道从 $\Re z = \alpha_N$ 向左平移至 $\Re z = 2\alpha_N - \frac{3}{4}$（对应 $\Re w = \frac{3}{4}$），跨越唯一单极点 $z = z_0$（对应 $w = c/L - it_0$），留数系数为 $+2\pi\sqrt{\varepsilon\alpha_N}$。

**水平围道消失的验证**：当 $\Re s = \alpha_N$、$\Re w \in [\alpha_N, 3/4]$ 时，$\Re(1 - s - w) \in [1/4 - \alpha_N, 1 - 2\alpha_N]$，由 $\zeta$ 凸性界有 $|\zeta(1-s-w)| \ll (1 + |\Im(s+w)|)^{3/8+\delta}$，而 $|\mathcal{X}_1(w)| \ll (1 + |\Im w|)^{-\Re w} \le 1$，$\mathscr{P}_{2p}$ 与 $\mathscr{D}_{2p}$ 至多对数增长；结合分母 $|1+w|^{-1}|z-z_0|^{-1} \asymp (1+|\Im z|)^{-2}$，水平段在 $|\Im z| = T$ 处为 $O(T^{-13/8+\delta}) \to 0$。

对得到的留数项与平移积分项，再将外层 $s$-围道从 $\Re s = \alpha_N$ 向右平移至 $\Re s = \frac{3}{4}$，跨越唯一单极点 $s = s_1$（外层平移方向相反且 $\overline{h(s)}$ 带负号，两负号相消）。同样验证水平段消失：当 $\Re w = 3/4$、$\Re s \in [1/4, 3/4]$ 时，$\Re(1-s-w) = 1/4 - \Re s \in [-1/2, 0]$，由函数方程得 $|\zeta(1-s-w)| \ll (1+|\Im(s+w)|)^{1/4+\Re s+\delta}$，恰好被 $|\mathcal{X}_1(s)| \ll (1+|\Im s|)^{-\Re s}$ 抵消 $\Re s$ 次幂，乘以分母 $|1+s|^{-1}|s-s_1|^{-1} \asymp (1+|\Im s|)^{-2}$ 后仍为 $O(T^{-13/8+\delta}) \to 0$。

由此得精确恒等式：
$$I_{LL} = \frac{4\pi^2\varepsilon}{L} \frac{\mathscr{E}_{2p}(c/L + it_0, c/L - it_0)}{|1 + c/L + it_0|^2} + R_{LL,\text{res}}(t_0) + \overline{R_{LL,\text{res}}(t_0)} + R_{LL,\text{sh}}(t_0). \tag{1.3}$$
估计两类余项（记 $X(t_0) := \mathscr{P}_{2p}(c/L + it_0, c/L - it_0) \ge 0$）：
- **双平移项 $R_{LL,\text{sh}}(t_0)$**（$\Re s = \Re w = 3/4$）：因 $\frac{1}{2} + \frac{3}{4} = \frac{5}{4} > 1$ 在绝对收敛域，故 $|\mathscr{P}_{2p}|, |\mathscr{D}_{2p}| = O(1)$，而 $|\mathscr{K}_{2p}| \ll N^{-3/2}(1+|t_1+t_2|)(1+|t_1|)^{-3/4}(1+|t_2|)^{-3/4}$；乘以两因子 $\sqrt{\varepsilon/L}$ 及分母衰减得 $|R_{LL,\text{sh}}(t_0)| \ll_c L^{-1}$。
- **单留数项 $R_{LL,\text{res}}(t_0)$**（$s = s_1, \Re w = 3/4$）：对 $\mathscr{P}_{2p}(c/L + it_0, 3/4 + it_2)$ 沿 $\chi \in X_{2p}^-$ 用 Cauchy–Schwarz，并利用 $|\frac{L'}{L}(\frac{5}{4}+it_2,\bar\chi)| \le -\frac{\zeta'}{\zeta}(\frac{5}{4}) = O(1)$，得 $|\mathscr{P}_{2p}(c/L+it_0, 3/4+it_2)| \ll \sqrt{X(t_0)}$。结合 $|\mathscr{D}_{2p}|, |\mathscr{K}_{2p}| = O(1)$ 及两因子 $\sqrt{\varepsilon/L}$，得
  $$|R_{LL,\text{res}}(t_0)| \ll_c \frac{1}{L}\frac{\sqrt{X(t_0)} + 1}{|1 + it_0|^2}\log(2 + |t_0|).$$

#### (b) 右边界项 $I_{RR}$ 与交叉项 $I_{LR}$

在 $\mathrm{GRH}(2p)$ 下，对右边界 $\beta = 1/8$（即 $\frac{1}{2} + \beta = \frac{5}{8}$），由标准 GRH 界（Montgomery–Vaughan, Theorem 13.13）有
$$\left|\frac{L'}{L}\!\left(\frac{5}{8} + it, \chi\right)\right| \ll \left(\log(p(2+|t|))\right)^{2 - 2\cdot(5/8)} = \left(\log(p(2+|t|))\right)^{3/4}.$$
- **对 $I_{RR}$**：在 $R_N$ 上 $|h(\beta+it)| \asymp \frac{\sqrt{\varepsilon/L}}{1+|t-t_0|}$，$|\mathscr{P}_{2p}(\beta+it_1, \beta-it_2)| \ll L^{3/2}(\log(2+|t_1|)\log(2+|t_2|))^{3/4}$，$|\mathscr{D}_{2p}| = O(1)$，$|\mathscr{K}_{2p}| \ll N^{-1/4}(1+|t_1-t_2|)^{1/2}(1+|t_1|)^{-1/8}(1+|t_2|)^{-1/8}$。积分得
  $$|I_{RR}| \ll_c L^{1/2}\frac{(\log(2+|t_0|))^{7/2}}{(1+|t_0|)^2}.$$
- **对 $I_{LR}$**：固定 $z = \beta + it_2 \in R_N$，将 $s$-围道从 $\Re s = \alpha_N$ 向右平移至 $\Re s = 3/4$，跨越 $s = s_1$：
  - 平移后的积分（$\Re s = 3/4, \Re\bar{z} = 1/8$）满足 $|\mathscr{P}_{2p}| \ll L^{3/4}(\log(2+|t_2|))^{3/4}$，乘以 $\varepsilon/L$ 后为 $O_c(L^{-1/4})$。
  - $s = s_1$ 的留数项中，沿 $\chi \in X_{2p}^-$ 用 Cauchy–Schwarz 得 $|\mathscr{P}_{2p}(c/L+it_0, \beta-it_2)| \ll \sqrt{X(t_0)}\,L^{3/4}(\log(2+|t_2|))^{3/4}$，积分后贡献
    $$O_c\!\left(L^{-1/4}\frac{\sqrt{X(t_0)}(\log(2+|t_0|))^{7/4}}{(1+|t_0|)^2}\right).$$

### 步骤 3：高斯积分与自举闭合

将 (1.2)–(1.3) 及所有余项估计代入 $\mathscr{E}_{2p}(c/L+it_0, c/L-it_0) = X(t_0) - \mathscr{D}_{2p}(2c/L) - \mathscr{K}_{2p}(c/L+it_0, c/L-it_0)$，两边同乘 $\frac{L}{4\pi^2\varepsilon}|1 + c/L + it_0|^2 \frac{e^{-t_0^2}}{\sqrt{\pi}}$ 并对 $t_0 \in \mathbb{R}$ 积分。结合 (1.1)，并对 $\sqrt{X(t_0)}$ 项沿 $t_0$ 用 Cauchy–Schwarz（$\int_{\mathbb{R}} \frac{e^{-t_0^2}}{\sqrt{\pi}}(\log(2+|t_0|))^{7/4}\sqrt{X(t_0)}\,\mathrm{d}t_0 \ll \sqrt{M_{2p}(c)}$），得
$$\left|M_{2p}(c) - \frac{1 - e^{-2c}}{4c^2}L^2\right| \ll_c L\|T_{2p}\| + L^{3/2} + L^{3/4}\sqrt{M_{2p}(c)}.$$
记 $Y := M_{2p}(c)/L^2 \ge 0$，两边除以 $L^2$：
$$\left|Y - \frac{1 - e^{-2c}}{4c^2}\right| \ll_c \frac{\|T_{2p}\|}{L} + L^{-1/2} + L^{-1/4}\sqrt{Y}.$$
由基本不等式 $Y \le A + B\sqrt{Y} \implies Y \le 2A + B^2$，在 $\|T_{2p}\| = O(L)$ 时自动推得 $Y = O_c(1)$；代回右端即得
$$\frac{M_{2p}(c)}{L^2} = \frac{1 - e^{-2c}}{4c^2} + O_c\!\left(\frac{\|T_{2p}\|}{L} + L^{-1/4}\right). \qquad \square$$
