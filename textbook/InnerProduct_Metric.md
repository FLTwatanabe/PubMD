> $V$を$F = \mathbb{R}$ or $\mathbb{C}$上のベクトル空間とする.また$V$には内積の条件うち$\langle a, a \rangle = 0 \Rightarrow a \in \mathbf{0}$ (零ベクトル)のみを満たさない内積に似た関数$\langle \cdot, \cdot \rangle : V \times V \rightarrow F$が定まっているとする.この時,関数$d: V \times V \rightarrow [0, \infty )$を$d(x,y) := \sqrt{ \langle x - y, x - y \rangle}$と定義すると,$d$は擬距離(pseudometric)である.
また、内積が定まっている場合は$d$は距離(metric)である.(証明略)

Proof.  
1. $d(x,y) \ge 0$  
正値性(positive-definiteness)より自明.  
1'. $d(x,x) = 0$  
正値性(positive-definiteness)より$x$が零ベクトルならば,$\langle x, x \rangle = 0$であるので$d(x,x) = \sqrt{\langle x -x, x-x \rangle}= 0$  
2. $d(x, y) = d(y,x)$  
線型性(Linearity)より
$d(x,y) = \sqrt{\langle x -y, x-y \rangle} = \sqrt{\langle y -x, y-x \rangle} = d(y,x)$  
3. $d(x, z) \le d(x,y) + d(y,z)$  
内積の条件から$\langle a, a \rangle = 0 \Leftrightarrow a = 0$を除いた,性質を用いて三角不等式$\| a + b \| \le \| a\| + \|b\|$が示される.ただし、$\|\cdot\| = \sqrt{\langle \cdot,\cdot \rangle}$.
詳細は「基礎講義　線形代数学 二木昭人 p137-140」を参照.
ゆえに,三角不等式に$a = x - y, b = y-z$を代入すると,
$$
\begin{align*}
		&\| a + b \| \le \| a\| + \|b\|\\
	\Leftrightarrow & \| x - z \|  \le \|x - y \| + \| y - z\|\\
	\Leftrightarrow & d(x,z) \le d(x,y) + d(y,z)
\end{align*}
$$

---
`Bitbucket>Akira Tanaka > MacDown>Files>InnerProduct_Metric.md Mon Feb 5 01:07:16 2018`
