# Description
這份文件是節錄edx的一門課程Street Fighting Math(SFM)上的精華內容，供沒修過這堂課的朋友一睹其樂趣。英文文字的部份是直接由課程內容剪下貼上。數學的部份會寫得非常隨意，重意不重形。

課程網址 https://www.edx.org/course/mitx/mitx-6-sfmx-street-fighting-math-1501#.U4bhk1T_QjA 

有關這門課：

這門課和其他MOOC不同的地方主要在於課程內容都是閱讀材料，配合一些網頁上的互動元件，授課影片非常稀少。課程的目標是傳授估算的數學技巧。大部分在學校的課程強調嚴謹（rigor），但解決真實世界問題的時候嚴謹可能導致很多冤枉路(課程中稱為屍僵 rigor mortis )，而估算可以指引正確的道路。

教授提供了一個比較好想像的例子：
> The theme of this course is the virtue of approximation, of having a rough idea of what to expect before starting exact calculations or looking for a proof. Imagine that you are studying a subject based on five postulates used to construct a 10-step proof. Without understanding why the theorem is true, you must search a gigantic space of $5^{10}$ paths. A common response is to random walk through the problem space, in the hope of wandering into the theorem. Higher-level approaches and ways of thinking about the problem help you break the path into manageable pieces, each with a tractable search space.



# Street Fighting Math tools

- Dimension Analysis
- Easy Case
- Lumping
- Pictorial Proofs
- Taking out the Big Part
- Analogy

# Dimension Analysis

亮點：猜積分技巧
重要概念：
 
 - 指數沒有Dimension
 - $dx$代表微小的$x$，$dx$的Dimension和$x$相同
 - $\frac{d}{dx}$的dimension和$\frac{1}{x}$一樣

$$\displaystyle  2^ n = \underbrace{2\times 2\times \cdots \times 2}_{\hbox{$n$ terms}}.$$
The notion of “how many times" is a pure number, so an exponent is dimensionless.

範例：估算積分
$$\displaystyle  \def\1 {e^{-\alpha x^2}}  \left[\int e^{-\alpha x^2}\, dx\right] = \underbrace{\left[e^{-\alpha x^2}\right]}_{1} \times \underbrace{\left[dx\right]}_{{\rm L}} = {\rm L}.$$

The third and final step in this dimensional analysis is to construct an $f(\alpha)$ with the same dimensions as the integral. Because the dimensions of $\alpha$ are $L−2$, the only way to turn α into a length is to form $\alpha^{−1/2}$. Therefore, $$\displaystyle  f(\alpha )\sim \alpha ^{-1/2}.$$

範例：
$${d\over dt} t^ n = nt^{x}$$
Because "d" means "a little bit of," the derivative operator d/dt has the same dimensions as $1/t$. Thus, the whole left side, which also contains $t^n$, has the same dimensions as $t^{n−1}$.The right side has to have the same dimensions. On the right side, the factor of $n$ has no dimensions: From the left side, we can see that $n$ is an exponent, so it is dimensionless. Therefore, $t^x$ must itself have the same dimensions as $t^{n−1}$. Therefore, $x$ has to be $n−1$.

# Easy Case
使用簡單的例子來驗證你猜的答案。但這招好像不用特別講一般人應該都會用。課程裡舉的例子非專業人士也不太會碰到。是以以下只以一個範例填塞內容。

範例：

For the Gaussian integral $$\displaystyle  \int _{-\infty }^{\infty } e^{-\alpha x^2}\, dx,$$use the three easy-cases tests$-\alpha \to 0$, $\alpha=1$, and $\alpha \to \infty$-to evaluate the following candidates for the integral. In particular, state how many of the three tests each candidate passes.

- $\sqrt {\pi }/\alpha$
- $1+(\sqrt \pi -1)/\alpha$
- $1/\alpha ^2+(\sqrt \pi -1)/\alpha$


# Lumping
概算，這章主要有下列內容，以下僅給出關鍵字。如果想知道詳細內容，恭喜您，您有足夠動機來修這門課了。

- 日常生活中的估計（商學院朋友可能比較有興趣）
- 估計積分
	- 1/e heuristic
	- Full width at half maximum(FWHM)
- 估計微分
	- secant approximation
	- Significant-change approximation
- 估計微分方程


估計尿布市場的大小
https://www.youtube.com/watch?v=kNLFin3Ph6U#t=166

is it a coinsident that $g\approx \pi ^2\, {\rm m/s}^2$
https://www.youtube.com/watch?v=J3jwB8BPrvM

# Pictorial Proofs
圖像思考，本章有很多範例如，圓面積、算幾不等式、任意兩點等分三角形面積。不過我覺得可以 take away 的內容是 $log(1+x)$ 的估算方式視覺化、及後面提及的rewriting trick。

一般人大概知道由泰勒展開式展開
$$\displaystyle  \ln (1+x)= x - {x^2\over 2} + {x^3\over 3} - \cdots .$$
（課程內容裡有前兩項的視覺化。）但是用這招去估計$ln{2}$ 會發生問題，因為此時$x=1$ ，高次項的$x$ 並不收斂。
  
Is there an analogous argument to help estimate $ln2$? (roughly 0.693)
Because 2 is also $(4/3)/(2/3)$, an analogous rewriting of $ln2$ is $$ln2=ln(4/3)−ln(2/3)$$. Each fraction has the form $1+x$ with $x=\pm 1/3$. Because $x$ is small, one term of the logarithm series might provide reasonable accuracy. Let's therefore use $ln(1+x)\approx x$ to approximate the two logarithms: $ln2≈1/3−(−1/3)=2/3$. This estimate is accurate to within 5%!

# Taking out the Big Part
這章大概是整門課最酷的地方
## Back-of-the-envelope estimates: One, few, or 10
把所有的數字都分成 1, few , 和 10。其中$(\text{few})^2=10$ 

範例：估計$3600 \times 4.4\times 10^{4}\times 32$
3600大概是一個few三個10
4.4大概是一個few
32大概是一個few和一個10
算式總共有三個few和八個10，結合few之後剩下一個few和九個10$$3600 \times 4.4\times 10^{4}\times 32 \approx 3\times 10^9$$

## Linear Approximation

$$\displaystyle  (1+z)^ n\approx \left\{  \begin{array}{cl} 1+nz&  (z\ll 1\hbox{ and }nz\ll 1) \\ e^{nz}&  (z\ll 1~ \hbox{and }~ nz~ \hbox{ unrestricted}) \end{array} \right.$$

依此邏輯$nz$ 很小時也可用$$ e^{nz}\approx 1+nz$$
## Rapid mental division

$$\displaystyle  {1\over 13} \approx {1\over 10} - 30\%  = 0.07$$

$${1 \over 13} =  {1 \over 13}\times {8 \over 8}={8 \over 104}\approx 0.08$$

even better, 
$${1 \over 13} ={8 \over 104}\approx 0.08 -4\% =0.0768$$

Alternatively,
$${1 \over 13} =  {1 \over 13}\times {77 \over 77}={77 \over 1001}\approx 0.077$$

even better, 
$${1 \over 13} = {77 \over 1001}\approx 0.077- 0.1\%=0.076923$$
computer calculation is 0.076923

## 72法則
https://www.youtube.com/watch?v=gAQZDW9wYv4
請自行google

## 細菌突變
> 私心覺得是最精彩的習題

Q:系統中每回合會有5%細菌會突變，請問140回合後有多少細菌還未突變
A:
即估算
$$(1-5\%)^{140}$$
但 $-5\%\times 140=-7$ 太大以至於不能用 $(1+z)^ n\approx 1+nz$ 而必須使用$e^{nz}$
$$(1-5\%)^{140}\approx e^{-7}$$

一組好用的規則是 $$e^{2.3} \approx 10, ln(10)\approx 2.3$$ 
這可以輕易的在指數與對數中取出10的成份
是以$$ e^{-7}\approx e^{-6.9}\approx 10^{-3}=0.001$$
更甚者
$$ e^{-0.1}\approx 1-0.1\approx 0.9$$
$$e^{-7}\approx 0.0009$$
再過份一點
$$n\ln (1+z)\approx n\left(z - {z^2\over 2}\right)$$
所以
$$(1+z)^ n \approx e^{nz} \times e^{-nz^2/2}.$$
$$e^{-nz^2/2}=e^{-7\times0.05/2}=e^{-7/40}\approx1-{7\over 40}=-1.75\%$$
結合前面的結果
$$0.0009-1.75\% =0.0007425$$
電腦計算的答案是0.00076086

## Successive approximation
對一個深度未知的水井投擲石頭，4秒後聽到水聲，問高如何？
嚴格的作法是解：
$$\displaystyle  T = \underbrace{\sqrt {2h\over g}}_{\rm rock} \, + \underbrace{h\over c_{\rm s}}_{\rm sound}$$
但音速有$340m/s$ 使得後項非常小，可以先算前面的部份。
把$g$用$10m/s^2$帶入，得到高約$80m$。$80m$的井聲音約飛了$80m/340m/s \approx .24s$，接著再用剩下的$4-0.24=3.76$再去估一次高度。得到$70.87m$ (嚴格值$71.56m$)
(課程這個答案應該也有敲計算機，用人估算的話我是估$75m$)

使用Successive approximation的理由不外乎是拿精度換速度，但更深刻的意義在於如果今天有個微小的模型修正，但使得模型會沒有公式解，這種作法可以幫助得到概算的答案。

例題：

$$10s^2 + 4000s + 16 = 0$$

- Find $s$ in the easy case $s\approx 0$. Don't use a calculator!
- Find $s$ in the easy case $|s|\gg 1$. Don't use a calculator!
- Improve the preceding estimate (the case $|s|\gg 1$) using one round of successive approximation. You shouldn't need a calculator.

$s\approx 0 \Rightarrow  4000s + 16 = 0\Rightarrow s\approx -0.004$
$|s|\gg 1 \Rightarrow 10s^2 + 4000s =0 \Rightarrow s\approx -400$
其實上面在做的事情就是
$$10s^2 + 4000s + 16=0 \Rightarrow 10s+4000+16/s\approx 10s+4000$$
所以重新整理後
$$10s+4000+16/s=0  \Rightarrow s=-400-1.6/s$$
用
$$s'=-400-1.6/s =-400-1.6/(-400)=399.996$$

# Analogy
課開始時我很期待這章的內容，但真正到了這章卻沒有很驚豔的感覺。

唯一比較有趣的是微分運算子$D$ 的討論。例如：$e^D$ 可以把函數往左移。把微分放在指數上是什麼意義呢？關鍵就在於建立微分運算子與一般數字的類比。

次方的類比：$D^2f$ 就是對函數$f$ 微分兩次
多項式的類比：$(D^2+D+I)f$，就是微分兩次的$f$ 加上微分一次的，再加上都沒微分的。
$e^D$的類比：利用泰勒展開式展開$e$
$$\displaystyle  e^ D = 1 + D + {1\over 2}D^2 + {1\over 6}D^3 + \cdots $$即可以多項式去理解。


> Written with [StackEdit](https://stackedit.io/).