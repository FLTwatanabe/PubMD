[TOC]
### 有限集合の濃度は一意に定まることの証明の補足

基本的には[ここ](http://www.math.is.tohoku.ac.jp/~obata/student/subject/file/2018-6_yugen.pdf)のサイトを参照(日本語)

[有限集合の濃度は一意に定まることの証明](http://www.math.is.tohoku.ac.jp/~obata/student/subject/file/2018-6_yugen.pdf)

>  補題6.1 
> $$
> \mathbb{N}_0 := \{0,1,…\},
> \begin{align}
> [n] := 
> \begin{cases}
> 	\{1,2,..,n\}  &n \ge 1\\
> 	\phi  &n = 0
> \end{cases}
> \end{align}
> $$

> 
>
> (1) もし単射 $f : [n] \to [m]$が存在すれば$n \le m$
>
> (2)もし全射$f : [n] \to [m]$が存在すれば$n \ge m$
>
> (3)もし全単射$f : [n] \to [m]$が存在すれば$n = m$

Proof.(2)

$m=0,1$の場合は自明なので$m \ge 2$の時を示す.$n$に関する帰納法を用いる.

[1] $n=0$の時

$m \gt 0$と仮定すると$f$の全射性より$[n]$は空集合ではないが,これは$n=0$に矛盾.ゆえに$m=0$

[2] $n \ge 1$の時成立すると仮定して$n+1$でも成立することを示す.

全射$f:[m+1] \to [m]$が成立しているとする

[2-1] $i \in [n]$が存在して$f(i) = f(n+1)$を満たす場合

$f_{\restriction_{[n]}} : [n] \to [m]$は全射.ゆえに$m \le n \lt n+1$より成立

[2-2]任意の$i \in [n]$に対して$f(i) \ne f(n+1)$の場合

$h:[m] \to [m]$を
$$
\begin{align*}
	h(k) = \begin{cases}
			m & k = f(n+1)\\
			f(n+1) & k= m \\
			k & その他
		\end{cases}
\end{align*}
$$
と定義すると$h$は全単射となるので$h \circ f : [n+1] \to [m]$は全射

このとき$h \circ f(n+1) = m$であり[2-2]の仮定より任意の$i \in [n]$に対して$h \circ f (i) \ne h \circ f(n+1) = m$よって $(h \circ f)_{\restriction_{[n]}} : [n] \to [m-1]$は全射.

よって帰納法の仮定より$n \ge m-1$



### 濃度を表す関数は測度である

> $\Omega$を空でない集合とし$P(\Omega)$を$\Omega$の部分集合族とする.
>
> $P(\Omega)$上に要素数を表す関数$\mu (A) = | A | \quad (A \in P(\Omega))$を定義すると$\mu(A)$は測度となる 

(Proof)

まず,以下のように定義する$A \in P(\Omega)$が無限集合の場合は$\mu(A) = \infin$と定義し,任意の$a \in \mathbb{R}\cup \{\infin \} $に対して$a + \infin = \infin$とする.

(i),(ii) 任意の$A \in P(\Omega)$に対して$\mu(A) \in [1, \infin]$,  $\mu(\empty) = 0$は自明

(iii) 互いに素な任意の$A_1, A_2,\dots \in P(\Omega)$に対して
$$
\mu\left( \bigcup_{n \ge 1} A_n\right) = \sum_{n=1}^\infin\mu(A_n)
$$
を示せば十分

(i) $A_m$が無限集合である$m \ge 1$が存在する場合

一般的に有限集合の任意の部分集合は有限集合であるので,$\bigcup_{n \ge 1} A_n$は無限集合であり(左辺)$=\infin$.一方,右辺においては$n \ge m$を満たす任意の$n$において$\sum_{k=1}^n \mu(A_k) = \infin$となるのでOK

(ii) 任意の$A_n$が有限集合かつ,ある$N \in \{1,2,\dots\}$が存在して,任意の$n > N$に対して$A_n = \empty$の場合
$$
 \mu \left( \bigcup_{n\ge1} A_n \right)
 = \mu \left( \bigcup_{n=1}^N A_n \right)
 = \sum_{n=1}^N \mu(A_n)
$$
となる.(互いに素な有限集合の和集合の要素数はそれぞれの集合の要素数の和になっているいることは集合の要素数の定義から示される 証明略)



任意の$n > N$に対して$A_n = \empty$であるので$\mu(A_n) = 0$であることに注意すると右辺と一致する.

(iii)任意の$A_n$が有限集合かつ,任意の$k \in \{1,2,\dots\}$に対してある$n > k$が存在して$|A_n| >0$を満たすとき.

$\bigcup_{k \ge 1} A_k$は無限集合であるので(証明は下記),(左辺)$= \infin$となる.一方で任意の$\ell \in \{1,2,\dots \}$に対して自然数$N$が存在して$\sum_{n=1}^N \mu (A_n) > 0$となるので(証明は下記), (右辺)$=\infty$となりOK



> $k \in \{1,2,..\}$に対して$A_k$は有限集合で互いに素とする.
>
> また,任意の$k  \in \{1,2,..\}$に対して$|A_n| > 0$かつ$n > k$を満たす自然数$n$が存在するとする.
>
> (途中から$A_k$が全て空集合とはならない)
>
> この時,$\bigcup_{k \ge 1} A_k$は無限集合(有限集合)ではない.

(Proof)

$ \bigcup_{k \ge 1} A_k$を有限集合だと仮定し,要素数を$n$とする.$n$より大きい自然数$n'$を1つ固定する.このとき$ \left| \bigcup_{k=1}^N A_k \right| > n'$を満たす自然数$N$が存在する(証明は下記).有限集合の有限個の和集合は有限集合であるので$\bigcup_{k=1}^N A_k $は有限集合であり$\{1,2,..,n'\}$から$\bigcup_{k=1}^N A_k $への単射が存在する.また,$\bigcup_{k=1}^N A_k \subset \bigcup_{k \ge 1} A_k  $であるので$\{1,2,\dots n'\}$から$\bigcup_{k \ge 1} A_k$への単射が存在する.よって,$n' \le n$であるがこれは$n'$が$n$より大きい自然数であることに矛盾.よって$\bigcup_{k \ge 1} A_k$は無限集合である.



> $\{A_k\}_{k=0}^N$:有限集合
>
> $k \in \{1,2,..\}$に対して$A_k$は有限集合で互いに素とする.
>
> また,任意の$k  \in \{1,2,..\}$に対して$|A_n| > 0$かつ$n > k$を満たす自然数$n$が存在するとする.
>
> (途中から$A_k$が全て空集合とはならない)
>
> この時,任意の$\ell \in \{1,2,...\}$に対して$| \bigcup_{k=1}^N A_k| > \ell$を満たす自然数$N$が存在する

(Proof.)

任意の$\ell \in \{1,2,\dots\}$に対して$N_{\ell}$を以下のように定めると$| \bigcup_{k=1}^{N_{\ell}} A_k| \ge \ell$を満たす.

[1]仮想的に$N_0 = 0$と定める

[2]$N_{\ell}$が定まっている時に$N_{\ell + 1}$を以下のように定める

$A_k$の定義より$N_\ell$に対して$| A_{N_{\ell +1}} | >0$かつ$N_{\ell + 1} > N_\ell$を満たす$N_{\ell + 1}$が存在するので,このうち一つを$N_{\ell + 1}$とする

(補足証明)

任意の$\ell \in \{1,2,\dots\}$に対して$| \bigcup_{k=1}^{N_{\ell}} A_k| \ge \ell$を満たすことを証明する

$\ell = 0$のとき$| A_{N_1} | > 0$であるので$  |\bigcup_{k=1}^{N_1} A_k| = \sum_{k=1}^{N_1} |A_k| \ge A_{N_1} > 0$より成立.

$\ell$のとき成立すると仮定すると,仮定より$A_{N_{\ell + 1}} > 0$かつ$N_{\ell + 1} > N_{\ell}$を満たす$N_{\ell + 1}$が存在するので,


$$
\left| \bigcup_{k=1}^{N_{\ell + 1}} A_k \right|
= \sum_{k=1}^{N_{\ell + 1}} A_k
\ge |A_{N_{\ell +1}}| + \sum_{k=1}^{N_{\ell}} |A_k| \ge \ell + 1
$$
となり成立.



### 濃度に対応する関数(counting measure)は元集合が可算集合なら$\sigma$-finite

> $\Omega$を空でない可算集合とし$P(\Omega)$を$\Omega$の部分集合族とする.
>
> この時$P(\Omega)$上のcounting measure $\mu$は$\sigma$-finiteである

(Proof)

$\Omega$は可算無限集合より自然数の部分集合$N$との間に全単射$f: N \to \Omega$が存在する.

よって$\{\{f(n)\}\}_{n \in N}$という単集合からなる$\Omega$の部分集合族を考えると$f$の全単射性から明らかに加算であり$\bigcup_{n \in N} \{ f(n) \} = \Omega$となる

$$
\lim_{n \to \infty} \mu(A_{n_0} \setminus A_n)
= \lim_{n \to \infty} \left(
		 \mu(A_{n_0}) - \mu(A_n)
	\right)
= \mu(A_{n_0}) -  \lim_{n \to \infty} \mu(A_n)
$$

