# E2：正确 Euler 乘积及二阶主项

**地位：** 来自所引原论文 `(2.10)–(2.12)` 的公式与可直接检查的 Euler 乘积代数。若论文采用不同归一化，须重新逐项比对原 PDF。

\[
P_N(w)=\prod_{\substack{\ell>2\ \ell\text{ prime}\\ \ell\nmid N}}\left(1+\frac{\ell^{-w}}{\ell-2}\right),
\qquad
\mathfrak S(N)=2C_2\prod_{\substack{\ell\mid N\\\ell>2}}\frac{\ell-1}{\ell-2},
\]

其中 `C₂=∏_{ℓ>2}(1−1/(ℓ−1)²)`。

设 `H_N(w)=𝔖(N)P_N(w)/ζ(1+w)`。`ζ` 的 Euler 乘积在 `Re w>0` 使用；右侧有限/无限修正积可在 `w=0` 延拓。对不整除 N 的奇素数 ℓ，

\[
\left(1+\frac{\ell^{-w}}{\ell-2}\right)(1-\ell^{-1-w})
=1+\frac{2\ell^{-w}-\ell^{-2w}}{\ell(\ell-2)}.
\]

此因子在 `w=0` 等于 `(ℓ−1)²/[ℓ(ℓ−2)]`。对整除 `N` 的奇素数，取 `𝔖` 中因子 `(ℓ−1)/(ℓ−2)` 与 `ζ^{-1}` 中 `(1−ℓ^{-1})` 之积，得到**相同**的数。素数 2 的 `ζ^{-1}` 因子为 `1/2`，抵消 `𝔖` 的开头因子 2。结合 `C₂` 的定义，得精确恒等式：

\[
H_N(0)=1.
\]

在固定 `|w|≤r<1/2` 的小邻域内，可以控制修正积的对数导数（各奇素数项的误差至多为 `O_r((log ℓ)/ℓ^{2-r})`，另有有限个除数因子；对 `N=2p` 其大素数 p 的贡献统一有界）。因此固定 `c>1`, `L=log(2p)` 时，

\[
H_{2p}(2c/L)=1+O_c(1/L),\quad
\mathfrak S(2p)P_{2p}(2c/L)
=\frac{L}{2c}+O_c(1).
\]

若连续核正如原论文定义

\[
\mathscr K_N(s,w)=\mathfrak S(N)(\pi/N)^{s+w}P_N(s+w)\zeta(1-s-w)\mathcal X_1(s)\mathcal X_1(w),
\]

则取 `s=c/L+it, w=c/L-it`（固定 t），两 ζ 极点给出

\[
\mathscr K_{2p}(s,w)\sim -\frac{e^{-2c}}{4c^2}L^2.
\]

**注意：** 从固定 t 的主项变成高斯积分下的 `O_c(L)` 加权误差需要额外控制，另见 [`conditional/lemma1-via-reproducing-kernel.md`](../conditional/lemma1-via-reproducing-kernel.md)。
