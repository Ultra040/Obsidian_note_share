对于钙钛矿结构的晶体，晶格中心的过渡金属阳离子通常处于由周围阴离子构成的八面体配位环境中。该局域环境使离子的对称性由孤立离子的 $O(3)$ 降低至 $O_h$，从而导致具有相同角量子数的简并 $d$ 轨道（主要是五个 $d$ 轨道）发生能级劈裂，形成所谓的 **晶体场效应**。

以 $\ce{LaMnO3}$ 为例，中心的 $\ce{Mn^{3+}}$ 离子具有 $3d^4$ 的电子构型。在晶体场的作用下，五个简并的 $d$ 轨道劈裂为两个能级：三重简并的 $t_{2g}$ 轨道和二重简并的 $e_g$ 轨道。根据洪特规则，$\ce{Mn^{3+}}$ 的四个电子将以相同的自旋尽可能分布在不同轨道上，而不会在同一轨道中成对出现，因此其电子构型为 $t_{2g}^3 e_g^1$。

此时，$e_g$ 能级中仍有一个空轨道，因此处于 $e_g^1$ 状态的电子除了自旋自由度之外，还具有 **轨道自由度** ——它可以选择占据 $e_g$ 的任意一个简并轨道。直观上，两个 $e_g$ 轨道能量相同，但若考虑晶格离子的影响，局域势场可能因晶格畸变而改变，从而使两个轨道退简并，能量一高一低，这正是著名的 **Jahn–Teller 效应**。

若这种晶格畸变以周期性方式出现，则 $e_g$ 轨道能级的高低分布也将呈周期性。由于电子总是倾向于占据能量较低的轨道，体系中电子的轨道分布将呈现出 **有序排列**，即所谓的 **轨道有序（orbital order）**。

然而，轨道有序的产生并非一定依赖于 Jahn–Teller 畸变。1973 年，Kugel 和 Khomskii 提出了另一种由电子间多体超交换相互作用（superexchange interaction）驱动的轨道有序机制，即著名的 **Kugel–Khomskii 模型**。本文档将以 $\ce{LaMnO3}$ 体系为例，详细推导该模型所导致的轨道有序效应。

---
考虑多体Hubbard模型，其哈密顿量可以表示为：$\hat{H}=\hat{H}_{0}+\hat{H}_{T}+\hat{H}_{U}$，其中
$$
\hat{H}_{0}=\varepsilon_{e_{g}}\sum_{i}\sum_{\sigma}\sum_{m}\hat{n}_{im\sigma}\tag{1}
$$
这是无相互作用下的能量项。
$$
\hat{H}_{T}=-\sum_{i\ne i'}\sum_{\sigma}\sum_{mm'}t_{m,m'}^{i,i'}c^{\dagger}_{im\sigma}c_{i'm'\sigma}\tag{2}
$$

^6c4623

这一求和的每一项表示在 $i'$ 点位上湮灭一个处于 $\ket{m'\sigma}$ 态的电子，同时在 $i$ 处生成一个处于 $\ket{m\sigma}$ 态的电子。在考虑不同点位（$i\ne i'$）的跃迁时，$t_{m,m'}^{i,i'}$ 表示 hopping 项。**（为什么不考虑相同点位的电子跃迁？）** 需要说明的是，一些教材或文献里对这一项的写法略有不同，另一种写法为：
$$
\hat{H}_{T}=-\sum_{\langle i,i'\rangle}\sum_{\sigma}\sum_{mm'}t_{m,m'}^{i,i'}c^{\dagger}_{im\sigma}c_{i'm'\sigma}+t_{m,m'}^{i',i}c^{\dagger}_{i'm\sigma}c_{im'\sigma}\tag{2-a}
$$

^4ffd2e

根本原因在于[[#^6c4623|(2)]]和[[#^4ffd2e|(2-a)]]式第一项求和的指标不同。[[#^6c4623|(2)]]的第一项求和指标是所有的 $i$ 和 $i'(i\ne i')$，而[[#^4ffd2e|(2-a)]]的第一项求和指标是不同 $i,i'$ 构成的位点对 $\langle i,i'\rangle$，求和项数后者是前者的一半。
接下来是 $\hat{H}_{U}$：
$$
\hat{H}_{U}=\frac{1}{2}\sum_{i}\sum_{\sigma\sigma^{\prime}}\sum_{m_{\alpha}m^{ \prime}_{\alpha}}\sum_{m_{\beta}m^{\prime}_{\beta}}U_{m_{\alpha}m_{\beta}m^{ \prime}_{\alpha}m^{\prime}_{\beta}} c^{\dagger}_{im_{\alpha}\sigma}c^{\dagger }_{im_{\beta}\sigma^{\prime}}c_{im^{\prime}_{\beta}\sigma^{\prime}}c_{im^{ \prime}_{\alpha}\sigma}\tag{3}
$$

^f911ac

这是库伦排斥项。这一项可以通过Slater积分进行计算（只考虑 $t_{2g}$ 和 $e_{g}$ 轨道），在Hubbard模型中，[[#^f911ac|(3)]]式可进一步写为：
$$
\begin{split}\hat{H}_{U}=& U\sum_{i}\sum_{m}\hat{n} _{im\uparrow}\hat{n}_{im\downarrow}+\frac{1}{2} \sum_{i}\sum_{\sigma\sigma^{ \prime}}\sum_{m\neq m^{\prime}}(U-2J-J\delta_{\sigma,\sigma^{\prime}}) \hat{n }_{im\sigma}\hat{n}_{im^{\prime}\sigma^{\prime}}\\ &- J\sum_{i}\sum_{m\neq m^{\prime}} \left[c^{\dagger}_{im \uparrow}c^{\dagger}_{im\downarrow}c_{im^{\prime}\uparrow}c_{im^{\prime} \downarrow}+c^{\dagger}_{im\uparrow}c_{im\downarrow}c^{\dagger}_{im^{\prime} \downarrow}c_{im^{\prime}\uparrow}\right],\end{split}\tag{3-a}
$$

^332edd

展开后的第一项是同一位点上的库仑排斥，第二项代表的是交换相互作用和洪特规则，第三项表示自旋翻转和对跃迁（pair hopping）。在这里若不考虑洪特规则耦合项（$J=0$），那么总哈密顿量可以写作：
$$
\begin{align*}
\hat{H}=\hat{H}_{0}+\hat{H}_{T}+\hat{H}_{U}&=\varepsilon_{e_{g}}\sum_{i}\sum_{\sigma}\sum_{m}\hat{n}_{im\sigma}-\sum_{i\ne i'}\sum_{\sigma}\sum_{mm'}t_{m,m'}^{i,i'}c^{\dagger}_{im\sigma}c_{i'm'\sigma}\\
&+U\sum_{i}\sum_{m}\hat{n} _{im\uparrow}\hat{n}_{im\downarrow}+\frac{U}{2} \sum_{i}\sum_{\sigma\sigma^{ \prime}}\sum_{m\neq m^{\prime}}\hat{n }_{im\sigma}\hat{n}_{im^{\prime}\sigma^{\prime}}\tag{4}
\end{align*}
$$
如果忽略 $\hat{H}_{T}$ 的作用，而只考虑 $\hat{H}_{0}+\hat{H}_{U}$，能量只与单个位点上的电子有关。设在位点 $i$ 上占据的电子数为 $N_{e}$，这样的占据态记作 $\ket{N_{e}}^i$。由于每个位点只提供了两个轨道（$e_{g}$ 的两个轨道），因此 $N_{e}=0\sim 4$。当 $N_{e}=0$ 时，表明位点 $i$ 上没有电子，显然此时该位点对应的能量 $E(N_{e}=0)=0$，对应的占据态 $\ket{0}^i$ 的简并度为1；当 $N_{e}=1$ 时，位点 $i$ 上有一个电子，只需要考虑 $\hat{H}_{0}$，对应的能量为 $E(1)=\varepsilon_{e_{g}}$，简并度为4（两个轨道、两种自旋）；当 $N_{e}=2$ 时，位点 $i$ 上有两个电子，需要考虑 $\hat{H}_{0}$ 和 $\hat{H}_{U}$，能量为 $E(2)=2\varepsilon_{e_{g}}+U$，其中有**两个电子占据同一轨道但自旋相反**和**两个电子占据不同轨道**两种情况，一共6个简并态；当 $N_{e}=3$ 时，表明 $i$ 位点由一个能级填满了自旋相反的两个电子，另一个能级只填了一个电子，这种情况能量为 $E(3)=3\varepsilon_{e_{g}}+3U$，简并度为4；当 $N_{e}=4$ 时，$i$ 位点的四个态全部被填满，$E(4)=4\varepsilon_{e_{g}}+6U$，简并度为1。上述讨论可总结为下表：
$$
\begin{array}{llll}|N_{e}\rangle_{\alpha}&E_{\alpha}(N_{e})&d(N_{e })\\ \hline\\ |0\rangle&E(0)=0&d(0)=1\\ |1\rangle=c^{\dagger}_{m\sigma}|0\rangle&E(1)=\varepsilon_{e_{g}}&d(0)=4\\ |2\rangle=c^{\dagger}_{m\sigma}c^{\dagger}_{m^{\prime}\sigma^{\prime}}|0 \rangle&E(2)=2\varepsilon_{e_{g}}+U&d(0)=6\\ |3\rangle=c^{\dagger}_{m\sigma}c^{\dagger}_{m^{\prime}\uparrow}c^{\dagger}_{ m^{\prime}\downarrow}|0\rangle&E(3)=3\varepsilon_{e_{g}}+3U&d(0)=4\\ |4\rangle=c^{\dagger}_{m\uparrow}c^{\dagger}_{m\downarrow}c^{\dagger}_{m^{ \prime}\uparrow}c^{\dagger}_{m^{\prime}\downarrow}|0\rangle&E(4)=4\varepsilon _{e_{g}}+6U&d(0)=1\end{array}
$$
表中 $\ket{N_{e}}_{\alpha}$ 的下标 $\alpha$ 表示简并态。考虑两个相邻位点 $i$ 和 $i'$，它们的占据态分别为 $\ket{N_{e}}_{\alpha}^i$ 和 $\ket{N_{e}'}_{\alpha'}^{i'}$， 这两个态的组合就是 $\ket{N_{e}}_{\alpha}^i\ket{N_{e}'}_{\alpha'}^{i'}$ 。对于具有 $n$ 个位点的体系，每个位点**平均**有一个电子，因此不难得出基态为每个位点一个电子，记作 $\ket{G}=\cdots \ket{1}_{\alpha}^i\otimes\ket{1}_{\alpha'}^{i'}\cdots\in\{\ket{1}_{\alpha}^i\ket{1}_{\alpha'}^{i'}\}$。这一记号表明任意两个相邻位点形成的占据态组合都是 $\ket{1}_{\alpha}^i\ket{1}_{\alpha'}^{i'}$，符合基态特征。显然基态的简并度为 $4^n$，因为每个位点具有4个简并度，而位点个数为 $n$。对于激发态，也就是存在相邻的格点满足一个位点上的电子跃迁到另一个位点上，形成 $\ket{2}_{\alpha}^i\ket{0}^{i'}$ 或 $\ket{0}^i\ket{2}_{\alpha'}^{i'}$，**每一对这样的格点，总能量就会提升 $\Delta E=E(2)+E(0)-2E(1)=U$**。激发态可以表示为 $\ket{E}\in\{\ket{2}_{\alpha}^i\ket{0}^{i'}\}\cup\{\ket{0}^i\ket{2}_{\alpha'}^{i'}\}$，也就是有若干对位点从 $\ket{1}_{\alpha}^i\ket{1}_{\alpha'}^{i'}$ 变为 $\ket{2}_{\alpha}^i\ket{0}^{i'}$ 或 $\ket{0}^i\ket{2}_{\alpha'}^{i'}$。
接下来再把 $\hat{H}_{T}$ 考虑进去，在只考虑相邻格点跃迁的基础上，跃迁项动能 $t_{m,m'}^{i,i'}$ 的形式相对简单：
$$
t_{mm^{\prime}}^{i,i\pm\hat{z}}=t\begin{pmatrix} 
0&0 \\
0&1
\end{pmatrix}\ \ \ \ t_{mm^{\prime}}^{i,i\pm\hat{x}}=t\begin{pmatrix} 
\frac{3}{4}&\frac{\sqrt{3}}{4} \\
\frac{\sqrt{3}}{4}&\frac{1}{4}
\end{pmatrix}\ \ \ \ t_{mm^{\prime}}^{i,i\pm\hat{y}}=t\begin{pmatrix} 
\frac{3}{4}&-\frac{\sqrt{3}}{4} \\
-\frac{\sqrt{3}}{4}&\frac{1}{4}
\end{pmatrix}\tag{5}
$$

^e89702

这里的矩阵是在 $e_{g}$ 的两个简并轨道 $\ket{\nearrow}=\ket{x^2-y^2},\ket{\searrow}=\ket{3z^2-r^2}$ 下定义的。
当 $t\ll U$ 时，可以将 $\hat{H}_{T}$ 看作是微扰。为了求解基态能量在此微扰下的能级变化，需要使用定态简并微扰。这里我们回顾跃迁项算符 $\hat{H}_{T}$ 的作用性质——在 $i'$ 点位上湮灭一个处于 $\ket{m'\sigma}$ 态的电子，同时在 $i$ 处生成一个处于 $\ket{m\sigma}$ 态的电子，那么根据这一性质可以不难得到，$\hat{H}_{T}$ 对基态作用后得到的态必定不是基态，也就是$\hat{H}_{T}\ket{G}\notin V_{G}$，这里 $V_{G}$ 表示基态简并子空间。由此，若考虑一阶微扰，原则上需要将 $\hat{H}_{T}$ 在 $V_{G}$ 上对角化，但根据上述性质，$\hat{H}_{T}$ 在 $V_{G}$ 上的矩阵元将为0，因此**一阶微扰无法去除基态空间的简并性**。进一步的，我们可以考虑 $\hat{H}_{T}$ 在 $V_{G}$ 上的二阶微扰（具体推导参考笔记[[量子力学定态微扰讨论]]里的内容），也就是将算符
$$
\hat{H}_{SE}=- \sum_{\ket{E} } \frac{\hat{H}_{T}\ket{E}\bra{E}\hat{H}^{\dagger}_{T}}{E_{E}-E_{G}}\tag{6}
$$

^cb4960

在基态空间 $V_{G}$ 中对角化。$\hat{H}_{SE}$ 这个算符的下标 “SE” 表示 **superexchange（超交换）**，即由电子的虚跃迁（virtual hopping）在二阶微扰近似下产生的有效相互作用算符。它反映了高能激发态（双占态等）被“积掉“（求和）后，在低能子空间中留下的有效自旋—轨道交换作用。[[#^cb4960|(6)]]式中的 $\ket{E}$ 即表示激发态，$E_{E}$ 对应激发态的能量。为了进一步计算[[#^cb4960|(6)]]式，我们现在只考虑沿 $z$ 方向分布的格点，代入[[#^e89702|(5)]]式的第一个矩阵，可以将[[#^6c4623|(2)]]式写为：
$$
\hat{H}_{T}^z=\sum_{i\ne i'}\hat{H}_{T}^{z(i,i')},\ \ \ \hat{H}_{T}^{z(i,i')}=-t\sum_{\sigma}c^{\dagger}_{i\tau\sigma}c_{i'\tau\sigma}\delta_{\tau,\searrow}\tag{7}
$$

^408759

将[[#^408759|(7)]]代入[[#^cb4960|(6)]]，得到
$$
\hat{H}_{SE}^z=-\sum_{\ket{E} } \frac{\hat{H}_{T}^{z}\ket{E}\bra{E}  \hat{H}_{T}^{\dagger z}}{E_{E}-E_{G}}=-\sum_{ii'}\sum_{jj'}\sum_{\ket{E}} \frac{\hat{H}_{T}^{z(i,i')}\ket{E}\bra{E}\hat{H}_{T}^{\dagger z(j,j')}  }{E_{E}-E_{G}} \tag{8}
$$

^3dd697

在此我们先停一会，分析一下推导出的[[#^3dd697|(8)]]式的性质。[[#^3dd697|(8)]]式有三层求和，求和数量非常庞大，每一求和项都具有
$$
\frac{\hat{H}_{T}^{z(i,i')}\ket{E}\bra{E}\hat{H}_{T}^{\dagger z(j,j')}  }{E_{E}-E_{G}} 
$$
的形式。但是我们最终是要将 $\hat{H}_{SE}^z$ 在 $V_{G}$ 上对角化，因此尽管求和项很多，但不是所有的项都在 $V_{G}$ 上有贡献。例如我们考察
$$
\bra{G_{1}}\hat{H}_{T}^{z(i,i')}\ket{E}\bra{E}\hat{H}_{T}^{\dagger z(j,j')}\ket{G_{2}} \tag{9}
$$

^2c3c2e

要求这一项不为0，那么 $\bra{G_{1}}\hat{H}_{T}^{z(i,i')}\ket{E}\ne0$，因此 $\hat{H}_{T}^{z(i,i')}\ket{E} \in V_{G}$，这就对 $\ket{E}$ 做出了限制：由于 $\hat{H}_{T}^{z(i,i')}$ 限制了跃迁只能发生在位点 $i$ 和 $i'$ 上，因此激发态 $\ket{E}$ 只能有一对位点处于 $\ket{2}_{\alpha}^i\ket{0}^{i'}$ 或 $\ket{0}^i\ket{2}_{\alpha'}^{i'}$ 的状态，其余位点都是单电子占据，不能有两对及以上的位点处于 $\ket{2}_{\alpha}^i\ket{0}^{i'}$ 或 $\ket{0}^i\ket{2}_{\alpha'}^{i'}$，否则必然有 $\hat{H}_{T}^{z(i,i')}\ket{E} \notin V_{G}$。**这样一来就限定了激发态的形式，$\ket{E}^{k,k'}=\ket{0}^k \ket{2}^{k'}_{\alpha'}\otimes \ket{1}\ket{1}\cdots \ket{1}$，同时激发态的能量也确定，$E_{E}-E_{G}=\Delta E=U$**。因此[[#^3dd697|(8)]]式可进一步化简为
$$
\hat{H}_{SE}^z=-\frac{1}{U}\sum_{ii'}\sum_{jj'}\sum_{\ket{E}} \hat{H}_{T}^{z(i,i')}\ket{E}\bra{E}\hat{H}_{T}^{\dagger z(j,j')}=-\frac{1}{U}\sum_{ii'}\sum_{jj'}\hat{H}_{T}^{z(i,i')}\left( \sum_{\ket{E} }\ket{E}\bra{E} \right) \hat{H}_{T}^{\dagger z(j,j')}\tag{10}
$$

^c8838e

注意到[[#^c8838e|(10)]]式括号里的部分存在另一种写法：
$$
\sum_{\ket{E} }\ket{E}\bra{E}=\sum_{kk'}\sum_{\alpha'}(\ket{0}^k \ket{2}^{k'}_{\alpha'}\otimes \ket{1}\ket{1}\cdots \ket{1}) ( \bra{1}  \cdots \bra{1}\bra{1}\otimes\bra{2}_{\alpha'}^{k'}\bra{0}^k    )  \tag{11}
$$
代入[[#^c8838e|(10)]]式，得到
$$
\hat{H}_{SE}^z=-\frac{1}{U}\sum_{ii'}\sum_{jj'}\sum_{kk'}\sum_{\alpha'}\hat{H}_{T}^{z(i,i')}(\ket{0}^k \ket{2}^{k'}_{\alpha'}\otimes \ket{1}\ket{1}\cdots \ket{1}) ( \bra{1}  \cdots \bra{1}\bra{1}\otimes\bra{2}_{\alpha'}^{k'}\bra{0}^k    ) \hat{H}_{T}^{\dagger z(j,j')}\tag{12}
$$

^2a457d

要使[[#^2a457d|(12)]]的求和项不为0，那么必然要求 $\hat{H}_{T}^{z(i,i')}$ 作用的位点对 $(i,i')$ 就是 $(k,k')$，同理 $\hat{H}_{T}^{\dagger z(j,j')}$ 作用的位点对 $(j,j')$ 也得是 $(k,k')$，否则都会出现内积为0的情形。因此我们有 $i=j=k,i'=j'=k'$（注意这里所有带 $'$ 的和带 $'$ 的作用，不带 $'$ 的和不带 $'$ 的作用），且由于作用只涉及 $k,k'$，因此可以将激发态简写为 $\ket{E}^{k,k'}=\ket{0}^k\ket{2}_{\alpha'}^{k'}$。因此[[#^2a457d|(12)]]可进一步简化为：
$$
\begin{align}
\hat{H}_{SE}^z&=-\frac{1}{U}\sum_{kk'}\sum_{\alpha'}\hat{H}_{T}^{z(k,k')}\ket{0}^k\ket{2}_{\alpha'}^{k'}\bra{2}_{\alpha'}^{k'}\bra{0}^k  \hat{H}_{T}^{\dagger z(k,k')} \\
&=-\frac{t^2}{U}\sum_{\sigma\sigma'}\sum_{kk'}\sum_{\alpha'}c^{\dagger}_{k\tau\sigma}c_{k'\tau\sigma}\ket{0}^k\ket{2}_{\alpha'}^{k'}\bra{2}_{\alpha'}^{k'}\bra{0}^kc^{\dagger}_{k'\tau\sigma'}c_{k\tau\sigma'} \delta_{\tau,\searrow} \\
&=-\frac{t^2}{U}\sum_{\sigma\sigma'}\sum_{kk'}\sum_{\alpha'}\left( c^{\dagger}_{k\tau\sigma}\ket{0}^k\bra{0}^kc_{k\tau\sigma'} \right) \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}^{k'}\bra{2}_{\alpha'}^{k'}c^{\dagger}_{k'\tau\sigma'} \right) \delta_{\tau,\searrow}  \\
&=-\frac{t^2}{U} \frac{1}{2}\sum_{\sigma\sigma'}\sum_{kk'}\sum_{\alpha'}\left\{ \left( c^{\dagger}_{k\tau\sigma}\ket{0}\bra{0}c_{k\tau\sigma'} \right) \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma'} \right) +(k\longleftrightarrow k^{\prime})\right\}  \delta_{\tau,\searrow}\tag{13}
\end{align}
$$

^1434dc

这里考虑到 $c_{k\tau\sigma}^{\dagger},\, c_{k\tau\sigma'}$ 本身就只作用在 $k$ 位点上，因此去掉了 $\ket{0}^k \bra{0}^k$ 上的角标 $k$；$c_{k'\tau\sigma},\,c_{k'\tau\sigma'}^{\dagger}$ 同理。此基础上，定义投影算符：$P_{\tau\sigma\sigma'}^i=c_{i\tau\sigma}^{\dagger}\ket{0}\bra{0}c_{i\tau\sigma'}$，考虑[[#^1434dc|(13)]]式中的部分求和项
$$
\begin{align}
&\sum_{\sigma\sigma'}\sum_{\alpha'}\left( c^{\dagger}_{k\tau\sigma}\ket{0}\bra{0}c_{k\tau\sigma'} \right) \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma'} \right)  \\
=&\sum_{\sigma\sigma'}\left( c^{\dagger}_{k\tau\sigma}\ket{0}\bra{0}c_{k\tau\sigma'} \right)\left[ \sum_{\alpha'} \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma'} \right) \right]   \tag{14}
\end{align}
$$

^440a33

其中对于 $\sigma\sigma'$ 的求和项，可以分为两类 $\sigma'=\sigma$ 和 $\sigma'=-\sigma$ 两类进行计算：

**A. $\sigma=\sigma'$**
此时[[#^440a33|(14)]]式变为：
$$
\sum_{\sigma}\left( c^{\dagger}_{k\tau\sigma}\ket{0}\bra{0}c_{k\tau\sigma} \right)\left[ \sum_{\alpha'} \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma} \right) \right]=\sum_{\sigma}P_{\tau\sigma\sigma}^k\left[ \sum_{\alpha'} \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma} \right) \right] \tag{15}
$$

^fb8f02

只考虑[[#^fb8f02|(15)]]式中方括号内的求和时，可以把 $\sigma$ 看作是固定的参数，此时对 $\alpha'$ 的求和，总共应有6项，对应 $\ket{2}$ 态的6种简并：
$$
\begin{gather}
\text{占据不同轨道：}\ket{\tau\sigma,(-\tau)\sigma},\ket{\tau\sigma,(-\tau)(-\sigma)},\ket{\tau(-\sigma),(-\tau)\sigma},\ket{\tau(-\sigma),(-\tau)(-\sigma)} \\ \\

\text{占据同一轨道：}\ket{\tau\sigma,\tau(-\sigma)},\ket{(-\tau)\sigma,(-\tau)(-\sigma)}
\end{gather}\tag{16}
$$

^f77654

要使使圆括号内 $c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma}$ 不为0，则 $\ket{2}_{\alpha'}$ 必须含有 $\ket{\tau\sigma,\cdot}$，符合要求的只有三个态：
$$
(1)\ket{\tau\sigma,(-\tau)\sigma},\,(2)\ket{\tau\sigma,(-\tau)(-\sigma)},\,(3)\ket{\tau\sigma,\tau(-\sigma)}
$$
对于 $(1)$， 
$$
c_{k'\tau\sigma}\ket{\tau\sigma,(-\tau)\sigma}\bra{\tau\sigma,(-\tau)\sigma}c^{\dagger}_{k'\tau\sigma}=c_{k'(-\tau)\sigma}^{\dagger}\ket{0}\bra{0}c_{k'(-\tau)\sigma}=P_{(-\tau)\sigma\sigma}^{k'}  
$$
对于 $(2)$，
$$
c_{k'\tau\sigma}\ket{\tau\sigma,(-\tau)(-\sigma)}\bra{\tau\sigma,(-\tau)(-\sigma)}c^{\dagger}_{k'\tau\sigma}=c_{k'(-\tau)(-\sigma)}^{\dagger}\ket{0}\bra{0}c_{k'(-\tau)(-\sigma)}=P_{(-\tau)(-\sigma)(-\sigma)}^{k'}  
$$
对于 $(3)$，
$$
c_{k'\tau\sigma}\ket{\tau\sigma,\tau(-\sigma)}\bra{\tau\sigma,\tau(-\sigma)}c^{\dagger}_{k'\tau\sigma}=c_{k'\tau(-\sigma)}^{\dagger}\ket{0}\bra{0}c_{k'\tau(-\sigma)}=P_{\tau(-\sigma)(-\sigma)}^{k'}  
$$
因此对于对于 $\sigma=\sigma'$ 的情况，[[#^fb8f02|(15)]]式变为
$$
\begin{align}
\sum_{\sigma}P_{\tau\sigma\sigma}^k\left[ \sum_{\alpha'} \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma} \right) \right] &=\sum_{\sigma}P_{\tau\sigma\sigma}^k\left[ P_{(-\tau)\sigma\sigma}^{k'}+P_{(-\tau)(-\sigma)(-\sigma)}^{k'} + P_{\tau(-\sigma)(-\sigma)}^{k'}\right]  \\
&=\sum_{\sigma}P_{\tau\sigma\sigma}^k\left[ P_{\tau(-\sigma)(-\sigma)}^{k'}+\sum_{\sigma'}P_{(-\tau)\sigma'\sigma'}^{k'} \right] \tag{17}
\end{align}
$$

^78f1b0

**B.** $\sigma=-\sigma'$
此时[[#^440a33|(14)]]式变为
$$
\begin{align}
&\sum_{\sigma}\left( c^{\dagger}_{k\tau\sigma}\ket{0}\bra{0}c_{k\tau(-\sigma)} \right)\left[ \sum_{\alpha'} \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau(-\sigma)} \right) \right] \\
=&\sum_{\sigma}P_{\tau\sigma(-\sigma)}^k\left[ \sum_{\alpha'} \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau(-\sigma)} \right) \right] \tag{18}
\end{align}
$$

^9fc20c

仍考虑[[#^f77654|(16)]]式给出的6个简并态，若要使圆括号内 $c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau(-\sigma)}$ 不为0，则只有 $\ket{\tau\sigma,\tau(-\sigma)}$ 这一个态满足要求，因此[[#^9fc20c|(18)]]式可以写为：
$$
\begin{align}
&\sum_{\sigma}P_{\tau\sigma(-\sigma)}^k\left[ \sum_{\alpha'} \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau(-\sigma)} \right) \right] \\
=&\sum_{\sigma}P_{\tau\sigma(-\sigma)}^kc_{k'\tau\sigma}\ket{\tau\sigma,\tau(-\sigma)}\bra{\tau\sigma,\tau(-\sigma)}c^{\dagger}_{k'\tau(-\sigma)} \\
=&\sum_{\sigma}P_{\tau\sigma(-\sigma)}^kc_{k'\tau\sigma}\ket{\tau\sigma,\tau(-\sigma)}\left[ c_{k'\tau(-\sigma)}\ket{\tau\sigma,\tau(-\sigma)} \right]^{\dagger}  \\
=&\sum_{\sigma}P^k_{\tau\sigma(-\sigma)}c^{\dagger}_{k'\tau(-\sigma)}\ket{0}[(-1)c^{\dagger}_{k'\tau\sigma}\ket{0} ] ^{\dagger} \\
=&-\sum_{\sigma}P^k_{\tau\sigma(-\sigma)}c^{\dagger}_{k'\tau(-\sigma)}\ket{0}\bra{0} c_{k'\tau\sigma}=-\sum_{\sigma}P^k_{\tau\sigma(-\sigma)}P_{\tau(-\sigma)\sigma}^{k'}\tag{19}
\end{align}
$$

^f6393c

注意这里在推导时，$c_{k'\tau\sigma}\ket{\tau\sigma,\tau(-\sigma)}\bra{\tau\sigma,\tau(-\sigma)}c^{\dagger}_{k'\tau(-\sigma)}$ 会多出一个负号，因为左侧和右侧的算符消去的是不同的态。

结合[[#^78f1b0|(17)]]式和[[#^f6393c|(19)]]式，[[#^440a33|(14)]]式最终可以写为：
$$
\begin{align}
&\sum_{\sigma\sigma'}\left( c^{\dagger}_{k\tau\sigma}\ket{0}\bra{0}c_{k\tau\sigma'} \right)\left[ \sum_{\alpha'} \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma'} \right) \right] \\
=& \sum_{\sigma}P_{\tau\sigma\sigma}^k\left[ P_{\tau(-\sigma)(-\sigma)}^{k'}+\sum_{\sigma'}P_{(-\tau)\sigma'\sigma'}^{k'} \right]-\sum_{\sigma}P^k_{\tau\sigma(-\sigma)}P_{\tau(-\sigma)\sigma}^{k'} \\
=&\sum_{\sigma}\left[P_{\tau\sigma\sigma}^k   P_{\tau(-\sigma)(-\sigma)}^{k'}-P^k_{\tau\sigma(-\sigma)}P_{\tau(-\sigma)\sigma}^{k'} \right]+\sum_{\sigma\sigma'}P_{\tau\sigma\sigma}^kP_{(-\tau)\sigma'\sigma'}^{k'}  \\
=&\sum_{\sigma\sigma'}(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau\sigma\sigma'}^kP_{\tau(-\sigma)(-\sigma')}^{k'}+\sum_{\sigma\sigma'}P_{\tau\sigma\sigma}^kP_{(-\tau)\sigma'\sigma'}^{k'}\tag{20}
\end{align}
$$

^be1bac

将[[#^be1bac|(20)]]式代入[[#^1434dc|(13)]]式，$\hat{H}_{SE}^z$ 可写为：
$$
\begin{align}
\hat{H}_{SE}^z=&-\frac{t^2}{U} \frac{1}{2}\sum_{\sigma\sigma'}\sum_{kk'}\sum_{\alpha'}\left\{ \left( c^{\dagger}_{k\tau\sigma}\ket{0}\bra{0}c_{k\tau\sigma'} \right) \left( c_{k'\tau\sigma}\ket{2}_{\alpha'}\bra{2}_{\alpha'}c^{\dagger}_{k'\tau\sigma'} \right) +(k\longleftrightarrow k^{\prime})\right\}  \delta_{\tau,\searrow} \\
=&-\frac{t^2}{U} \frac{1}{2} \sum_{kk'}\left[ \sum_{\sigma\sigma'}(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau\sigma\sigma'}^kP_{\tau(-\sigma)(-\sigma')}^{k'}+\sum_{\sigma\sigma'}P_{\tau\sigma\sigma}^kP_{(-\tau)\sigma'\sigma'}^{k'} \right]\delta_{\tau,\searrow} + \\
&\underbrace{ -\frac{t^2}{U} \frac{1}{2} \sum_{kk'}\left[ \sum_{\sigma\sigma'}(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau\sigma\sigma'}^{k'}P_{\tau(-\sigma)(-\sigma')}^{k}+\sum_{\sigma\sigma'}P_{\tau\sigma\sigma}^{k'}P_{(-\tau)\sigma'\sigma'}^{k} \right]\delta_{\tau,\searrow} }_{ (k\,\longleftrightarrow\, k') } \tag{21}
\end{align}
$$

^9cfc6f

对于第二项 $(k\longleftrightarrow k')$ 的求和，重命名指标：
$$
\begin{gather}
\sum_{\sigma\sigma'}(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau\sigma\sigma'}^{k'}P_{\tau(-\sigma)(-\sigma')}^{k}\xlongequal{\sigma\to-\sigma,\sigma'\to-\sigma'} \sum_{\sigma\sigma'}(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau(-\sigma)(-\sigma')}^{k'}P_{\tau\sigma\sigma'}^{k} \\
\sum_{\sigma\sigma'}P_{\tau\sigma\sigma}^{k'}P_{(-\tau)\sigma'\sigma'}^{k} \xlongequal{\sigma \to \sigma',\sigma'\to\sigma}\sum_{\sigma\sigma'}P_{\tau\sigma'\sigma'}^{k'}P_{(-\tau)\sigma\sigma}^{k}
\end{gather}
$$
再代入[[#^9cfc6f|(21)]]式，可得
$$
\begin{align}
\hat{H}_{SE}^z=&-\frac{t^2}{U} \frac{1}{2} \sum_{kk'}\left[ \sum_{\sigma\sigma'}(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau\sigma\sigma'}^kP_{\tau(-\sigma)(-\sigma')}^{k'}+\sum_{\sigma\sigma'}P_{\tau\sigma\sigma}^kP_{(-\tau)\sigma'\sigma'}^{k'} \right]\delta_{\tau,\searrow} + \\
&-\frac{t^2}{U} \frac{1}{2} \sum_{kk'}\left[ \sum_{\sigma\sigma'}(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau(-\sigma)(-\sigma')}^{k'}P_{\tau\sigma\sigma'}^{k}+\sum_{\sigma\sigma'}P_{\tau\sigma'\sigma'}^{k'}P_{(-\tau)\sigma\sigma}^{k} \right]\delta_{\tau,\searrow} \\
=&-\frac{t^2}{U} \frac{1}{2}\sum_{kk'}\sum_{\sigma\sigma'}\left[ 2(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau\sigma\sigma'}^kP_{\tau(-\sigma)(-\sigma')}^{k'}+P_{\tau\sigma\sigma}^kP_{(-\tau)\sigma'\sigma'}^{k'}+P_{(-\tau)\sigma\sigma}^{k}P_{\tau\sigma'\sigma'}^{k'} \right] \delta_{\tau,\searrow} \\
=&-\frac{t^2}{U}\sum_{ii'}\sum_{\sigma\sigma'} \left\{ (-1)^{1-\delta_{\sigma\sigma'}}P_{\tau\sigma\sigma'}^iP_{\tau(-\sigma)(-\sigma')}^{i'}+\frac{1}{2}\left[ P_{\tau\sigma\sigma}^iP_{(-\tau)\sigma'\sigma'}^{i'}+P_{(-\tau)\sigma\sigma}^{i}P_{\tau\sigma'\sigma'}^{i'} \right] \right\}    \delta_{\tau,\searrow} \\
=&-\frac{t^2}{U}\sum_{ii'}\sum_{\sigma\sigma'}(A_{\tau\sigma\sigma'}^{ii'}+B_{\tau\sigma\sigma'}^{ii'})\delta_{\tau,\searrow}\tag{22}
\end{align}
$$

^70f055

式中
$$
A_{\tau\sigma\sigma'}^{ii'}=(-1)^{1-\delta_{\sigma\sigma'}}P_{\tau\sigma\sigma'}^iP_{\tau(-\sigma)(-\sigma')}^{i'},\ B_{\tau\sigma\sigma'}^{ii'}=\frac{1}{2}\left[ P_{\tau\sigma\sigma}^iP_{(-\tau)\sigma'\sigma'}^{i'}+P_{(-\tau)\sigma\sigma}^{i}P_{\tau\sigma'\sigma'}^{i'} \right]
$$
将投影算符 $P^i_{\tau\sigma\sigma'}$ 写成自旋-轨道张量积的形式：
$$
\begin{align}
& P^{i}_{\tau\uparrow\uparrow}=\hat{o}^{i}_{\tau \tau} \hat{s}^{i}_{\uparrow\uparrow}=\left(\frac{\hat{n}_{i}}{2}\hat{I}+(-1)^ {\delta_{\tau,\searrow}}\hat{O}^{i}_{z}\right)\left(\frac{\hat{n}_{i}}{2}\hat{I}+\hat{S}^{i}_{z} \right),\\ & P^{i}_{\tau\downarrow\downarrow}=\hat{o}^{i}_{\tau \tau} \hat{ s}^{i}_{\downarrow\downarrow}=\left(\frac{\hat{n}_{i}}{2}\hat{I}+(-1)^{\delta_{\tau,\searrow}}\hat{O}^{i}_{z} \right)\left(\frac{\hat{n}_{i}}{2}\hat{I}-\hat{S}^{i}_{z}\right),\\ & P^{i}_{\tau\uparrow\downarrow}=\hat{o}^{i}_{\tau \tau} \hat{ s}^{i}_{\uparrow\downarrow}=\left(\frac{\hat{n}_{i}}{2}\hat{I}+(-1)^{\delta_{\tau,\searrow}}\hat{O}^{i}_{z} \right)\hat{S}^{i}_{+},\\ & P^{i}_{\tau\downarrow\uparrow}=\hat{o}^{i}_{\tau \tau} \hat{ s}^{i}_{\downarrow\uparrow}=\left(\frac{\hat{n}_{i}}{2}\hat{I}+(-1)^{\delta_{\tau,\searrow}}\hat{O}^{i}_{z} \right)\hat{S}^{i}_{-}
\end{align}\tag{23}
$$

^f63837

为方便计算，可以令 $\hat{C}_{i}=\dfrac{\hat{n}_{i}}{2}\hat{I}$。将[[#^f63837|(23)]]式代入[[#^70f055|(22)]]式，即可把[[#^70f055|(22)]]式改写成由自旋轨道算符构成的有效哈密顿量。考虑[[#^70f055|(22)]]式对自旋的求和部分，总共有四项，分别对应 $\uparrow\uparrow,\uparrow\downarrow,\downarrow\uparrow,\downarrow\downarrow$，为简化计算，根据[[#^f63837|(23)]]式的特征，可以将 $\uparrow\uparrow,\downarrow\downarrow$ 放在一起求和，将 $\uparrow\downarrow,\downarrow\uparrow$ 放在一起求和：
$$
\begin{align}
\hat{H}_{SE}^z&=-\frac{t^2}{U}\sum_{ii'}\sum_{\sigma\sigma'}(A_{\tau\sigma\sigma'}^{ii'}+B_{\tau\sigma\sigma'}^{ii'})\delta_{\tau,\searrow} \\
&=-\frac{t^2}{U}\sum_{ii'}\left( A_{\searrow\uparrow\uparrow}^{ii'}+B_{\searrow\uparrow\uparrow}^{ii'}+A_{\searrow\downarrow\downarrow}^{ii'}+B_{\searrow\downarrow\downarrow}^{ii'} \right)  +\left( A_{\searrow\uparrow\downarrow}^{ii'}+B_{\searrow\uparrow\downarrow}^{ii'}+A_{\searrow\downarrow\uparrow}^{ii'}+B_{\searrow\downarrow\uparrow}^{ii'} \right)\tag{24}
\end{align}
$$

^7fbb3d

首先计算 $\uparrow\uparrow,\downarrow\downarrow$ 的求和部分：
$$
\begin{align}
&A_{\searrow\uparrow\uparrow}^{ii'}+B_{\searrow\uparrow\uparrow}^{ii'}+A_{\searrow\downarrow\downarrow}^{ii'}+B_{\searrow\downarrow\downarrow}^{ii'} \\
=&P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\searrow\downarrow\downarrow}+\frac{1}{2}\left( P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\nearrow\uparrow\uparrow}+P^{i}_{\nearrow\uparrow\uparrow}P^{i'}_{\searrow\uparrow\uparrow} \right)  +P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow}+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\downarrow\downarrow} \right)   \\
=&P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\searrow\downarrow\downarrow}+P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow}+\frac{1}{2}\left( P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\nearrow\uparrow\uparrow}+P^{i}_{\nearrow\uparrow\uparrow}P^{i'}_{\searrow\uparrow\uparrow} \right)  +\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\downarrow\downarrow} \right)\tag{25}
\end{align}
$$

^9f5f9f

其中
$$
\begin{align}
&P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\searrow\downarrow\downarrow}+P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow} \\
=&\underbrace{ (\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i}+\hat{S}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{C}^{i'}-\hat{S}^{i'}_{z}) }_{  P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\searrow\downarrow\downarrow}}+P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow} \\
=&(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i}+\hat{S}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{C}^{i'}-\hat{S}^{i'}_{z})+(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i}-\hat{S}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z}) \\
=&(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})\left[ (\hat{C}^{i}+\hat{S}^i_{z}) (\hat{C}^{i'}-\hat{S}^{i'}_{z})+(\hat{C}^{i}-\hat{S}^i_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z})\right]  \\
=&2(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{S}^i_{z}\hat{S}^{i'}_{z})\tag{26}
\end{align}
$$
$$
\begin{align}
&\frac{1}{2}\left( P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\nearrow\uparrow\uparrow}+P^{i}_{\nearrow\uparrow\uparrow}P^{i'}_{\searrow\uparrow\uparrow} \right)+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\downarrow\downarrow} \right) \\
=& \frac{(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}+\hat{O}^{i'}_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z}) +(\hat{C}^i+\hat{O}^i_{z})(\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z})}{2}  \\
&+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\downarrow\downarrow} \right) \\
=&\frac{1}{2}\left\{ (\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z})\left[ (\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}+\hat{O}^{i'}_{z})+ (\hat{C}^i+\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})\right] \right\} \\
&+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\downarrow\downarrow} \right) \\
=&(\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'})+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\downarrow\downarrow} \right) \\
=&(\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'})+(\hat{C}^{i}-\hat{S}^{i}_{z})(\hat{C}^{i'}-\hat{S}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'}) \\
=&\left[ (\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z})+ (\hat{C}^{i}-\hat{S}^{i}_{z})(\hat{C}^{i'}-\hat{S}^{i'}_{z})\right] (\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'})  \\
=&2(\hat{C}^{i}\hat{C}^{i'}+\hat{S}_{z}^i \hat{S}_{z}^{i'}) (\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'}) \tag{27}
\end{align}
$$
由此[[#^9f5f9f|(25)]]式可化简为：
$$
\begin{align}
&A_{\searrow\uparrow\uparrow}^{ii'}+B_{\searrow\uparrow\uparrow}^{ii'}+A_{\searrow\downarrow\downarrow}^{ii'}+B_{\searrow\downarrow\downarrow}^{ii'} \\
=&2(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{S}^i_{z}\hat{S}^{i'}_{z})+2(\hat{C}^{i}\hat{C}^{i'}+\hat{S}_{z}^i \hat{S}_{z}^{i'}) (\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'}) \tag{28}
\end{align}
$$

^2aef86

接下来计算 $\uparrow\downarrow,\downarrow\uparrow$ 的求和部分：
$$
\begin{align}
&A_{\searrow\uparrow\downarrow}^{ii'}+B_{\searrow\uparrow\downarrow}^{ii'}+A_{\searrow\downarrow\uparrow}^{ii'}+B_{\searrow\downarrow\uparrow}^{ii'} \\
=&-P^{i}_{\searrow\uparrow\downarrow}P^{i'}_{\searrow\downarrow\uparrow}+\frac{1}{2}\left( P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\uparrow\uparrow}P^{i'}_{\searrow\downarrow\downarrow} \right)  -P^{i}_{\searrow\downarrow\uparrow}P^{i'}_{\searrow\uparrow\downarrow}+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\uparrow\uparrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow} \right)   \\
=&-P^{i}_{\searrow\uparrow\downarrow}P^{i'}_{\searrow\downarrow\uparrow} -P^{i}_{\searrow\downarrow\uparrow}P^{i'}_{\searrow\uparrow\downarrow}+\frac{1}{2}\left( P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\uparrow\uparrow}P^{i'}_{\searrow\downarrow\downarrow} \right)+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\uparrow\uparrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow} \right)  \tag{29}
\end{align}
$$

^b35d07

其中
$$
\begin{align}
-P^{i}_{\searrow\uparrow\downarrow}P^{i'}_{\searrow\downarrow\uparrow} -P^{i}_{\searrow\downarrow\uparrow}P^{i'}_{\searrow\uparrow\downarrow}&=-(\hat{C}^i-\hat{O}^i_{z})\hat{S}_{+}^i(\hat{C}^{i'}-\hat{O}^{i'}_{z})\hat{S}_{-}^{i'}-(\hat{C}^i-\hat{O}^i_{z})\hat{S}_{-}^i(\hat{C}^{i'}-\hat{O}^{i'}_{z})\hat{S}_{+}^{i'} \\
&=-(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{S}_{+}^i\hat{S}_{-}^{i'}+\hat{S}_{-}^i\hat{S}_{+}^{i'})\tag{30}
\end{align}
$$
$$
\begin{align}
&\frac{1}{2}\left( P^{i}_{\searrow\uparrow\uparrow}P^{i'}_{\nearrow\downarrow\downarrow}+P^{i}_{\nearrow\uparrow\uparrow}P^{i'}_{\searrow\downarrow\downarrow} \right)+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\uparrow\uparrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow} \right)  \\
=& \frac{(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}+\hat{O}^{i'}_{z})(\hat{C}^{i'}-\hat{S}^{i'}_{z}) +(\hat{C}^i+\hat{O}^i_{z})(\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{C}^{i'}-\hat{S}^{i'}_{z})}{2} \\
&+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\uparrow\uparrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow} \right) \\
=&(\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}-\hat{S}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'})+\frac{1}{2}\left( P^{i}_{\searrow\downarrow\downarrow}P^{i'}_{\nearrow\uparrow\uparrow}+P^{i}_{\nearrow\downarrow\downarrow}P^{i'}_{\searrow\uparrow\uparrow} \right) \\
=&(\hat{C}^{i}+\hat{S}^{i}_{z})(\hat{C}^{i'}-\hat{S}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'})+(\hat{C}^{i}-\hat{S}^{i}_{z})(\hat{C}^{i'}+\hat{S}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'}) \\
=&2(\hat{C}^{i}\hat{C}^{i'}-\hat{S}_{z}^i \hat{S}_{z}^{i'}) (\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'}) \tag{31}
\end{align}
$$
由此[[#^b35d07|(29)]]式可化简为：
$$
\begin{align}
&A_{\searrow\uparrow\downarrow}^{ii'}+B_{\searrow\uparrow\downarrow}^{ii'}+A_{\searrow\downarrow\uparrow}^{ii'}+B_{\searrow\downarrow\uparrow}^{ii'} \\
=&-(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{S}_{+}^i\hat{S}_{-}^{i'}+\hat{S}_{-}^i\hat{S}_{+}^{i'})+2(\hat{C}^{i}\hat{C}^{i'}-\hat{S}_{z}^i \hat{S}_{z}^{i'}) (\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'})\tag{32}
\end{align}
$$

^3b02dd

结合[[#^2aef86|(28)]]式与[[#^3b02dd|(32)]]式，
$$
\begin{align}
&\left( A_{\searrow\uparrow\uparrow}^{ii'}+B_{\searrow\uparrow\uparrow}^{ii'}+A_{\searrow\downarrow\downarrow}^{ii'}+B_{\searrow\downarrow\downarrow}^{ii'} \right)  +\left( A_{\searrow\uparrow\downarrow}^{ii'}+B_{\searrow\uparrow\downarrow}^{ii'}+A_{\searrow\downarrow\uparrow}^{ii'}+B_{\searrow\downarrow\uparrow}^{ii'} \right)  \\
=&2(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{C}^{i}\hat{C}^{i'}-\hat{S}^i_{z}\hat{S}^{i'}_{z})+2(\hat{C}^{i}\hat{C}^{i'}+\hat{S}_{z}^i \hat{S}_{z}^{i'}) (\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'}) \\
&-(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(\hat{S}_{+}^i\hat{S}_{-}^{i'}+\hat{S}_{-}^i\hat{S}_{+}^{i'})+2(\hat{C}^{i}\hat{C}^{i'}-\hat{S}_{z}^i \hat{S}_{z}^{i'}) (\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'}) \\
=&(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(2\hat{C}^{i}\hat{C}^{i'}\underbrace{ -2\hat{S}^i_{z}\hat{S}^{i'}_{z}-\hat{S}_{+}^i\hat{S}_{-}^{i'}-\hat{S}_{-}^i\hat{S}_{+}^{i'} }_{ -2\hat{\boldsymbol{S}}^{i}\cdot\hat{\boldsymbol{S}}^{i'} })+ \\
&2(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'})(\hat{C}^{i}\hat{C}^{i'}-\hat{S}_{z}^i \hat{S}_{z}^{i'}+\hat{C}^{i}\hat{C}^{i'}+\hat{S}_{z}^i \hat{S}_{z}^{i'}) \\
=&(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(2\hat{C}^{i}\hat{C}^{i'}-2\hat{\boldsymbol{S}}^{i}\cdot\hat{\boldsymbol{S}}^{i'})+4\hat{C}^{i}\hat{C}^{i'}(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'})\tag{33}
\end{align}
$$

^fbc49b

由[[#^fbc49b|(33)]]式，[[#^7fbb3d|(24)]]式的 $\hat{H}_{SE}^z$ 可以改写为：
$$
\begin{align}
\hat{H}_{SE}^z&=-\frac{t^2}{U}\sum_{ii'}\left( A_{\searrow\uparrow\uparrow}^{ii'}+B_{\searrow\uparrow\uparrow}^{ii'}+A_{\searrow\downarrow\downarrow}^{ii'}+B_{\searrow\downarrow\downarrow}^{ii'} \right)  +\left( A_{\searrow\uparrow\downarrow}^{ii'}+B_{\searrow\uparrow\downarrow}^{ii'}+A_{\searrow\downarrow\uparrow}^{ii'}+B_{\searrow\downarrow\uparrow}^{ii'} \right)\\
&=-\frac{t^2}{U}\sum_{ii'}(\hat{C}^i-\hat{O}^i_{z})(\hat{C}^{i'}-\hat{O}^{i'}_{z})(2\hat{C}^{i}\hat{C}^{i'}-2\hat{\boldsymbol{S}}^{i}\cdot\hat{\boldsymbol{S}}^{i'})+4\hat{C}^{i}\hat{C}^{i'}(\hat{C}^{i}\hat{C}^{i'}-\hat{O}_{z}^i \hat{O}_{z}^{i'}) \\
&=\frac{t^2}{U} \sum_{ii'}(2\hat{\boldsymbol{S}}^{i}\cdot\hat{\boldsymbol{S}}^{i'}-2\hat{C}^{i}\hat{C}^{i'})(\hat{O}^i_{z}-\hat{C}^i)(\hat{O}^{i'}_{z}-\hat{C}^{i'})+4\hat{C}^{i}\hat{C}^{i'}(\hat{O}_{z}^i \hat{O}_{z}^{i'}-\hat{C}^{i}\hat{C}^{i'}) \\
&=\frac{2t^2}{U} \sum_{ii'}(\hat{\boldsymbol{S}}^{i}\cdot\hat{\boldsymbol{S}}^{i'}-\hat{C}^{i}\hat{C}^{i'})(\hat{O}^i_{z}-\hat{C}^i)(\hat{O}^{i'}_{z}-\hat{C}^{i'})+2\hat{C}^{i}\hat{C}^{i'}(\hat{O}_{z}^i \hat{O}_{z}^{i'}-\hat{C}^{i}\hat{C}^{i'}) \\
&=\frac{2t^2}{U} \sum_{ii'}\left( \hat{\boldsymbol{S}}^{i}\cdot\hat{\boldsymbol{S}}^{i'}-\frac{\hat{n}_{i}\hat{n}_{i'}}{4} \right)\left( \hat{O}^i_{z}- \frac{\hat{n}_{i}}{2} \right)\left( \hat{O}^{i'}_{z}-\frac{\hat{n}_{i'}}{2} \right)+\frac{\hat{n}_{i}\hat{n}_{i'}}{2} \left( \hat{O}_{z}^i \hat{O}_{z}^{i'}-\frac{\hat{n}_{i}\hat{n}_{i'}}{4} \right) \tag{34}
\end{align}
$$

^143adf

至此，我们完整得到了只考虑沿 $z$ 向存在hopping作用的超交换哈密顿量，需要再次注意的是推导这个模型进行的几个假设：1. 不考虑洪特规则耦合，略去了[[#^332edd|(3-a)]]中所有含 $J$ 的项；2. 只考虑相邻格点上的跃迁，且不考虑同一格点不同轨道上的跃迁；3. 将hopping项看作微扰，认为 $t\ll U$；4. 推导时假设不同格点的投影算符是可交换的。
尽管[[#^143adf|(34)]]式所代表的结果不是完善的，但从它出发我们也能分析出关于轨道有序的信息。首先回忆一下我们推导[[#^143adf|(34)]]式的目的，我们是希望将 $\hat{H}_{SE}^z$ 在基态简并空间 $V_{G}$ 中表示出来，因此进行了一系列计算推导出了[[#^143adf|(34)]]式。那么接下来做的就是把 $\hat{H}_{SE}^z$ 在基态空间中进行对角化，或者说寻找它的特征向量。
具体的我们考虑下面几种特殊的基态组合对应的能量期望值：

自旋铁磁排列，$\ket{G}=\ket{\tau\uparrow}_{\alpha}^i\ket{\tau'\uparrow}_{\alpha'}^{i'}$ 或 $\ket{\tau\downarrow}_{\alpha}^i\ket{\tau'\downarrow}_{\alpha'}^{i'}$
以 $\ket{G}=\ket{\tau\uparrow}_{\alpha}^i\ket{\tau'\uparrow}_{\alpha'}^{i'}$ 为例，计算涉及的几种算符在这一基态上的作用：
$$
\begin{gather}
\bra{G}  \hat{\boldsymbol{S}}^i\cdot \hat{\boldsymbol{S}}^{i'}\ket{G} =\bra{\uparrow^{i'}\uparrow^{i}} \hat{S}^i_{z}\hat{S}^{i'}_{z}+\frac{1}{2}(\hat{S}^i_{+}\hat{S}^{i'}_{-}+\hat{S}^i_{-}\hat{S}^{i'}_{+})\ket{\uparrow^i\uparrow^{i'}}=\frac{1}{4} \\
\bra{G}\hat{O}_{z}^i \hat{O}_{z}^{i'} \ket{G}=\bra{\tau'^{i'}\tau^{i}}\hat{O}_{z}^i \hat{O}_{z}^{i'} \ket{\tau^i\tau'^{i'}} =  \frac{1}{4}\delta_{\tau,\tau'}-\frac{1}{4}\delta_{\tau,-\tau'} \\
\bra{G}\hat{n}^{i}\ket{G}  =\bra{G}\hat{n}^{i'}\ket{G}=1
\end{gather}\tag{35}
$$

^d4f58e

由此可得
$$
\Delta E_{\tau \uparrow,\tau' \uparrow}=\Delta E_{\tau \downarrow,\tau' \downarrow}=\bra{G}\hat{H}_{SE}^{z(i,i')}\ket{G}=-\frac{2t^2}{U}\frac{1}{4}(1-\delta_{\tau,\tau'})\tag{36}
$$
可见**在自旋铁磁排列的情形下，若轨道交替排列（相邻位点电子占据不同的轨道态），则对应的能量更低，这就形成了一种交替轨道序**。还值得注意的是，自旋铁磁排列的态都是 $\hat{H}_{SE}^z$ 的能量本征态，这是因为这两个态在上述计算中都是相应算符的本征态。

自旋反铁磁排列，$\ket{G}=\ket{\tau\uparrow}_{\alpha}^i\ket{\tau'\downarrow}_{\alpha'}^{i'}$ 或 $\ket{\tau\downarrow}_{\alpha}^i\ket{\tau'\uparrow}_{\alpha'}^{i'}$
以 $\ket{G}=\ket{\tau\uparrow}_{\alpha}^i\ket{\tau'\downarrow}_{\alpha'}^{i'}$ 为例，算符在这一基态上的作用参考[[#^d4f58e|(35)]]式给出的内容，但需要注意的是：
$$
\begin{gather}
\bra{G}  \hat{\boldsymbol{S}}^i\cdot \hat{\boldsymbol{S}}^{i'}\ket{G} =\bra{\downarrow^{i'}\uparrow^{i}} \hat{S}^i_{z}\hat{S}^{i'}_{z}+\frac{1}{2}(\hat{S}^i_{+}\hat{S}^{i'}_{-}+\hat{S}^i_{-}\hat{S}^{i'}_{+})\ket{\uparrow^i\downarrow^{i'}}=-\frac{1}{4}
\end{gather}
$$
此时 $\ket{G}$ 不再是 $\hat{\boldsymbol{S}}^i\cdot \hat{\boldsymbol{S}}^{i'}$ 的本征态，但是我们仍可计算这个态对应的期望值，定性的对系统状态作出判断：
$$
\begin{align}
\Delta E_{\tau\uparrow,\tau'\downarrow}=\Delta E_{\tau\downarrow,\tau'\uparrow}&=\bra{G}\hat{H}_{SE}^{z(i,i')}\ket{G}=\frac{2t^2}{U}\cdot \left( -\frac{1}{4}-\frac{1}{4} \right) \delta_{\tau,\tau'}\delta_{\tau,\searrow}-\frac{2t^2}{U}\frac{1}{4}(1-\delta_{\tau,\tau'}) \\
&=-\frac{2t^2}{U}\left[ \frac{1}{2}\delta_{\tau,\tau'}\delta_{\tau,\searrow}+\frac{1}{4}(1-\delta_{\tau,\tau'}) \right]\tag{37}
\end{align}
$$

^513f41

可见在**自旋反铁磁排列**下，为使能量期望值降低，[[#^513f41|(37)]]式中括号内的值越大越好，最大值为 $\dfrac{1}{2}$，此时 $\tau=\tau'=\searrow$，也就是**轨道倾向于同向排列，且相邻位点电子都占据 $\ket{\searrow}$ 态，由此形成了一种同向轨道序**。

但是上述讨论均假设自旋铁磁或反铁磁，这两种状态只有当材料在较低的温度下才会体现，而轨道序在高于材料铁磁或反铁磁相变温度时仍然存在，此时自旋处于顺磁排布
$$
\langle\hat{\boldsymbol{S}}^i\cdot \hat{\boldsymbol{S}}^{i'}\rangle=0
$$
我们可以通过变分法求解此时的电子轨道排布，**这并不是在“证明轨道有序存在”**，而是在 **假定轨道有序已经形成的情况下，研究其具体排布（即轨道态的取向 ）和能量最优条件**。例如对于 $\ce{ LaMnO_{3} }$，它在 $z$ 方向具有同向轨道序，设变分参数为 $\theta$，相应的态记为 $\ket{\theta}$，则 $\ket{\theta}_{i \pm \hat{z}}=\ket{\theta}_{i}$，这里
$$
\ket{\theta}_{i}=-\sin\frac{\theta-\pi}{2}\ket{x^{2}-y^{2}} +\cos\frac{ \theta-\pi}{2}\ket{3z^{2}-r^{2}} =-\sin\frac{\theta-\pi}{2}\ket{\nearrow} +\cos\frac{ \theta-\pi}{2}\ket{\searrow} \tag{38}
$$

^715ea7

$$
\begin{align}
\langle \hat{O}_{z}\rangle_{\theta}=\bra{\theta} \hat{O}_{z}\ket{\theta}&= \bra{\theta}\left( - \frac{1}{2}\sin\frac{\theta-\pi}{2}\ket{\nearrow} -\frac{1}{2}\cos\frac{ \theta-\pi}{2}\ket{\searrow}  \right) =-\frac{1}{2}\left(\cos^2\frac{\theta-\pi}{2} -\sin^2\frac{\theta-\pi}{2} \right)  \\
&=-\frac{1}{2}\cos(\theta-\pi)
\end{align}
$$
$\hat{H}_{SE}^z$ 在 $\ket{\theta}_{i}$ 上的期望为：
$$
\begin{align}
\langle \hat{H}_{SE}^z\rangle_{\theta}=&\frac{2t^2}{U}\sum_{ii'}\left\langle \hat{\boldsymbol{S}}^i\cdot \hat{\boldsymbol{S}}^{i'}-\frac{1}{4} \right\rangle\left\langle  \left( \hat{O}^i_{z}- \frac{\hat{n}_{i}}{2} \right)\left( \hat{O}^{i'}_{z}-\frac{\hat{n}_{i'}}{2} \right)  \right\rangle \\
&+\frac{2t^2}{U}\sum_{ii'}\left\langle \frac{\hat{n}_{i}\hat{n}_{i'}}{2} \right\rangle\left\langle \hat{O}_{z}^i \hat{O}_{z}^{i'}-\frac{\hat{n}_{i}\hat{n}_{i'}}{4} \right\rangle \\
=&\frac{2t^2}{U}\sum_{ii'}\left[ \left( -\frac{1}{4} \right)\left( \frac{\cos(\theta-\pi)+1}{2} \right)^2+\frac{1}{2} \frac{\cos^2(\theta-\pi)-1}{4} \right]  \\
=&\sum_{ii'}\frac{2t^2}{U} \frac{-\cos^2(\theta-\pi)-1-2\cos(\theta-\pi)+2\cos^2(\theta-\pi)-2}{16} \\
=&\sum_{ii'}\frac{t^2}{8U}\left[ \cos^2(\theta-\pi)-2\cos(\theta-\pi) \right]+\text{const.}\tag{39}  
\end{align}
$$

^90a765

当 $\cos(\theta-\pi)=1\Rightarrow \theta=\pi$ 时 $\Delta E_{\theta}=\dfrac{t^2}{8U}\left[ \cos^2(\theta-\pi)-2\cos(\theta-\pi) \right]$ 取得最小值，此时对应的态为
$$
\ket{\theta=\pi }=\ket{3z^2-r^2}=\ket{\searrow}   
$$
这说明此时电子倾向于统一排布在 $\ket{\searrow}$ 轨道上。这与实际的 $\ce{ LaMnO_{3} }$ 在 $z$ 向的轨道序分布有差异，原因是我们当前的计算都仅限于 $z$ 方向，而实际需要考虑体系在三维空间中整体的超交换能。若要考虑其他方向的计算，则可作代换：
$$
\begin{gather}
\hat{O}_z^i\underbrace{\to}_{\hat{z}\to\hat{x}}-\frac{1}{2}\hat{O}_z^i-\frac{\sqrt{3}}{2}\hat{O}_x^i \\
\hat{O}_z^i\underbrace{\to}_{\hat{z}\to\hat{y}}-\frac{1}{2}\hat{O}_z^i+\frac{\sqrt{3}}{2}\hat{O}_x^i
\end{gather}\tag{40}
$$

^8a243e

将[[#^8a243e|(40)]]式，可得 $\hat{H}_{SE}^x$ 与 $\hat{H}_{SE}^y$，这里不做详细计算。在此基础上，仍以 $\ce{ LaMnO_{3} }$ 为例，它在 $x-y$ 面内具有交替轨道序（相邻轨道空间取向相互正交），若 $i$ 点位的轨道态仍然满足 [[#^715ea7|(38)]]式，则 $i'=i \pm \hat{x}$ 或 $i\pm \hat{y}$ 的轨道态可以表示为：
$$
\ket{\theta}_{i'}= \sin\frac{\theta-\pi}{2}\ket{x^{2}-y^{2}} +\cos\frac{ \theta-\pi}{2}\ket{3z^{2}-r^{2}} =\sin\frac{\theta-\pi}{2}\ket{\nearrow} +\cos\frac{ \theta-\pi}{2}\ket{\searrow}\tag{41}
$$
相应的 $\hat{F}^i=-\dfrac{1}{2}\hat{O}_{z}^i-\dfrac{\sqrt{ 3 }}{2}\hat{O}_{x}^i$ 及 $\hat{F}^{i'}=-\dfrac{1}{2}\hat{O}_{z}^{i'}-\dfrac{\sqrt{ 3 }}{2}\hat{O}_{x}^{i'}$ 在 $\ket{\theta}_{i},\,\ket{\theta}_{i'}$ 上的期望为
$$
\begin{align}
\left\langle  \hat{F}^i  \right\rangle_{\theta^i}&=\left\langle  -\frac{1}{2}\hat{O}_{z}^i-\frac{\sqrt{ 3 }}{2}\hat{O}_{x}^i  \right\rangle_{\theta^i} \\
&=\bra{\theta}_{i}\left( -\frac{1}{2}\hat{O}_{z}^i-\frac{\sqrt{ 3 }}{2}\hat{O}_{x}^i \right)  \ket{\theta}_{i} =-\frac{1}{2}\langle \hat{O}_{z}\rangle_{\theta^i}-\frac{\sqrt{ 3 }}{2}\bra{\theta}_{i}\hat{O}_{x}^i\ket{\theta}_{i} \\
&=\frac{\cos(\theta-\pi)}{4}-\frac{\sqrt{ 3 }}{4}\bra{\theta}_{i} \hat{O}_{+}^i+\hat{O}_{-}^i\ket{\theta}_{i}  \\
&=\frac{\cos(\theta-\pi)}{4}-\frac{\sqrt{ 3 }}{4}\bra{\theta}_{i}\left(\cos\frac{ \theta-\pi}{2}\ket{\nearrow}  -\sin\frac{\theta-\pi}{2}\ket{\searrow}   \right) \\
&=\frac{\cos(\theta-\pi)}{4}+\frac{\sqrt{ 3 }}{4}\sin(\theta-\pi)\tag{42} 
\end{align}
$$

^bab383

$$
\begin{align}
\left\langle  \hat{F}^{i'}  \right\rangle_{\theta^{i'}}&=\left\langle  -\frac{1}{2}\hat{O}_{z}^{i'}-\frac{\sqrt{ 3 }}{2}\hat{O}_{x}^{i'}  \right\rangle_{\theta^{i'}} \\
&=\bra{\theta}_{i'}\left( -\frac{1}{2}\hat{O}_{z}^{i'}-\frac{\sqrt{ 3 }}{2}\hat{O}_{x}^{i'} \right)  \ket{\theta}_{i'}=-\frac{1}{2}\langle \hat{O}_{z}\rangle_{\theta^{i'}}-\frac{\sqrt{ 3 }}{2}\bra{\theta}_{i'}\hat{O}_{x}^{i'}\ket{\theta}_{i'} \\
&=\frac{\cos(\theta-\pi)}{4}-\frac{\sqrt{ 3 }}{4}\bra{\theta}_{i'} \hat{O}_{+}^{i'}+\hat{O}_{-}^{i'}\ket{\theta}_{i'}  \\
&=\frac{\cos(\theta-\pi)}{4}-\frac{\sqrt{ 3 }}{4}\bra{\theta}_{i'}\left(\cos\frac{ \theta-\pi}{2}\ket{\nearrow}  +\sin\frac{\theta-\pi}{2}\ket{\searrow}   \right) \\
&=\frac{\cos(\theta-\pi)}{4}-\frac{\sqrt{ 3 }}{4}\sin(\theta-\pi)\tag{43}
\end{align}
$$

^aec414

利用[[#^bab383|(42)]]及[[#^aec414|(43)]]式，计算得到 $\hat{H}_{SE}^x$ 的期望：
$$
\begin{align}
\langle \hat{H}_{SE}^x\rangle_{\theta^i,\theta^{i'}}=&\frac{2t^2}{U}\sum_{ii'}\left\langle \hat{\boldsymbol{S}}^i\cdot \hat{\boldsymbol{S}}^{i'}-\frac{1}{4} \right\rangle\left\langle  \left( \hat{F}^i- \frac{\hat{n}_{i}}{2} \right)\right\rangle_{\theta^i} \left\langle\left( \hat{F}^{i'}-\frac{\hat{n}_{i'}}{2} \right)  \right\rangle_{\theta^{i'}} \\
&+\frac{2t^2}{U}\sum_{ii'}\left\langle \frac{\hat{n}_{i}\hat{n}_{i'}}{2} \right\rangle \left( \underbrace{ \left\langle\hat{F}^{i} \right\rangle_{\theta^i} }_{ A }\underbrace{ \left\langle\hat{F}^{i'}\right\rangle_{\theta^{i'}} }_{ B }-\frac{\left\langle\hat{n}_{i}\hat{n}_{i'}\right\rangle}{4} \right)   \\
=&\frac{2t^2}{U}\sum_{ii'}\left( -\frac{1}{4} \right)\left( A-\frac{1}{2}  \right)\left( B-\frac{1}{2} \right)+\frac{2t^2}{U}\sum_{ii'} \frac{1}{2} \left( AB-\frac{1}{4} \right)\\
=&\sum_{ii'}\frac{2t^2}{U} \left[ -\frac{1}{4}\left( A-\frac{1}{2} \right) \left( B-\frac{1}{2} \right)+\frac{1}{2} AB \right] +\text{const.} \\
=&\sum_{ii'}\frac{2t^2}{U}\left( \frac{AB}{4}+ \frac{A+B}{8} \right) +\text{const.} \\
=&\sum_{ii'}\frac{t^2}{8U}\left[ \cos^2(\theta-\pi)+\cos(\theta-\pi) \right] +\text{const.}\tag{44}
\end{align}
$$

^5a5619

由对称性可得
$$
\langle \hat{H}_{SE}^y\rangle_{\theta^i,\theta^{i'}}=\langle \hat{H}_{SE}^x\rangle_{\theta^i,\theta^{i'}}=\sum_{ii'}\frac{t^2}{8U}\left[ \cos^2(\theta-\pi)+\cos(\theta-\pi) \right] +\text{const.}\tag{45}
$$

^0a8bb2

结合[[#^90a765|(39)]]，[[#^5a5619|(44)]]和[[#^0a8bb2|(45)]]，$\ce{ LaMnO_{3} }$ 在超交换作用下的总哈密顿量在参数 $\theta$ 下的期望为：
$$
\begin{align}
\langle\hat{H}_{SE}\rangle&=\langle\hat{H}_{SE}^x+\hat{H}_{SE}^y+\hat{H}_{SE}^z\rangle=\langle\hat{H}_{SE}^x\rangle+\langle\hat{H}_{SE}^y\rangle+\langle\hat{H}_{SE}^z\rangle \\
&=\sum_{ii'}\frac{t^2}{8U}\left[ \cos^2(\theta-\pi)-2\cos(\theta-\pi)+ 2\cos^2(\theta-\pi)+2\cos(\theta-\pi)\right]  \\
&=\sum_{ii'}\frac{3t^2}{8U} \cos^2(\theta-\pi)  \tag{46}
\end{align}
$$
当 $\cos(\theta-\pi)=0\Rightarrow \theta=\dfrac{\pi}{2}$ 时 $\Delta E_{\theta}=\dfrac{3t^2}{8U} \cos^2(\theta-\pi)$ 取得最小值，
$$
\ket{\theta}_{i}= \frac{\sqrt{ 2 }}{2}\ket{x^2-y^2}+\frac{\sqrt{ 2 }}{2}\ket{3z^2-r^2}  \tag{47}
$$
$\ce{ LaMnO_{3} }$ 沿 $z$ 向与位点 $i$ 相邻的轨道态为：
$$
\ket{\theta}_{i\pm \hat{z}}=\ket{\theta}_{i}=  \frac{\sqrt{ 2 }}{2}\ket{x^2-y^2}+\frac{\sqrt{ 2 }}{2}\ket{3z^2-r^2}\tag{48}
$$
$\ce{ LaMnO_{3} }$ 在 $x-y$ 面内与位点 $i$ 相邻的轨道态为：
$$
\ket{\theta}_{i\pm \hat{x}}= \ket{\theta}_{i\pm \hat{x}}=-\frac{\sqrt{ 2 }}{2}\ket{x^2-y^2}+\frac{\sqrt{ 2 }}{2}\ket{3z^2-r^2}\tag{49}
$$
至此，我们通过Kugel-Khomskii superexchange模型完整地推导出了 $\ce{ LaMnO_{3} }$ 的轨道序状态。
   