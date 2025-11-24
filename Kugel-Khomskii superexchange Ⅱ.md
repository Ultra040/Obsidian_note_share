在[[Kugel-Khomskii superexchange Ⅰ]]这篇笔记中，详细推导了K-K超交换模型，其计算过程略显繁琐，且物理图像不够清晰，为了弥补这一缺陷，这份笔记作为一个补充，从更简单的物理角度分析K-K超交换作用

---
Kugel–Khomskii 模型的核心在于将 hopping 项 $\hat{H}_{T}$ 作为微扰，计算其二阶微扰修正。由于hopping项会改变个别位点的电子占据数，因此在“每个位点恰有一个电子”的基态空间中，其一阶微扰贡献恒为0，只能考虑 $\hat{H}_{T}$ 导致的二阶微扰，也就是
$$
\hat{H}_{SE}=- \sum_{\ket{E} } \frac{\hat{H}_{T}\ket{E}\bra{E}\hat{H}^{\dagger}_{T}}{E_{E}-E_{G}} \tag{1}
$$

^25e157

对于大量位点的情形，详细的计算过程见[[Kugel-Khomskii superexchange Ⅰ]]。为了便于说明物理过程，我们这里考虑最简单的情况：只考虑两个位点 $a$ 和 $b$，并假设跃迁仅发生在相同轨道之间，则二阶微扰的形式可以写为：
$$
\hat H_T =  - t\sum_\sigma  \sum_m (c_{am\sigma}^{\dagger} {c_{bm\sigma}} + c_{bm\sigma}^{\dagger} {c_{am\sigma}}),\ \hat{H}_{T}=\hat{H}_{T}^{\dagger}
$$
对于两个位点、每个位点一个电子的简并基态空间，可分为四类典型态： A. 自旋铁磁且轨道同向，$\ket{m\sigma,m\sigma}$；B. 自旋反铁磁且轨道同向，$\ket{m\sigma,m\sigma'}$；C. 自旋反铁磁且轨道交替，$\ket{m\sigma,m'\sigma'}$；D. 自旋铁磁且轨道交替，$\ket{m\sigma,m'\sigma}$。但是无论哪种基态，由于我们限定了 $\hat H_T$ 的作用形式，因此在 $\hat H_T$ 的作用下都只会得到能级相同的激发态。比如 $\hat H_T$ 作用在 $\ket{m\sigma,m'\sigma'}$ 上，得到的激发态将是“某一位点有两个电子占据两个不同轨道且自旋相反，另一位点为空”的态，也就是 $\ket{\varnothing,mm'\sigma\sigma'}$ 或 $\ket{mm'\sigma\sigma',\varnothing}$，但这两个激发态的能量是相同的。考虑到这一性质，计算[[#^25e157|(1)]]式在四类典型态上的对角元时可以做如下变形：设考虑的态是 $\ket{G_{1}}$，$\hat{H}_{T}\ket{G_{1}}=-t\ket{E_{1}}$（这里 $\ket{E_{1}}$ 表示能量为 $E_{1}$ 的激发态，对应有两个简并态），那么
$$
\begin{align*}
\bra{G_{1}}\hat{H}_{SE} \ket{G_{1}}=& - \bra{G_{1}} \sum_{\ket{E} } \frac{\hat{H}_{T}\ket{E}\bra{E}\hat{H}^{\dagger}_{T}}{E_{E}-E_{G_{1}}}\ket{G_{1}} =-\sum_{\ket{E} } \frac{\bra{G_{1}} \hat{H}_{T}\ket{E}\bra{E}\hat{H}^{\dagger}_{T}\ket{G_{1}} }{E_{E}-E_{G_{1}}} \\
=&-t^2\sum_{\ket{E} } \frac{\braket{ E_{1} | E } \braket{ E | E_{1} }  }{E_{E}-E_{G_{1}}}=-t^2\sum_{\ket{E} } \frac{\braket{ E_{1} | E } \braket{ E | E_{1} }  }{E_{E}-E_{G_{1}}}\delta_{E,E_{1}} \\
=&-\frac{t^2}{E_{E_{1}}-E_{G_{1}}}\sum_{\ket{E} }\braket{ E_{1} | E } \braket{ E | E_{1} } \\
=&-\frac{1}{\Delta E}\sum_{\ket{E} }\bra{G_{1}} \hat{H}_{T}\ket{E}\bra{E}\hat{H}^{\dagger}_{T}\ket{G_{1}}  \\
=&-\frac{1}{\Delta E}\bra{G_{1}} \hat{H}_{T}\left( \sum_{\ket{E} }\ket{E}\bra{E} \right) \hat{H}^{\dagger}_{T}\ket{G_{1}}\tag{2}
\end{align*}
$$

^6f50c2

利用完备性关系：
$$
\sum_{\ket{E} }\ket{E}\bra{E}+\sum_{\ket{G} }\ket{G}\bra{G}=1
$$
[[#^6f50c2|(2)]]式可以进一步写为：
$$
\bra{G_{1}}\hat{H}_{SE} \ket{G_{1}}=-\frac{1}{\Delta E}\bra{G_{1}} \hat{H}_{T}\left(1- \sum_{\ket{G} }\ket{G}\bra{G} \right) \hat{H}^{\dagger}_{T}\ket{G_{1}}\tag{3}
$$

^15474e

由于$\hat H_T$ 的一阶微扰贡献为0，也就是 $\bra{G}\hat{H}_{T}\ket{G_{1}}=0$，因此[[#^15474e|(3)]]式可以化简为
$$
\bra{G_{1}}\hat{H}_{SE} \ket{G_{1}}=-\frac{1}{\Delta E}\bra{G_{1}} \hat{H}_{T}\hat{H}^{\dagger}_{T}\ket{G_{1}}\tag{4}
$$

^bd98f0

[[#^bd98f0|(4)]]式的物理意义相对而言就清晰了很多：处于基态 $\ket{G_{1}}$ 的电子在 $\hat{H}_{T}$ 的作用下跃迁至能量为 $E_{1}$ 的激发态，然后在 $\hat{H}_{T}^{\dagger}$ 的作用下发生进一步跃迁。**若要获得能量增益，则 $\bra{G_{1}} \hat{H}_{T}\hat{H}^{\dagger}_{T}\ket{G_{1}}\ne0$，也就是第二次跃迁要正好返回基态，那么中间跃迁至能量为 $E_{1}$ 的激发态就可以看作是一个虚拟的跃迁过程，也就是所谓的虚跃迁。** 这里分母上的 $\Delta E$ 表示虚跃迁的激发态和初始基态的能量差。

---
根据[[#^bd98f0|(4)]]式可以计算之前提到的在四类典型态上的对角元：

A. $\ket{m\sigma,m\sigma}=\ket{A}$
这个态实际上无法在 $\hat{H}_{T}$ 作用下跃迁至中间态，因为跃迁后轨道、自旋均不变，那么必然出现某一位点具有两个电子处于相同轨道相同自旋的情况，这是违背泡利不相容原理的，因此
$$
\bra{m\sigma,m\sigma} \hat{H}_{SE}\ket{m\sigma,m\sigma}=0
$$
B. $\ket{m\sigma,m\sigma'}=\ket{B}$
这个态在 $\hat{H}_{T}$ 作用下会跃迁至“某一位点两个自旋相反的电子占据同一轨道，另一位点为空”的激发态，这一激发态能量相比于基态多了同一位点同一轨道上的库仑排斥能，即 $\Delta E=U$。此外需要注意，激发态具有两重简并，$\ket{\varnothing,mm\sigma\sigma'}$ 或 $\ket{mm\sigma\sigma',\varnothing}$，因此[[#^bd98f0|(4)]]式计算为
$$
\bra{m\sigma,m\sigma'} \hat{H}_{SE}\ket{m\sigma,m\sigma'}=-\frac{2t^2}{U}
$$
C. $\ket{m\sigma,m'\sigma'}=\ket{C}$
这个态在 $\hat{H}_{T}$ 作用下会跃迁至“某一位点两个自旋相反的电子占据不同轨道，另一位点为空”的激发态。由于两个电子不再挤在同一轨道上，因此相比与情形B的激发态能量有所降低，$\Delta E=U-2J$，这里 $J$ 代表洪特耦合能，那么
$$
\bra{m\sigma,m'\sigma'} \hat{H}_{SE}\ket{m\sigma,m'\sigma'}=-\frac{2t^2}{U-2J}
$$
D. $\ket{m\sigma,m'\sigma}=\ket{D}$
这个态在 $\hat{H}_{T}$ 作用下会跃迁至“某一位点两个自旋相同的电子占据不同轨道，另一位点为空”的激发态。这个态完全满足洪特规则描述的能量最小化要求，因此 $\Delta E=U-3J$ 
$$
\bra{m\sigma,m'\sigma'} \hat{H}_{SE}\ket{m\sigma,m'\sigma'}=-\frac{2t^2}{U-3J}
$$
综合上述对这四类典型态的讨论可以看到，第四类基态 $\ket{m\sigma,m'\sigma}$ 获得的二阶微扰能量降低最多，因此体系倾向于形成“相邻自旋呈铁磁排列，而轨道呈交替分布”的轨道有序状态。

---
但是上述计算只局限于计算四类典型态上的对角元，由于是简并微扰，真正严格的计算需要在这四类典型态的16个基态（每类态有四个简并态）组成的空间上将 $\hat{H}_{SE}$ 进行对角化。为了计算这个16×16的矩阵，我们需要对 $\hat{H}_{T}$  做进一步分析。

由于假设 $\hat{H}_{T}$ 对应的跃迁仅发生在相同轨道之间且不改变自旋，那么对于属于不同类的两个态，例如 $\ket{m\sigma,m\sigma}$ 和 $\ket{m\sigma,m\sigma'}$，其作用在 $\ket{m\sigma,m\sigma}$ 后对应激发态的两个电子自旋仍相同，而作用在$\ket{m\sigma,m\sigma'}$ 得到的激发态电子仍自旋相反，因此不可能存在某个本征激发态 $\ket{E}$ 能同时等于 $\hat{H}_{T}\ket{m\sigma,m\sigma}$ 和 $\hat{H}_{T}\ket{m\sigma,m\sigma'}$，因此必有
$$
\bra{m\sigma,m\sigma}\hat{H}_{T}\ket{E}\bra{E}\hat{H}^{\dagger}_{T}  \ket{m\sigma,m\sigma'}=0  
$$
由此，$\hat{H}_{SE}$ 在属于不同类的两个态上的矩阵元也必为0，也就是16×16的矩阵实际只需考虑四块4×4的小矩阵，每块矩阵对应的是一类态。除此以外，我们还能发现，对于同一类态，$\hat{H}_{T}$ 作用到这类态上得到的激发态能量总是相同的，因此类似于[[#^6f50c2|(2)]]式的推导仍然成立：
$$
\bra{G_{1}} \hat{H}_{SE}\ket{G_{2}} =-\frac{1}{\Delta E}\bra{G_{1}} \hat{H}_{T}\hat{H}^{\dagger}_{T}\ket{G_{2}}
$$
这里 $\ket{G_{1}}$ 和 $\ket{G_{2}}$ 属于四类态中的同一类。也就是说，要想 $\bra{G_{1}} \hat{H}_{SE}\ket{G_{2}}$ 不为0，那么 $\ket{G}_{1}$ 和 $\ket{G_{2}}$ 要能通过两次跃迁联系起来。据此我们可以分别计算A，B，C，D每类上的矩阵，进行分块对角化。

A. $\ket{G_{1}},\ket{G_{2}}\in \{\ket{m\sigma,m\sigma}\}$
由于泡利不相容原理，
$$
\bra{G_{1}} \hat{H}_{SE}\ket{G_{2}}=0
$$
B. $\ket{G_{1}},\ket{G_{2}}\in \{\ket{m\sigma,m\sigma'}\}$
这一类共四个简并态：$\ket{1}=\ket{\searrow\uparrow,\searrow\downarrow},\,\ket{2}=\ket{\searrow\downarrow,\searrow\uparrow},\,\ket{3}=\ket{\nearrow\uparrow,\nearrow\downarrow},\,\ket{4}=\ket{\nearrow\downarrow,\nearrow\uparrow}$
同样由于 $\hat{H}_{T}$ 保自旋保轨道的性质，能够在两次 $\hat{H}_{T}$ 作用下联系的态只有 $(\ket{1},\ket{2})$，$(\ket{3},\ket{4})$ 两对。对于 $(\ket{1},\ket{2})$，设 $\ket{G_{1}}=\ket{1}$，$\ket{G_{2}}=\ket{2}$，$\bra{G_{1}} \hat{H}_{T}\hat{H}^{\dagger}_{T}\ket{G_{2}}$ 存在两种跃迁途径：
![[Pasted image 20251123110125.png|400]]
对于每一种跃迁，激发态能量与基态能量差均为 $\Delta E=U$，因此
$$
\bra{G_{1}} \hat{H}_{SE}\ket{G_{2}}=\bra{1}\hat{H}_{SE}\ket{2}=\bra{2}\hat{H}_{SE}\ket{1}=-2\times\frac{t^{2}}{U}=-\frac{2t^2}{U}   
$$
上式中的2表示两种途径。同理我们有
$$
\bra{G_{1}} \hat{H}_{SE}\ket{G_{2}}=\bra{3}\hat{H}_{SE}\ket{4}=\bra{4}\hat{H}_{SE}\ket{3}=-\frac{2t^2}{U}
$$
因此在B这一类下，$\hat{H}_{SE}$ 对应的矩阵元为：
$$
\begin{array}{c|c|c|c|}\ &\ket{1} &\ket{2}&\ket{3}&\ket{4} \\ \hline \ket{1} &-\dfrac{2t^2}{U}&-\dfrac{2t^2}{U}&0&0 \\
\hline\ket{2} &-\dfrac{2t^2}{U}&-\dfrac{2t^2}{U}&0&0 \\
\hline\ket{3} &0&0&-\dfrac{2t^2}{U}&-\dfrac{2t^2}{U} \\
\hline\ket{4} &0&0&-\dfrac{2t^2}{U}&-\dfrac{2t^2}{U}\end{array}
$$
对这一4×4方阵对角化，得到能级和相应的本征态为：
$$
\begin{align*}
E_{B_{1}}=-\frac{4t^2}{U}&:\ \,\ket{\psi_{B_{1}}}=\frac{1}{\sqrt{ 2 }}(\ket{1}+\ket{2}  ) ,\ \ket{\psi_{B_{2}}}=\frac{1}{\sqrt{ 2 }}(\ket{3}+\ket{4}  ) \\
E_{B_{2}}=0&:\ \,\ket{\psi_{B_{3}}}=\frac{1}{\sqrt{ 2 }}(\ket{1}-\ket{2}  ) ,\ \ket{\psi_{B_{2}}}=\frac{1}{\sqrt{ 2 }}(\ket{3}-\ket{4}  )
\end{align*}
$$
C. $\ket{G_{1}},\ket{G_{2}}\in \{\ket{m\sigma,m'\sigma}\}$
这一类有四个简并态：$\ket{1}=\ket{\searrow\uparrow,\nearrow\uparrow},\,\ket{2}=\ket{\searrow\downarrow,\nearrow\downarrow},\,\ket{3}=\ket{\nearrow\uparrow,\searrow\uparrow},\,\ket{4}=\ket{\nearrow\downarrow,\searrow\downarrow}$
同样由于 $\hat{H}_{T}$ 保自旋保轨道的性质，能够在两次 $\hat{H}_{T}$ 作用下联系的态只有 $(\ket{1},\ket{3})$，$(\ket{2},\ket{4})$ 两对。对于每一种跃迁，激发态能量与基态能量差均为 $\Delta E=U-2J$。使用和B类相同的分析，可得 $\hat{H}_{SE}$ 对应的矩阵元为：
$$
\begin{array}{c|c|c|c|}\ &\ket{1} &\ket{2}&\ket{3}&\ket{4} \\ \hline \ket{1} &-\dfrac{2t^2}{U-2J}&0&-\dfrac{2t^2}{U-2J}&0 \\
\hline\ket{2} &0&-\dfrac{2t^2}{U-2J}&0&-\dfrac{2t^2}{U-2J} \\
\hline\ket{3} &-\dfrac{2t^2}{U-2J}&0&-\dfrac{2t^2}{U-2J}&0 \\
\hline\ket{4} &0&-\dfrac{2t^2}{U-2J}&0&-\dfrac{2t^2}{U-2J}\end{array}
$$
对这一4×4方阵对角化，得到能级和相应的本征态为：
$$
\begin{align*}
E_{C_{1}}=-\frac{4t^2}{U-2J}&:\ \,\ket{\psi_{C_{1}}}=\frac{1}{2}(\ket{1}+\ket{2} +\ket{3}+\ket{4} ) ,\ \ket{\psi_{C_{2}}}=\frac{1}{2}(\ket{1}-\ket{2} +\ket{3}-\ket{4}  ) \\
E_{C_{2}}=0&:\ \,\ket{\psi_{C_{3}}}=\frac{1}{\sqrt{ 2 }}(\ket{1}-\ket{3}  ) ,\ \ket{\psi_{C_{2}}}=\frac{1}{\sqrt{ 2 }}(\ket{2}-\ket{4}  )
\end{align*}
$$
D. $\ket{G_{1}},\ket{G_{2}}\in \{\ket{m\sigma,m'\sigma'}\}$
这一类也有四个简并态：$\ket{1}=\ket{\searrow\uparrow,\nearrow\downarrow},\,\ket{2}=\ket{\searrow\downarrow,\nearrow\uparrow},\,\ket{3}=\ket{\nearrow\uparrow,\searrow\downarrow},\,\ket{4}=\ket{\nearrow\downarrow,\searrow\uparrow}$
同样由于 $\hat{H}_{T}$ 保自旋保轨道的性质，能够在两次 $\hat{H}_{T}$ 作用下联系的态只有 $(\ket{2},\ket{3})$，$(\ket{1},\ket{4})$ 两对。对于每一种跃迁，激发态能量与基态能量差均为 $\Delta E=U-3J$。同样可得 $\hat{H}_{SE}$ 对应的矩阵元为：
$$
\begin{array}{c|c|c|c|}\ &\ket{1} &\ket{2}&\ket{3}&\ket{4} \\
\hline \ket{1} &-\dfrac{2t^2}{U-3J}&0&0&-\dfrac{2t^2}{U-3J} \\
\hline\ket{2} &0&-\dfrac{2t^2}{U-3J}&-\dfrac{2t^2}{U-3J}&0 \\
\hline\ket{3} &0&-\dfrac{2t^2}{U-3J}&-\dfrac{2t^2}{U-3J}&0 \\
\hline\ket{4} &-\dfrac{2t^2}{U-3J}&0&0&-\dfrac{2t^2}{U-3J}\end{array}
$$
对这一4×4方阵对角化，得到能级和相应的本征态为：
$$
\begin{align*}
E_{D_{1}}=-\frac{4t^2}{U-3J}&:\ \,\ket{\psi_{D_{1}}}=\frac{1}{\sqrt{ 2 }}(\ket{1}+\ket{4}  ) ,\ \ket{\psi_{D_{2}}}=\frac{1}{\sqrt{ 2 }}(\ket{2}+\ket{3}  ) \\
E_{D_{2}}=0&:\ \,\ket{\psi_{D_{3}}}=\frac{1}{\sqrt{ 2 }}(\ket{1}-\ket{4}  ) ,\ \ket{\psi_{D_{2}}}=\frac{1}{\sqrt{ 2 }}(\ket{2}-\ket{3}  )
\end{align*}
$$
综合上述讨论，在超交换作用下最小的能量为 $E_{D_{1}}=-\dfrac{4t^2}{U-3J}$，此时系统对应的本征态为
$$
\ket{\psi_{D_{1}}}=\frac{1}{\sqrt{ 2 }} (\ket{\searrow\uparrow,\nearrow\downarrow}+\ket{\nearrow\downarrow,\searrow\uparrow})
$$
或
$$
\ket{\psi_{D_{1}}}=\frac{1}{\sqrt{ 2 }} (\ket{\searrow\downarrow,\nearrow\uparrow}+\ket{\nearrow\uparrow,\searrow\downarrow})
$$
