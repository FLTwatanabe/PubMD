[TOC]



## 概要

> ***About this book***
>
> - Abstract 
>
>   測度論と確率について丁寧に書いてある.証明もきちんと載っているが、簡単な部分は省略してあるので自分で補足する必要あり.
>
> - Available 
>
>   Kyushu Universiy ebookss
>
> - Authors 
>
>   Krishna B. AthreyaSoumendra N. Lahiri
>
> - Print ISBN 
>
>   978-0-387-32903-1
>
> - Online ISBN 
>
>   978-0-387-35434-7

## 補足

### 1.Measure

#### 1.1 Classes of sets

##### Example 1.1.6

> $\sigma \langle \mathcal{O}_2 \rangle = \langle \mathcal{O}_4 \rangle = \mathcal{B}(\mathbb{R})^k$

$\mathcal{G}$を$\mathcal{O}_4$を含む$\sigma$-algebraだとする.
このとき$\mathbb{R}^k$の任意の開集合$A \subset \mathbb{R}^k$をとると,Problem1.9より$\{B_n\}_{n \ge 1} \subset \mathcal{O}_3$が存在して,$A = \bigcup_{n \ge 1} B_n$とできる.
ここで,
$B_n = (a_1^n, b_1^n) \times \cdots \times (a_k^n, b_k^n)$
とおくと,
$$
\begin{align*}
	B_n &= (a_1^n, b_1^n) \times \cdots \times (a_k^n, b_k^n)\\
		&= \bigcup_{i \ge 1} (-\infty, b_1^n) \times \cdots \times (-\infty, b_k^n) \setminus
			(-\infty, a_1^n + \frac{1}{i}) \times \cdots \times (-\infty, a_k^n + \frac{1}{i})\\
		&= \bigcup_{i \ge 1} C_n \setminus C_n^i
\end{align*}
$$
ゆえに,$A = \bigcup_{n \ge 1} \bigcup_{i \ge 1} C_n \cap (C_n^i)^c$.
$C_n, C_n^i \in \mathcal{O}_4$であり,$\mathcal{G}$は$\mathcal{O}_4$を含む$\sigma$-algebraなので$A \in \mathcal{G}$.
ゆえに,$\mathcal{G}$は$\mathbb{R}^k$の任意の開集合を含む$\sigma$-algebraであるので以下が成立
$$
\mathcal{B}(\mathbb{R}^k) \supset 
	\sigma \langle \mathcal{O}_2 \rangle \supset 
	\sigma \langle \mathcal{O}_4 \rangle =
	\bigcap_{\mathcal{G}: \mathcal{O}_4 \subset \mathcal{G}, \sigma - field}
		\mathcal{G} \supset
	\mathcal{B}(\mathbb{R}^k)
$$

##### Theorem 1.1.2 (The $\pi\text{-}\lambda$ theorem)
>$\lambda_1(\mathcal{C})$ is $\lambda$-system

Proof.
(i)$\Omega \in \lambda_1(C)$は明らか.
(ii) $A, A' \in \lambda_1(\mathcal{C}), A \subset A' \Rightarrow A' \setminus A \in \lambda_1(\mathcal{C})$を示す.
$A, A' \in \lambda_1(C)$より$A, A' \in \lambda \langle \mathcal{C} \rangle$であり, $ A \subset A' $であることを踏まえると,$A' \setminus A \in \lambda\langle \mathcal{C} \rangle$.
また,任意の$B \in \mathcal{C}$をとったとき,$(A' \setminus A) \cap B = (A' \cap B) \setminus (A \cap B) \in \lambda\langle \mathcal{C} \rangle$
(iii)$A_n \in \lambda_1(\mathcal{C}), A_n \subset A_{n+1} \Rightarrow \bigcup_n A_n \in \lambda_1(\mathcal{C})$
任意の$B \in \mathcal{C}$をとったとき,$(\bigcup_n A_n) \cap B = \bigcup_n (A_n \cap B) \in \lambda \langle \mathcal{C} \rangle$($A_n \cap B \subset A_{n+1} \cap B$)

>by the previous step $\mathcal{C} \subset \lambda_1(\mathcal{C})$

Proof.
任意に$A \in \mathcal{C}$をとる.また任意に$A' \in \lambda \langle \mathcal{C} \rangle = \lambda_1(\mathcal{C})$をとると,$\lambda_1(C)$の定義より,$A' \cap A \in \lambda \langle \mathcal{C} \rangle$.また$A \in \mathcal{C}$より,$A \in \lambda \langle \mathcal{C} \rangle$は明らか.



#### 1.2 Measures

##### Example 1.2.1 (The counting measure)

[濃度を表す関数は測度であるを参照](./set)

##### Example 1.2.2 (Discrete Probability Measure)

> Let $w_1, w_2,\dots \in \Omega$ and $p_1, p_2,\dots \in [0,1]$ be such that $\sum_{i=1}^{\infty} p_i = 1$. Define for any $A \subset \Omega$
> $$
> P(A) = \sum_{i=1}^{\infty} p_i I_A (w_i),
> $$
> Then $P(\cdot)$ is a measure and finite.

Proof.

まず,$P(A)$が定義できることを示す.任意の自然数$n \ge 1$について,$0 \le  \sum_{i=1}^n p_i I_A (w_i) \le \sum_{i=1}^n p_i \le \sum_{i=1}^{\infty} p_i = 1$であるので$ \sum_{i=1}^n p_i I_A (w_i)$は単調増加で上に有界なので上限に収束する.よって,$P(A)$はwell-definedでfiniteつまり$P(\Omega) < \infty$である.

次に$P(\cdot)$がmeasureであることを示す.(i)先の議論より任意の$A \subset \Omega$に対して,$P(A) \in [0,1] \subset [0, \infty]$.(ii)$P(\empty) = 0$は定義より明らか.(iii)互いに素な集合$A_1, A_2,\dots \in \Omega$に対して,
$$
\begin{align*}
	P\left(
		\bigcup_{n \ge 1} A_n
		\right)
	&= \sum_{i=1}^{\infty} p_i I_{\left( \cup_{n \ge1} A_i\right)} (w_i)\\
  &= \sum_{i=1}^{\infty} p_i
  	\left(
  		\sum_{n=1}^{\infty} I_{A_n} (w_i) 
  	\right) \quad \because A_n \text{ is disjoint}\\
  &= \sum_{i=1}^{\infty} \sum_{n=1}^{\infty} 
  	\left(
  		p_i I_{A_n} (w_i)
  	\right) \quad \because \text{収束列の定数倍は収束列}\\
  &= \sum_{n=1}^{\infty} \sum_{i=1}^{\infty} 
  	\left(
  		p_i I_{A_n} (w_i)
  	\right) \quad \because \text{無限和の交換(下記に説明)}\\
  &= \lim_{n \to \infty} \sum_{i=1}^{n} P(A_n)\\
  &= \lim_{n \to \infty} P 
  	\left(
  		\bigcup_{i = 1}^n A_i
  	\right) \quad \because 証明は下記
\end{align*}
$$
[収束列の定数倍は収束列の補足](./calculus_compl)

無限和の交換について.上式の式変形から,任意の$i \in \mathbb{N}_{\ge 1}$に対して $\sum_{n=1}^{\infty} | p_i I_{A_n} (w_i) | = \sum_{n=1}^{\infty}  p_i I_{A_n} (w_i) $は$p_i$か0に収束するので,
$$
\sum_{i=1}^{k} \sum_{n=1}^{\infty} | p_i I_{A_n} (w_i) | 
\le \sum_{i=1}^{k} p_i 
\le \sum_{i=1}^{\infty} p_i 
\le 1
$$
が任意の自然数$k$に対して成立.ゆえに,左辺の極限も1以下.よって,[無限和の交換](./calculus_compl)を用いることができる.

最後の式変形を示すためには,互いに素な集合$A, B \in \Omega$に対して
$$
P(A) + P(B) = P(A \cup B)
$$
を示せば十分.$A, B$が互いに素であることに注意すると,
$$
\begin{align*}
	P(A \cup B) 
	&= \sum_{i=1}^{\infty} p_i I_{A \cup B} (w_i)\\
	&= \sum_{i=1}^{\infty} p_i (I_A(w_i) + I_B(w_i))\\
	&= \sum_{i=1}^{\infty} p_i I_A (w_i) + \sum_{i=1}^{\infty} p_i I_B (w_i) \quad \because 収束する数列の和は収束する\\
	&= P(A) + P(B)
\end{align*}
$$


##### Prop 1.2.2 (iii)の補足 

> Let $\mu$ be a measure on an algebra $\mathcal{F}$, and let $A,B, A_1, \dots ,A_k \in \mathcal{F}$, $1 \le k < \infty$. Then,
>
> (iii) (Inclusion-exclusion formula) If $\mu (A_i) < \infty$ for all $i = 1, \dots ,k$, then
> $$
> \begin{align*}
> \mu (A_1 \cup \dots \cup A_k)
> &= \sum_{i=1}^k \mu (A_i) 
> 	- \sum_{1 \le i < j \le k} \mu(A_i \cap A_j) + \cdots
>   + (-1)^{k-1} \mu (A_1 \cap \cdots \cap A_k)\\
> &= \sum_{j=1}^k 
> 	(-1)^{j-1} \sum_{1 \le i_1 < i_2 < \cdots< i_j \le k}
> 		\mu(A_{i_1} \cap A_{i_2} \cdots \cap A_{i_j})
> \end{align*}
> $$

(Proof.)

Prop 1.2.2 (ii)の証明より,$\mu(A) < \infty$と$\mu(B) < \infty$のどちらかが成立しているならば,
$$
\mu(A \cup B) = \mu(A) + \mu(B) - \mu(A \cap B)
$$
が成立することが示された.

ここで(iii)が$k=n$の時,成立していると仮定して$k=n+1$の時も成立することを示す.仮定より$\mu(A_{n+1}) < \infty$であることに注意すると
$$
\begin{align*}
	\mu\left( \bigcup_{i=1}^{n+1} A_i \right)
	=& \mu \left( \bigcup_{i=1}^{n} A_i \right)
		+ \mu(A_{n+1})
		- \mu \left( \bigcup_{i=1}^{n} A_i \cap A_{n+1} \right)\\
  =& \sum_{j=1}^n
    (-1)^{j-1} \sum_{1 \le i_1 < i_2 < \cdots< i_j \le n}
      \mu(A_{i_1} \cap A_{i_2} \cdots \cap A_{i_j})
      + \mu (A_{n+1})\\
   &(-1) \sum_{j=2}^{n+1}
    (-1)^{j-2} \sum_{1 \le i_1 < i_2 < \cdots< i_{j-1} \le n}
      \mu(A_{i_1} \cap \cdots \cap A_{i_{j-1}} \cap A_{n+1})\\
  =& \sum_{j=1}^{n+1}
    (-1)^{j-1} \sum_{1 \le i_1 < i_2 < \cdots< i_j \le n+1}
      \mu(A_{i_1} \cap A_{i_2} \cdots \cap A_{i_j})
\end{align*}
$$



##### Prop1.2.3 

> Let $\mu$ be a *measure* on an *algebra* $\mathcal{F}$
>
> (i) (Monotone continuity from above)
>
> Let $\{A_n\}_{n \ge 1}$ be a sequence of sets in $\mathcal{F}$ such that $A_{n+1} \subset A_n$ for all $n \ge 1$ and $A \equiv \bigcap_{n \ge 1} A_n \in \mathcal{F}$. Also, let $\mu(A_{n_0}) < \infty$ for some $n_0 \in \mathbb{N}$. Then, 
> $$
> \lim_{n \to \infty} \mu(A_n) = \mu(A)
> $$

Proof(i)

$C_n \equiv A_{n_0} \setminus A_n$と定義すると,$\{C_n\}_{n \ge 1}$は単調増加であり,
$$
\bigcup_{n \ge 1} C_n 
=  A_{n_0} \setminus \bigcap_{n \ge 1} A_n
= A_{n_0} \setminus A \in  \mathcal{F}
$$
であるので,Prop1.2.1$(iii)'_b$より,$\mu(A_{n_0} \setminus A) = \lim_{n \to \infty} \mu(A_{n_0} \setminus A_n) $

$A \subset A_{n_0}$であるので,$\mu(A_{n_0} \setminus A) = \mu(A_{n_0}) - \mu(A)$.また,十分大きな$n$に対して$A_n \subset A_{n_0}$であるので,
$$
\lim_{n \to \infty} \mu(A_{n_0} \setminus A_n)
= \lim_{n \to \infty} \left(
		 \mu(A_{n_0}) - \mu(A_n)
	\right)
= \mu(A_{n_0}) -  \lim_{n \to \infty} \mu(A_n)
$$


##### Prop 1.2.3( Monotone continuity from above)

> Let $\mu$ be a measure on an algebra $\tilde{\mathcal{F}}$
> (Monotone continuity from below)
> Let $\{A_n\}_{n \ge 1} \subset \tilde{\mathcal{F}}$ satisfies $A_n \subset A_{n+1}, A \equiv \bigcup_{n \ge1} A_n \in \tilde{\mathcal{F}}, \mu(A_n) \lt \infty \quad(n \in \mathbb{N})$ . Then,
> $$\lim_{n \rightarrow \infty} \mu(A_n) = A$$

Proof.
Let $\{B_n\}_{n \ge 1}$ be $B_n = A_n \setminus A_{n-1} (n \in \mathbb{N}, A_0 = \emptyset)$.Then, $\{B_n\}_{n \ge 1} \subset \tilde{\mathcal{F}}$ are disjoint and $\bigcup_{n \ge 1} = A$.Therefore,
$$
\begin{align*}
	\mu(A) &= \mu \big(
				\bigcup_{n \ge 1} B_n
			\big)\\
		&= \sum_{n \ge 1} \mu(B_n)\\
		&= \sum_{n \ge 1} \mu(A_{n} \setminus A_{n-1})\\
		&= \sum_{n \ge 1} \mu(A_{n}) - \mu(A_{n-1})\\
		&= \lim_{n \rightarrow \infty} \mu(A_n)
\end{align*}
$$



#### The extension theorems and Lebesgue-Stieltjes measures

##### Definition 1.3.1 (*semialgebra*)

>  Let $\Omega$ be a noempty set and let $\mathcal{P} (\Omega)$ be the power set of $\Omega$. A class $\mathcal{C} \subset \mathcal{P} (\Omega)$ is called a *semialgebra* if (i) $A, B \in \mathcal{C} \Rightarrow A \cap B \in \mathcal{C}$ and (ii) for any $A \in \mathcal{C}$, there exists $\{B_i\}_{i=1}^k \subset \mathcal{C}$, for some $1 \le k < \infty$, such that $B_i \cap B_j = \empty$ for $i \ne j$, and $A^c = \bigcup_{i=1}^k B_i$





##### Example 1.3.2(区間はsemialgebra)

> $\Omega = \mathbb{R}, \mathcal{C} \equiv \{I : I \text{ is an interval}\}$. An interval $I$ in $\mathbb{R}$ is a set in $\mathbb{R}$ such that $a, b \in I, a < b \Rightarrow (a,b) \subset I$.
>
> Then, $\mathcal{C}$ is semialgebra, that is if (i) $A,B \in \mathcal{C} \Rightarrow A \cap B \in \mathcal{C}$ and (ii) for any $A \in \mathcal{C}$, there exist sets $B_1, B_2, \dots , B_k \in \mathcal{C}$, for some $1 \le k < \infty$, such that $B_i \cap B_j = \empty$ for $i \ne j$, and $A^c = \bigcup_{i=1}^k B_i$



(Proof)

(i) $A,B \in \mathcal{C} \Rightarrow A \cap B \in \mathcal{C}$は定義通りに示せるので略.

(ii) for any $A \in \mathcal{C}$, there exis sets $B_1, B_2, \dots , B_k \in \mathcal{C}$, for some $1 \le k < \infty$, such that $B_i \cap B_j = \empty$ for $i \ne j$, and $A^c = \bigcup_{i=1}^k B_i$.

を示す.

$I$をintervalとする.$I = \empty$と時は$I^c = \mathbb{R}$となり$\mathbb{R}$はIntervalであるのでOK.

$I$が単集合の時も自明であるので,以後$I$は空集合でも単集合でもないとする

$A \equiv \{x \in \mathbb{R} \mid (-\infty, x] \subset I^c\}$と定義する.

Intervalである$C$を以下のように定める.(​後に$D$を定めて,$I^c = C \cup D$であることを示す)

(1)$A = \empty$の場合

$I$は下に有界でない.この時は$C = \empty$と定める.

(2)$A$が上に有界でない場合

$A$の定義より$A = \mathbb{R}$となるので$I^c = \mathbb{R}$.これは$I = \empty$となり矛盾するので,(2)は起こり得ない

(3)$A$が上に有界である場合

上限が存在するので$c$とおく. 

(3-1) $c \in I$ならば$C = (-\infty,  c)$と定義する.

(3-2)$c \notin I$ならば$C = (-\infty,  c]$と定義する

(1)~(3)のいずれの場合でも$A$の定義から

- 「$C$と$I$は互いに素」である.

- また$I$が上に有界ならば$b = \sup I$,有界でない場合は$b = \infty$と定めると$(-\infty, b) \subset C \sqcup I$である(*1)

(*1)の証明

(1)すなわち$A = \empty$の場合は$I$は下に有界でないことを考慮すると簡単に示せる.

(3)の場合

$x \in (-\infty, b)$を任意にとる.$x$より小さい実数で$I$に含まれるものが存在するなら,$b$とIntervalの定義より$x \in I$であることがわかる.そうでない場合, すなわち$(-\infty, x] \subset I^c$の時を考える.

$c$の定義より$x \le c$である.この時(3-1),(3-2)のいずれの場合でも$x \in C$であることが示せるのでOK.



同様にして$ \{x \in \mathbb{R} \mid [x, \infty) \subset I^c\}$についても考えると以下のようなInterval  $D$を作成することが出来る.

- $D$と$I$は互いに素
- $I$が下に有界ならば$a = \inf I$,有界でない場合は$a = -\infty$と定めると$(a, \infty) \subset 
  D \sqcup I$



$I$が単集合でないことを考慮すると$(-\infty, b) \cup  (a, \infty) = \mathbb{R}$であるので,
$$
\mathbb{R}
= (-\infty, b) \cup  (a, \infty)
\subset C \cup D \cup I
$$
最後に$C$と$D$が互いに素であることを背理法を用いて示す.

$C$と$D$が互いに素でない場合は$A \equiv \{x \in \mathbb{R} \mid (-\infty, x] \subset I^c\}$が上に有界(上限を$c$とおく)かつ$\{ x \in \mathbb{R} \mid [x, \infty) \subset I^c \}$が下に有界(下限を$d$とおく)で,
$$
(-\infty, c] \cap [d,\infty) \ne \empty
$$
である時に限る.

一方で$x \in (-\infty, c] \and d < x$を満たす$x$が存在するならば$c,d$の定義より$I^c = \mathbb{R}$となり$I$が空集合となってしまうので矛盾.$x < c \and d = x$を満たす$x$が存在する場合も同様の理由で矛盾.よって,$(-\infty, c] \cap [d,\infty) \ne \empty$を満たすならば$c =d$の時に限るがその場合$I$が単集合になり矛盾



##### Example 1.3.3

> $\Omega = \mathbb{R}^k, \mathcal{C} \equiv \{I_1 \times I_2 \times \, \times I_k:I_j \text{ is an interval in } \mathbb{R}  \text{ for } 1 \le j \le k \}$
>
> Then, $\mathcal{C}$ is a $semialgebra$

(Proof)

(i) Example 1.3.2で$\mathbb{R}$上の区間は*semialgebra​*であることが分かったので,*semialgebraの*定義(i)を用いれば,$C_1, C_2 \in \mathcal{C} \Rightarrow C_1 \cap C_2 \in \mathcal{C}$は容易に示せる.

(ii)任意に$\prod_{j=1}^k I_j \in \mathcal{C}$をとり,$I_j^0 \equiv I_j, I_j^1 \equiv I_j^c$と定義する.この時
$$
\left( \prod_{j=1}^k I_j \right)^c 
= \bigsqcup_{x \in \{0,1\}^k, x \ne {\bf 0}} \prod_{j=1}^k I_j^{x_j}
$$
が成立する(証明略)

また$\mathbb{R}$上の区間は*semialgebra*であるので,任意の区間$I_j$に対して$I_j^c = \bigsqcup_{i=1}^{m_j} B_j^i$となるような区間$B_j^i$が存在する.よって,$B_j^0 \equiv = I_j^0 = I_j$,任意の自然数$n$に対して$[n] = \{0,1,\dots,n\}$と定義すると
$$
I_j^{x_j} 
= \bigsqcup_{
		y_j \in [m_j]\\
		y_j = 0 (\text{if } x_j = 0)\\
		y_j \ne 0 (\text{if } x_j = 1)
	} B_j^{y_j}
$$
が成立.よって,,


$$
\prod_{j=1}^k I_j^{x_j}
 = \bigsqcup_{
 		y \in \prod_{j=1}^k [m_j]\\
 		y_j = 0 (\forall j: x_j = 0)\\
 		y_j \ne 0 (\forall j: x_j = 1)
 	}
 	\prod_{j=1}^k B_j^{y_j}
$$
であるので,(ii)が示せた.



##### Proposition 1.3.1

 > Let $\mu$ be a *measure* on a *semialgebra* $\mathcal{C}$. Let $\mathcal{A(\mathcal{C})}$ be the smallest algebra generated by $\mathcal{C}$. For each $A \in \mathcal{A}$, set
 > $$
 > \bar{\mu} (A) = \sum_{i=1}^k \mu (B_i).
 > $$
 > if the set $A$ has teh representation $A = \bigcup_{i=1}^k B_i$, for some $B_1, \dots , B_k \in \mathcal{C}, k < \infty$ with $B_i \cap B_j = \empty$ for $i \ne j$. Then
 >
 > (i) $\overline{\mu}$ is independent of the representation of $A$ as $A = \bigcup_{i=1}^k B_i$
 > Note:
 > For any $A \in \mathcal{A}$, there exist disjoint $\{B_i\}_{i=1}^K \subset \mathcal{C} \quad (K \in \mathbb{N})$ such that $A = \bigcup_{i=1}^K B_i$
 >
 > (iii) $\bar{\mu}$ is *countably additive* on $\mathcal{A}$, *i.e.*, if $A_n \in \mathcal{A}$ for all $n \ge 1$, $A_i \cap A_j = \empty$ for all $i=j$, and $\bigcup_{n \ge 1} A_n \in \mathcal{A}$, then
 > $$
 > \bar{\mu}
 > 	\left(
 > 		\bigcup_{n \ge 1} A_n
 > 	\right)
 > = \sum_{n=1}^{\infty} \bar{\mu} (A_n)
 > $$

(Proof)

始めに$\mathcal{C}$に誘導される最小の*algebra*を具体的に構成する.

> Let $\mathcal{C}$ be a *semialgebra* on no-empty set $\Omega$. Then, we define
> $$
> \mathcal{A} \equiv 
> 	\left\{ 
> 		\bigsqcup_{i=1}^k A_i \mid A_i \in \mathcal{C}, 0 \le k < \infty
> 	\right\}
> $$
> Then, $\mathcal{A}$ is algebra 

(c')$\bigsqcup_{i=1}^k A_i, \bigsqcup_{j=1}^{\ell} B_j \in \mathcal{A}$とすると
$$
\left( \bigsqcup_{i=1}^k A_i \right) \cap \left( \bigsqcup_{j=1}^{\ell} B_j \right)
=  \bigsqcup_{
    \substack{i= \{1,2,\dots,k\}\\
      j= \{1,2,\dots,\ell\}
    }
  } \big( A_i \cap B_j \big)
\in \mathcal{A}
$$
(b)
$$
\left( \bigsqcup_{i=1}^k A_i \right)^c
= \bigcap_{i=1}^k A_i^c
$$
であり,*semialgebra*の定義より$A_i^c \in \mathcal{A}$であるので(c')より(右辺)$\in \mathcal{A}$

(c)$\empty \in \mathcal{A}$であるので,(b)より$\Omega = \empty^c \in \mathcal{A}$

次に以下を示す.

> Let $\mathcal{A} (\mathcal{C})$ be the smallest algebra generated by $\mathcal{C}$. Then $\mathcal{A} (\mathcal{C}) = \mathcal{A}$

 $\mathcal{A}$は$\mathcal{C}$を含む*algebra*であることから,$\mathcal{A} \subset \mathcal{A} (\mathcal{C})$を示せば十分だが,これは$ \mathcal{A} (\mathcal{C})$が*algebra*であることから自明



Proof.(i)
$A$が$A = \bigcup_{i=1}^K A_i, \bigcup_{j=1}^L B_j \quad (A_i \in \mathcal{C}, A_i \cap A_{i'} = \emptyset \text{    for  } i \ne i', B_j \text{  に対しても同様}) $と2通りで表せられたとすると,
$$
\begin{align*}
	\overline{\mu}\Big(
		\bigcup_{i=1}^K A_i
	\Big) 
	&= \overline{\mu}\Bigg(
		\Big( \bigcup_{i=1}^K A_i \Big) \cap A
		\Bigg)\\
	&= \overline{\mu}\Bigg(
			\Big( \bigcup_{i=1}^K A_i \Big) \cap 
			\Big( \bigcup_{j=1}^L B_j \Big)
		\Bigg)\\
	&= \overline{\mu}\Big(
		\bigcup_{
			\substack{i= \{1,2,\dots,K\}\\
				j= \{1,2,\dots,L\}
			}
		} \big( A_i \cap B_j \big)
	\Big) \\
	&= \bigcup_{
			\substack{i= \{1,2,\dots,K\}\\
				j= \{1,2,\dots,L\}
			}
		} \mu(A_i \cap B_j)\\
\end{align*}
$$
である.同様に
$$
\begin{align*}
	\overline{\mu}\Big(
		\bigcup_{j=1}^L B_j
	\Big) 
	&= \bigcup_{
			\substack{i= \{1,2,\dots,K\}\\
				j= \{1,2,\dots,L\}
			}
		} \mu(A_i \cap B_j)\\
\end{align*}
$$
であるので,題意は示せた.

Proof (iii)

$A_n$の定義より,任意の$n \ge 1$に対して,$A_n = \bigcup_{j=1}^{k_n} B_{nj}$, $B_{nj} \in \mathcal{C}$, $\{B_{nj}\}_{j=1}^{k_n}$が互いに素になるような$\{B_{nj}\}_{j=1}^{k_n}$が存在する.また,$\bigcup_{n \ge 1} A_n \in \mathcal{A}$であるので,互いに素な$\{B_i\}_{i=1}^k \subset \mathcal{C}$で$\bigcup_{n \ge 1} A_n = \bigcup_{i=1}^k B_i$を満たす$B_i$が存在する.
$$
B_i 
= B_i \cap \bigcup_{n \ge 1} A_n
= \bigcup_{n \ge 1} B_i \cap A_n
= \bigcup_{n \ge 1} \bigcup_{j=1}^{k_n} B_i \cap B_{nj}
$$
であり,$\mu$はは*semi-algebra*$\mathcal{C}$上の*measure*であるので,
$$
\mu(B_i) = \sum_{n \ge 1} \sum_{j=1}^{k_n} \mu(B_i \cap B_{nj})
$$
よって,
$$
A_n 
= A_n \cap \bigcup_{i=1}^k B_i 
= \bigcup_{i=1}^k \bigcup_{j=1}^{k_n} B_i \cap B_{nj}
$$


であるので,
$$
\begin{align*}
	\bar{\mu}\left(
		\bigcup_{n \ge 1} A_n
	\right)
	&= \sum_{i=1}^k \mu (B_i)\\
  &= \sum_{i=1}^k \sum_{n \ge 1}
  	\left(
  		\sum_{j=1}^{k_n} \mu (B_i \cap B_j)
  	\right)\\
   &= \sum_{n \ge 1} 
  	\left(
  		\sum_{i = 1}^k \sum_{j=1}^{k_n} 
  			\mu (B_i \cap B_j)
  	\right)\\
  &= \sum_{n \ge 1} \bar{\mu}(A_n)

\end{align*}
$$


3つ目の等号が成立することを示す.

(case1) 任意の$i \in \{1, \dots ,k \}$について$\mu(B_i) < \infty$の場合.

[リンク先>有限和と無限和の交換](calculus_compl)より成立

(case2)$i_0 \in \{1, \dots ,k \}$が存在して$\mu(B_{i_0}) = \infty$を満たす場合
$$
\bar{\mu} \left(
	\bigcup_{n \ge 1} A_n
\right) 
= \sum_{n = 1}^{\infty} \bar{\mu}(A_n) 
= \infty
$$
であることを示す.

(ii)で示した*finitely additive*性より
$$
A, B \in \mathcal{A}, A \subset B 
\Rightarrow
\bar{\mu}(B) = \bar{\mu}(A) + \bar{\mu}(B \setminus A) \ge \bar{\mu}(A)
$$
が成立することに注意すると,
$$
\bar{\mu} \left(
	\bigcup_{n \ge 1} A_n
\right)
= \bar{\mu} \left(
	\bigcup_{i = 1}^k B_i
\right) 
\ge \bar{\mu}(B_{i_0}) = \infty
$$
また,$\bigcup_{n \ge 1} A_n = \bigcup_{i=1}^k B_i$であるので,$\bigcup_{\ell = 1}^m A_{\ell}  \supset B_{i_0}$を満たす$m$が存在する.

$\mathcal{A}$は*algebra*であるので,$\bigcup_{\ell = 1}^m A_{\ell} \in \mathcal{A}$であり(ii)で示した*finitely additive*性を用いると,
$$
\sum_{\ell = 1}^m \bar{\mu}(A_\ell)
=\bar{\mu} \left(
	\bigcup_{\ell = 1}^m A_{\ell}
\right) 
\ge \bar{\mu}(B_{i_0})
= \infty
$$
であるので,
$$
\sum_{n = 1}^{\infty} \bar{\mu}(A_n) 
= \infty
$$


##### Definition 1.3.3

> $$
> \begin{align*}
> \mu^* &= \overline{\mu} \text{ on } \mathcal{A}\\
> \mu^* &= \mu \text{ on } \mathcal{C}
> \end{align*}
> $$

Prrof.$\mu^* = \overline{\mu} \text{ on } \mathcal{A}$

Fix $A \in \mathcal{A}$.
任意に$\{A_n\}_{n \ge 1} \subset \mathcal{C}$ with $A \subset \bigcup_{n \ge 1} A_n$をとる.
We define $\{B_n\}_{n \ge 1}$ as
$$
\begin{align*}
	B_n \equiv \Bigg(
			A_n \setminus \bigcup_{k=1}^{n-1}  A_k
		\Bigg) \cap A
		\quad (
			B_1 \equiv A_1, n \ge 1
		)
\end{align*}
$$
Then, $\{B_n\}_{n \ge 1}$ is disjoint,  $B_n \subset A_n$.
Since algebra is closed under complementation and finite intersection, $\{B_n\}_{n \ge 1} \subset \mathcal{A}$.
It also satisfies $A = A \cap \bigcup_{n \ge 1} A_n = \bigcup_{n \ge 1} B_n$.
Therefore
$$
\begin{align*}
	\overline{\mu}(A) &= \overline{\mu}\Big(
				\bigcup_{n \ge 1} B_n
			\Big)\\
		&= \sum_{n \ge 1} \overline{\mu}(B_n) 
			\quad(\because \overline{\mu} \text{ is a measure on an algebra } \mathcal{A})\\
		&\le \sum_{n \ge 1} \overline{\mu}(A_n)
			\quad (\because B_n \subset A_n) \\
		&= \sum_{n \ge 1} \mu (A_n)
\end{align*}
$$
右辺の下限をとると$\overline{\mu}(A) \le \mu^{*}(A)$が示せる.
Next we show $\overline{\mu}(A) \ge \mu^{*}(A)$.
Since, $A \in \mathcal{A}$, 
$$
A = \bigsqcup_{i=1}^N C_n 
	\quad (N \in \mathbb{N}, \{C_n\}_{i=1}^N \subset \mathcal{C})
$$
Since $A \subset \bigsqcup_{i=1}^N C_n $, 
$$
\begin{align*}
	\mu^*(A) &\le \sum_{i=1}^N \mu(C_n)\\
		&= \overline{\mu}(A)
\end{align*}
$$
Proof.$\mu^* = \mu \text{ on } \mathcal{C}$
Since $\mathcal{C} \subset \mathcal{A}$, $\mu^* = \overline{\mu} \text{ on } \mathcal{A}$, and $\overline{\mu} = \mu \text{ on } \mathcal{C}$.
Therefore,$\mu^* = \mu \text{ on } \mathcal{C}$

##### 1.3.2 Lebesgue-Stieltjes measures on $\mathbb{R}$  $\mu_F$ is a measure on $\mathcal{C}$

(a)$\mu_F(\emptyset) = \mu_F([a,a]) = F(a+) - F(a+) = 0$は明らか.
(b)$\mu_F(\cdot) \in [0, \infty]$を示す.
(1) 
$$
-\infty \le a \lt b \lt \infty \Rightarrow F(b+) - F(a+) \ge 0
$$
を示す.

(1-1)$-\infty \lt a$のとき.
背理法で示す.

$F(b+) \lt F(a+)$であるとする.
$\epsilon = \frac{F(b+) - F(a+)}{2} (\gt 0)$とおく.
このとき$F(a+)$の定義より$\delta_1 \gt 0$が存在して,
$$
0 \lt x - a \lt \delta_1 \Rightarrow |F(a+) - F(x)| \lt \epsilon /2
$$
である.ここで,$x = a + \min\{ \delta_1/2, b-a\}$とすると$0 \lt x - a \lt \delta_1$であり,$x \le b$である.
また$F(b+)$の定義より$\delta_2 \gt 0$が存在して
$$
0 \lt y - b \lt \delta_1 \Rightarrow |F(b+) - F(y)| \lt \epsilon /2
$$
が成立.ここで$0 \lt y - b \lt \delta_1$を満たす.$y$を任意にとると,
$$
\begin{align*}
	F(a+) \lt F(x) + \epsilon /2
	\le F(y) + \epsilon /2
	\le F(b+) + \epsilon
	= \frac{F(a+)+F(b+)}{2}
\end{align*}
$$
ゆえに矛盾.同様に(1-2)$a = -\infty$
(2)
$$
-\infty \le a \lt \infty \Rightarrow
F(\infty) - F(a+) \ge 0
$$
も示せるので(b)は示せる.

(c)

$\{C_n\}_{n \ge 1} \subset \mathcal{C}$がdisjointで$\bigcup_{n\ge1} C_n \in \mathcal{C}$だとすると,$\bigsqcup_{n \ge 1} C_n$は次のいずれかで表される.
$$
\bigsqcup_{n \ge 1} (a_n, b_n] \cup (b, \infty)\\
\bigsqcup_{n \ge 1} (a_n, b_n]
$$
ただし,$\bigsqcup_{n \ge 1} (a_n, b_n] = (a,b]$と表される.
[Problem 1.22](#Problem 1.22)(b),(c)において$F(\cdot)$を$G(\cdot)$に置き換えても成立するので,
の証明は下記.

$$
\begin{align*}
	G(b) - G(a) = \sum_{n \ge 1} G(b_i) - G(a_i)
\end{align*}
$$
が成立.
ゆえに,
$$
\begin{align*}
	\mu_F((a,b]) &= \mu_G((a,b])\\
		&= G(b+) - G(a+)\\
		&= G(b) - G(a)\\
		&= \sum_{n \ge 1} G(b_i) - G(a_i)\\
		&= \sum_{n \ge 1} G(b_i+) - G(a_i+)\\
		&= \sum_{n \ge 1} \mu_G((a_i, b_i])\\
		&= \sum_{n \ge 1} \mu_F((a_i, b_i])\\
\end{align*}
$$

$$
\begin{align*}
	\mu_F((a,\infty)) &= \mu_G((a,\infty))\\
		&= G(\infty) - G(a+)\\
		&= G(\infty) - G(b+) + G(b) - G(a)\\
		&= \mu_G((b, \infty)) + G(b) - G(a)\\
		&= \mu_F((b, \infty)) + \sum_{n \ge 1} \mu_F((a_i, b_i])\\
\end{align*}
$$

##### Definition 1.3.7

>  $\sigma \langle \mathcal{C} \rangle = \mathcal{B}(\mathbb{R})$

Proof.
$(a,b] = (a, \infty) \cap (b, \infty)^c$であり,$(a, \infty), (b, \infty)$は$\mathbb{R}$の開集合なので$(a, \infty), (b, \infty) \in \mathcal{B}(\mathbb{R})$.また,$\mathcal{B}(\mathbb{R})$は$\sigma$-fieldより,$[a,b] \in \mathcal{B}(\mathbb{R})$.また,$(a,\infty) \in \mathcal{B}(\mathbb{R})$は明らかなので,$\mathcal{C} \subset \mathcal{B}(\mathbb{R})$.よって,$\sigma \langle \mathcal{C} \rangle$の定義より$\sigma \langle \mathcal{C} \rangle \subset \mathcal{B}(\mathbb{R})$.
$$
\begin{align*}
	 \mathcal{C} 
		 &\equiv  \{(a,b] : -\infty \le a \le b \lt \infty\} \cup \{(a,\infty) : -\infty \le a  \lt \infty\}\\
	 &= \mathcal{O}_1 \cup \mathcal{O}_2
\end{align*}
$$
とすると,P12 Example 1.1.6より
$$
\sigma \langle \mathcal{C} \rangle 
	=\sigma \langle \mathcal{\mathcal{O}_1 \cup \mathcal{O}_2} \rangle 
	\supset \sigma \langle \mathcal{\mathcal{O}_2} \rangle
	= \mathcal{B}(\mathbb{R})
$$

>  $\mu_F^*$ is also a measure on $(\mathbb{R}, \mathcal{B}((\mathbb{R}))$

Proof.
From Th1.3.3, $\mathcal{C} \subset \mathcal{M}$, and Th1.3.2 says $\mathcal{M}$ is $\sigma$-algebra. Therefore, $\sigma \langle \mathcal{C} \rangle \subset \mathcal{M}$. Moreover, Th1.3.2 says $\mu^*$ restricted to $\mathcal{M}$ is measure, so $\mu^*$ is a measure on $\sigma \langle \mathcal{C} \rangle = \mathcal{B}((\mathbb{R}))$

>  $\mu_F= \mu$ on $\mathcal{C}$

>$F(x+) = F(x)$

Proof.
when $x \gt 0$
$\{(0, x + 1/n]\}_{n \ge 1}$ is monotonically decreasing and $\bigcup_{n \ge 1}(0, x+ 1/n] = (0,x] \in \mathcal{B}(\mathbb{R})$. By [Prop 1.2.3](#Prop 1.2.3( Monotone continuity from above)) Monotone continuity from below,
$$
	F(x+) = \lim_{n \rightarrow \infty} \mu\big(
					(0, x+ 1/n]
				\big)
			=\mu \big(
					(0,x]
				\big)
			= F(x)
$$
when $x = 0$
For the same reason, $F(0+) = F(0)$

when $x \lt 0$
We take $N \in \mathbb{N}$ with $x + 1/N \lt 0$. Then,
$\{(x+ \frac{1}{N+n},0]\}_{n \ge 1}$ is monotonically increasing. By Prop 1.2.3, 
https://www.evernote.com/l/AVpuGUWq52RL-4ph_75OgA0Tb25t0p7vuWI
$$
F(x+) 
= \lim_{n \rightarrow \infty} \mu\big(
		(x+ \frac{1}{N+n}, 0]
	\big) 
= \mu \big(
		(x,0]
	\big)
= F(x)
$$

> $\mu_F= \mu$ on $\mathcal{C}$

Proof.
$\mu_F\big((a,b]\big) = F(b+) - F(a+) = F(b) - F(a)$
$$
\begin{align*}
	F(b) - F(a) = \begin{cases}
			\mu \big((0,b]\big) - \mu \big((0,a]\big)
				\quad (0 \le a \le b)\\
			\mu \big((0,b]\big) + \mu \big((a,0]\big)
				\quad (a \le 0 \le b)\\
			\mu \big((b,0]\big) + \mu \big((a,0]\big)
				\quad (a \le b \le 0)\\
		\end{cases}
\end{align*}
$$
If we care $[0,b) = (0, a] \cup (a, b] \quad ( 0 \le a \le b)$,
$F(b) - F(a) = \mu \big((a,b]\big)$
Simiraly,
$$
\begin{align*}
	\mu_F\big((a, \infty]\big) &= F(\infty) - F(a+)\\
		&= F(\infty) - F(a)\\
		&= \mu \big((a, \infty]\big)
\end{align*}
$$

#### 1.5 Problem

##### 1.9 $\mathbb{R}^k$の任意の開集合は加算個の開区間(open interval)で表される 

> $\mathbb{R}^k$の任意の開集合は加算個の開区間(open interval)で表される.

Proof of (a),(b) 

任意に$\mathbb{R}^k$の開集合$U$をとる.
$U_{\mathbb{Q}} \equiv \{x \in U \mid xの全ての成分は有理数\}$
$U_{\mathbb{R}} \equiv  U \setminus U_{\mathbb{Q}}$
と定義する.
また写像$f: U_{\mathbb{R}} \rightarrow U_{\mathbb{Q}}$を次のように定義する.
$x \in U_{\mathbb{R}}$をとると$U$が開集合であることから$\epsilon_x \gt 0$が存在し
$(x_1 - \epsilon_x, x_1 + \epsilon_x)\times \cdots \times (x_k - \epsilon_x, x_k + \epsilon_x) \subset U$
とできる.
また,実数の稠密性から以下を満たす有理数$y$がとれる.
$$
y \in (x_1 - \epsilon_x / 3, x_1 + \epsilon_x / 3) \times \cdots \times (x_k - \epsilon_x / 3, x_k + \epsilon_x / 3)
$$
これを1つ固定し,$f(x) = y$とする.
このとき,
$$
I_{f,x} = (y_1 - 2\epsilon_x / 3, y_1 + \epsilon_x / 3) \times \cdots \times (y_k - \epsilon_x / 3, y_k + \epsilon_x / 3)
$$
とすると,$y \in I_{f,x} \in U$を満たす.
また,任意の$y \in U_{\mathbb{Q}}$に対して$U$が開集合であることから以下を満たす開区間$I_y$がとれる.
$$
	I_y = (y_1 - \epsilon_y, y_1 + \epsilon_y) \times \cdots \times (y_k - \epsilon_y, y_k + \epsilon_y) \subset U
$$
ここで$\epsilon_y \gt 0$である.
このとき以下が成立(証明略)
$$
	U = \bigcup_{y \in U_{\mathbb{Q}}}
		\Big(
			\bigcup_{x \in f^{-1}(y)} I_{f,x}
		\Big)
		\cup I_y
$$
ここで,$I_{f,x}, I_y$は$y$を中心とした開区間の和集合であるので,$\Big(\bigcup_{x \in f^{-1}(y)} I_{f,x}\Big)\cup I_y$も$y$を中心とした開区間の和集合である.また,加算集合の有限個の積集合も加算集合であるので$U_{\mathbb{Q}}$も加算集合.ゆえに,$U$は開区間の加算個の和集合でかける.(特に$\epsilon$を有理数でとると,開区間の端点が有理数であるようにできる)



> $\mathbb{R}$上の開集合は高々加算個の互いに素なの開区間の和集合で表される.

Proof of (c)
有界な開集合$U \in \mathbb{R}$について考える.(有界でない場合も同様)
任意の$x \in U$に対して,$a_x, b_x, I_x$を以下のように定める.
$a_x \equiv  \inf \{y \in \mathbb{R} \mid  [y,x] \subset U \}$
$b_x \equiv  \sup \{y \in \mathbb{R} \mid  [x,y] \subset U \}$
定義より$a_x \lt x \lt b_x$であるので$I_x \equiv (a_x, b_x)$を定義できる.
このとき定義より$I_x \subset U$が成立することに注意すると,
$$
\bigcup_{x \in U} I_x = U
$$
また,
> $I_x \ne I_y \Rightarrow I_x \cap I_y = \emptyset$である.

対偶を示す.
$I_x \cap I_y \ne \emptyset$とする.
任意の$z \in I_x \cap I_y$に対して$I$の定義より$I_x = I_z$となる.
実際,$a_x \lt a_z$とすると,$a_x \lt a \lt a_z$を満たす$a$に対して,$a_x$の定義より,$[a,x] \subset U$であり, $\min\{x,z\} \gt b \gt b_x$を満たす$b$に対して,$b_x$の定義より,$[x,b] \subset U$であるので$[a,z) \subset [a,b] \subset U$.これは$a_z$の定義に矛盾.ゆえに.$a_x = a_z$.同様に$b_x = b_z$も示せるので$I_x=I_z$が成立.
同様の議論技$I_y$にも成立するので$I_y = I_z = I_x$
よって対偶が示された.
また$U$上に以下の同値類を定める.
$x, y \in U$に対して$x \sim y \Leftrightarrow I_x = I_y$
このとき,
$$
	\bigcup_{x \in U / \sim} I_x = U
$$
である.
また,$x, y \in U / \sim (x \ne y)$に対して$I_x \cap I_y = \emptyset$であるので,
を$x \in U / \sim$に対して$f(x)$を区間$I_x$に含まれる有理数と定めた写像$f: U / \sim \rightarrow \mathbb{Q}$は単射である.ゆえに,$U / \sim$は高々加算個であり,また$I_x$は互いに素な開区間である.



##### Problem 1.18

> Let $\Omega \equiv \mathbb{N}, \mathcal{F} = \mathcal{P}(\Omega)$, and $A_n = \{j : j \in \mathbb{N}, j \ge n\}, n \in \mathbb{N}$. Let $\mu$ be the counting measure on $(\Omega, \mathcal{F})$. Verify that $\lim_{n \to \infty} \mu(A_n) \ne \mu \left( \bigcap_{n \ge 1} A_n \right)$ 

(Proof)

[$\mu$がmeasureになる証明>濃度を表す関数は測度である](./set)

任意の自然数$n$に対して,$A_n$は無限集合$\mathbb{N}$から有限集合($n$より小さい自然数)を除いたものなので,無限集合である.ゆえに任意の$n$に対して$\mu(A_n) = \infty$であるので,(左辺)$= \infty$.

一方,$\bigcap_{n \ge 1} A_n = \empty$であるので右辺$=0$.

このことから,Prop1.2.3(i)の仮定である自然数$n_0$に対して$\mu(A_{n_0}) < \infty$ を満たさないと,$\lim_{n \to \infty} \mu(A_n) \ne \mu \left( \bigcap_{n \ge 1} A_n \right)$ となる場合がある.(Prop1.2.3(i)の結果を満たさない)



##### Problem 1.19

> Let $\Omega$ be a nonempty set and let $\mathcal{C} \subset \mathcal{P}(\Omega)$ be a semialgebra. Let
$$
\mathcal{A}( \mathcal{C}) \equiv \{ A : A = \bigcup_{i=1}^K B_i: B_i \in \mathcal{C}, i= 1,2,\dots,k, k \in \mathbb{N}\}
$$
(a) Show that $\mathcal{A}(\mathcal{C})$ is the smallest algebra containing $\mathcal{C}$
(b) Show $\sigma \langle \mathcal{C} \rangle = \sigma \langle \mathcal{A}(\mathcal{C}) \rangle$
(c)追加 For any $A \in \mathcal{A(\mathcal{C})}$, there exist disjoint $\{B_i\}_{i=1}^K \subset \mathcal{C} \quad (K \in \mathbb{N})$ such that $A = \bigcup_{i=1}^K B_i$

Proof
$\mathcal{C} \ne \emptyset$と仮定する.(これは必要)
このとき, $\emptyset \in \mathcal{C}$であることは容易に示せる(証明略)

(a) algebraであることを示す.
(a1) $\Omega \in \mathcal{A}(\mathcal{C})$
(c1) $A, B \in \mathcal{A}(\mathcal{C}) \Rightarrow A \cap B \in \mathcal{A}(\mathcal{C})$
は容易に示せる. (証明略)
(b1) $A \in \mathcal{A}(\mathcal{C}) \Rightarrow A^c$
を示す.
任意に$A \in \mathcal{A}(\mathcal{C})$ととると仮定より,$A = \bigcup_{i=1}^K B_i \quad (B_i \in \mathcal{C})$と表せる.
また,$\mathcal{C}$がsemialgebraであることから,
$$
B_i^c = \bigcup_{j=1}^{N_i} C_j^i 
	\quad (C_j^i \in \mathcal{C}, C_j^i \cap C_{j'}^i = \emptyset \text{   for  } j \ne j')
$$
と表せる.ゆえに,$C_j^i \cap C_{j'}^i = \emptyset \text{   for  } j \ne j'$であることを注意すると,
$$
\begin{align*}
	A^c &= \Big( \bigcup_{i=1}^K B_i  \Big)^c\\
		&= \bigcap_{i=1}^K B^c_i\\
		&= \bigcap_{i=1}^K \big( \bigcup_{j=1}^{N_i} C_j^i \big)\\
		&= (C^1_1 \cap C^1_2 \cap \cdots \cap C^1_{N_1}) \cap 
			\Bigg( 
				\bigcap_{i=2}^K \Big(
					\bigcup_{j=1}^{N_i} C^i_j
				\Big) 
			\Bigg)\\
		&= \bigcup_{l_1 = 1}^{N_1} \Bigg(
			C_l^1 \cap \Big(
				\bigcap_{i=2}^K \bigcup_{j=1}^{N_i} C_j^i
				\Big)
			\Bigg)\\
		&= \bigcup_{l_1=1}^{N_1} \bigcap_{i=2}^{K} \bigcup_{j=1}^{N_i} 
			C_{l_1}^1 \cap C_j^i
\end{align*}
$$
上の式において,
$\bigcap_{i=2}^{K} \bigcup_{j=1}^{N_i}  C_{l_1}^1 \cap C_j^i$に対して同様の処理を再帰的に繰り返すことによって以下が得られる.
$$
\begin{align*}
	A^c &=  \bigcup_{l_1=1}^{N_1} \bigcup_{l_2=1}^{N_2} \Bigg(
					\bigcap_{i=3}^K \bigcup_{j=1}^{N_i} C_{l_1}^1 \cap C_{l_2}^2 \cap C_j^i
			\Bigg)\\
		&= \bigcup_{l_1=1}^{N_1} \bigcup_{l_2=1}^{N_2} \cdots \bigcup_{l_K=1}^{N_K}
		C_{l_1}^1 \cap C_{l_2}^2 \cap \cdots C_{l_K}^K \in \mathcal{A}(\mathcal{C})
\end{align*}
$$
ゆえに$\mathcal{A}(\mathcal{C})$はalgebraである.

(a) 最小性を示す.
$\mathcal{F}$を$\mathcal{C}$を含むalgebraだとする.
もし$B_1, B_2, \dots, B_K \in \mathcal{C} \quad (K \in \mathbb{N})$が存在して,$\bigcup_{i=1}^K B_i \notin \mathcal{F}$だとする.
仮定より$\mathcal{F}$は$\mathcal{C}$を含むので,$B_i \in \mathcal{F}$である.
また,$ \mathcal{F}$はalgebraであり有限和に閉じているので,
$\bigcup_{i=1}^K B_i \in \mathcal{F}$が成立する.ゆえに矛盾.
よって,
$$
\begin{align*}
	\mathcal{A}( \mathcal{C}) 
		\equiv \{ A : A = \bigcup_{i=1}^K B_i: B_i\in \mathcal{C}, i= 1,2,\dots,k, k \in \mathbb{N}\}
		\subset \mathcal{F}
\end{align*}
$$
であるので,$\mathcal{A}( \mathcal{C}) $は$\mathcal{C}$を含む最小のalgebraである.

Proof.(b)
$\mathcal{C} \subset \mathcal{A} (\mathcal{C})$より,$\sigma\langle \mathcal{C} \rangle \subset \sigma \langle \mathcal{A} (\mathcal{C}) \rangle$は自明.逆を示す.
$ \mathcal{A} (\mathcal{C}) \subset \sigma \langle \mathcal{C} \rangle$が示されれば,$\sigma \langle \mathcal{A} (\mathcal{C}) \rangle$は$\mathcal{A} (\mathcal{C})$を含む最小の$\sigma$-algebraであるので,$\sigma \langle \mathcal{A} (\mathcal{C}) \rangle \subset \sigma\langle \mathcal{C} \rangle$が示される.よって以下では,
$ \mathcal{A} (\mathcal{C}) \subset \sigma \langle \mathcal{C} \rangle$を示す.
任意に$\bigcup_{i=1}^k B_i\in \mathcal{A}(\mathcal{C}), B_i \in \mathcal{C}$をとる.
定義より$\mathcal{C} \subset \sigma \langle \mathcal{C} \rangle$であり,$\sigma \langle \mathcal{C} \rangle$有限和に閉じているので$\bigcup_{i=1}^k B_i \in \sigma \langle \mathcal{C} \rangle$である.よって題意は示せた.

Proof.(c)
For any $A \in \mathcal{A}$,  there exist $\{A_n\}_{n=1}^N \subset \mathcal{C} \quad N \in \mathbb{N}$ such that $A = \bigcup_{n=1}^N A_n$.
We define ${B_n}$ as $B_n = A_n \setminus \bigcup_{k=1}^{n-1} A_k \quad (1 \le n \le N, A_0 = \emptyset)$.
Then $A = \bigcup_{n=1}^N A_n = \bigcup_{n=1}^N B_n$ and $\{B_n\}_{n = 1}^N$ is disjoint.

Moreover,
$$
\begin{align*}
	B_n &=  A_n \setminus \bigcup_{k=1}^{n-1} A_k\\
		&= A_n \cap \Big(
				\bigcup_{k=1}^{n-1} A_k
			\Big)^c\\
		&= A_n \cap \Big(
				\bigcap_{k=1}^{n-1} A_k^c
			\Big)\\
\end{align*}
$$
For any $1 \le k \le N$, since $A_k \in \mathcal{C}$, there exist disjoint subsets $\{A_{kl}\}_{l=1}^{N_k} \subset \mathcal{C} \quad (N_k \in \mathbb{N})$ such that $A_k^c = \bigcup_{l=1}^{N_k} A_{kl}$.
Therefore
$$
\begin{align*}
	\bigcap_{k=1}^{n-1} A_k^c &= \bigcap_{k=1}^{n-1} \bigg(
			\bigcup_{l=1}^{N_k} A_{kl}
		\bigg)\\
	&= \bigg(
			\bigcup_{l=1_1}^{N_1} A_{1l_1}
		\bigg) \cap 
		\Bigg(
				\bigcap_{k=2}^{n-1} \bigg(
					\bigcup_{l=1}^{N_k} A_{kl}
				\bigg)
		\Bigg)\\
	&= \bigcup_{l=1_1}^{N_1} \bigcap_{k=2}^{n-1} \bigcup_{l=1}^{N_k} 
		(A_{1l_1} \cap A_{kl})\\
	&= \cdots\\
	&= \bigcup_{l=1_1}^{N_1}  \bigcup_{l_2=1}^{N_2} \cdots \bigcup_{l_{n-1}=1}^{N_{n-1}} 
		(A_{1l_1} \cap A_{1l_2} \dots \cap A_{1l_{n-1}} )\\
\end{align*}
$$
Therefore 
$$
\begin{align*}
	B_n &= A_n \cap \Big(
				\bigcap_{k=1}^{n-1} A_k^c
			\Big)\\
	&= A_n \cap \Bigg(
			\bigcup_{l=1_1}^{N_1}  \bigcup_{l_2=1}^{N_2} \cdots \bigcup_{l_{n-1}=1}^{N_{n-1}} 
				(A_{1l_1} \cap A_{1l_2} \dots \cap A_{1l_{n-1}} )
		\Bigg)\\
	&= \bigcup_{l=1_1}^{N_1}  \bigcup_{l_2=1}^{N_2} \cdots \bigcup_{l_{n-1}=1}^{N_{n-1}} 
				(A_n \cap A_{1l_1} \cap A_{1l_2} \dots \cap A_{1l_{n-1}} )
\end{align*}
$$
Therefore, $B_n \quad (1 \le n \le N)$ is represented as disjoint finite union of $\mathcal{C}$. Since $A = \bigcup_{n=1}^N B_n$ and $\{B_n\}_{n=1}^N$ is disjoint, A is represented as finite disjoint union of $\mathcal{C}$.



##### Problem 1.20

> Given a measure $\mu$ on a *semialgebra* $\mathcal{C}$, let the *outer measure* induced by $\mu$ be $\mu^*$
>
> Then, the following statements satisfy 
> $$
> \begin{align}
> 	\mu^* (\empty) &= 0 \label{eq:OutMeas1} \\
> 	A \subset B &\Rightarrow \mu^*(A) \le \mu^*(B) \label{eq:OutMeas2}\\
> 	\mu^*\left(
> 			\bigcup_{n \ge 1} A_n 
> 		\right) 
> 	&\le \sum_{i=1}^{\infty} \mu^*(A_n) 
> 		\quad \forall\{A_n\}_{n \ge 1} \subset \mathcal{P}(\Omega)
> 		\label{eq:OutMeas3}
> \end{align}
> $$

任意の$A \in \mathcal{P}(\Omega)$ ($A \subset \mathbb{R}$)に対して
$$
\mathcal{G}_A 
\equiv \left\{
	\sum_{n=1}^{\infty} \mu(A_n) 
		\mid \{A_n\}_{n \ge 1} \subset \mathcal{C}, 
			A \subset \bigcup_{n \ge 1} A_n
\right\}
$$
と定義すると$\mu^*(A)  = \inf \mathcal{G}_A$と表せる.

(Proof $\ref{eq:OutMeas1}$)

$\mathcal{G}_A$の定義より任意の$x \in \mathcal{G} \subset \mathbb{R} \cup \{\infty\}$に対して$0 \le x$.よって,下限の定義より$0 \le \inf \mathcal{G}_A$.また$\empty \subset \empty \in \mathcal{C}, \mu(\empty) =0$であるのでinfの定義より$\inf \mathcal{G}_A \le \mu(\empty) = 0$

(Proof $\ref{eq:OutMeas2}$)

$A \subset B$とすると$\mathcal{G}_A \subset \mathcal{G}_B \subset \mathbb{R} \cup \{\infty\}$.よって,$\inf \mathcal{G}_A \le \inf \mathcal{G}_B \Leftrightarrow \mu^*(A) \le \mu^*(B)$

(Proof $\ref{eq:OutMeas3}$)

Case1:任意の自然数$n$に対して$\mu^*(A_n) < \infty$が成立している場合

$\epsilon > 0$を任意に固定する.下限の定義より任意の自然数$n$に対して
$$
\sum_{j=1}^{\infty} \mu(A_{nj}) < \mu^*(A_n) + \frac{\epsilon}{2^n}
$$
を満たす$\{A_{nj}\}_{j\ge1} \subset \mathcal{C}, A_n \subset \bigcup_{j \ge 1} A_{nj}$が存在する.

(Case1-1) $\sum_{n \ge 1} \mu^*(A_n) < \infty$の場合

M-testより$\sum_{n \ge 1} \sum_{j \ge 1} \mu(A_{nj})$は収束する.よって
$$
\sum_{n \ge 1} \sum_{j \ge 1} \mu(A_{nj}) 
\le \sum_{n \ge 1} \mu^*(A_n) + \epsilon
$$
が成立する.$\bigcup_{n \ge 1} A_n \subset \bigcup_{n \ge 1} \bigcup_{j \ge 1} A_{nj}$であることに注意すると,
$$
\begin{align}
	\mu^* \left( 
			\bigcup_{n \ge 1} A_n
		\right)
	&\le \mu^* \left(
			\bigcup_{n \ge 1} \bigcup_{j \ge1} A_{nj}
  	\right) \quad \because (\ref{eq:OutMeas2})\\
  &\le \sum_{n \ge 1} \sum_{j \ge 1} \mu(A_{nj}) 
  	\quad \because \mu^*の定義, 加算集合の直積は加算集合\\
  &\le \sum_{n \ge 1} \mu^*(A_n) + \epsilon
\end{align}
$$
$\epsilon > 0$は任意にとったので,($\ref{eq:OutMeas3}$)が成立.

(Case1-2)$\sum_{n \ge 1} \mu^*(A_n) = \infty$の場合

($\ref{eq:OutMeas3}$)の右辺が$\infty$なので常に成立

(Case2)ある自然数$n$に対して$\mu^*(A_n) = \infty$が成立している場合

($\ref{eq:OutMeas3}$)の右辺が$\infty$なので常に成立



##### Problem 1.22

> Let $F:\mathbb{R} \rightarrow \mathbb{R}$ be nondecreasing.Then, $F$ has right(left)side limit. 

Proof. (right-side limit)
Fix $x \in \mathbb{R}$.
We define sequence $\{a_n\}_{n \ge 1},a_n \equiv F(x+1/n)$.
Since $F(x)$ is nondecreasing, $\{a_n\}_{n \ge 1}$ is nonincreasing. Moreover $F(x) \le a_n$. Therefore $\{a_n\}_{n \ge 1}$ is convergent, and we can define $a \equiv \lim_{n \rightarrow \infty} a_n$. We show that
$$
lim_{y \downarrow x} F(y) = a
$$
Fix $\epsilon \gt 0$.
Since $a_n$ is  convergent, there exist $N \in \mathbb{N}$ such that
$$
 n \gt N \Rightarrow 0 \lt a_n - a \lt \epsilon \Leftrightarrow 0 \lt F(x+1/n) -a \lt \epsilon
$$
We take $\delta$ with $\delta \in (0, \frac{1}{N+1})$, and if we consider $F$ is nonincreasing,
$$
0 \lt y - x \lt \delta \Rightarrow 
	0 \lt F(y) -a \le F(x+\delta) - a \lt F(x+\frac{1}{N+1}) -a \lt \epsilon
$$

---
Proof. (left-side limit)
It is also proved in the same way, so ignore if you don't care.

Fix $x \in \mathbb{R}$.
We define sequence $\{a_n\}_{n \ge 1},a_n \equiv F(x-1/n)$.
Since $F(x)$ is nondecreasing, $\{a_n\}_{n \ge 1}$ is also nondecreasing. Moreover $F(x) \ge a_n$. Therefore $\{a_n\}_{n \ge 1}$ is convergent, and we can define $a \equiv \lim_{n \rightarrow \infty} a_n$. We show that
$$
lim_{y \uparrow x} F(y) = a
$$
Fix $\epsilon \gt 0$.
Since $a_n$ is  convergent, there exist $N \in \mathbb{N}$ such that
$$
 n \gt N \Rightarrow 0 \lt a -a_n \lt \epsilon \Leftrightarrow 0 \lt a - F(x-1/n) \lt \epsilon
$$
We take $\delta$ with $\delta \in (0, \frac{1}{N+1})$, and if we consider $F$ is nonincreasing,
$$
0 \lt x - y \lt \delta \Rightarrow 
	0 \lt a- F(y)  \le a- F(x-\delta) \lt  a - F(x-\frac{1}{N+1}) \lt \epsilon
$$
$G(\infty+) \equiv G(\infty) $
と定義する.

Proof.(a)(i) $G(\cdot)$ is nondecreasing
x = yのときは明らか.
x < yのとき成立しない、すなわち$G(x) \gt G(y) \Leftrightarrow F(x+) \gt F(y+)$が成立すると仮定する.
このとき$\epsilon = \frac{F(x+) - F(y+)}{2} $とすると$F(x+)$の定義より$0 \lt \delta$が存在し,以下を満たす.
$$
0 \lt z - x \lt \delta \Leftrightarrow
| F(x+) - F(z) | \lt \frac{\epsilon}{2}
$$
同様に$F(y+)$の定義より,$0 \lt \delta'$が存在し,以下を満たす.
$$
0 \lt v - y \lt \delta' \Leftrightarrow
| F(y+) - F(v) | \lt \frac{\epsilon}{2}
$$

ゆえに$z = x + \min\{\delta / 2, \frac{y-x}{2}\}$とすると,上記より$| F(x+) - F(z) | \lt \frac{\epsilon}{2}$.
また$0 \lt v - y \lt \delta'$を満たす$v$を1つとると,$z \lt y \lt v$なので
$$
\begin{align*}
	F(x+) \lt \frac{\epsilon}{2} + F(z) 
			\le \frac{\epsilon}{2}+ F(v) 
			\lt \epsilon + F(y+)
			= \frac{F(x+)+F(y+)}{2}
\end{align*} 
$$
より,$F(x+) \lt F(y+)$なので矛盾.

Proof. $\lim_{y \downarrow x} G(y) = G(x)$
任意に$\epsilon \gt 0$をとる.$F(x+)$の定義より$\delta_1$が存在して,
$$
\begin{align*}
	0 \lt z - x \lt \delta_1 \Rightarrow
	|F(z) - F(x+)| \lt \epsilon /2
\end{align*}
$$
ここで,$\delta = \delta_1 / 2$とすると,
$$
\begin{align*}
	0 \lt y - x \lt \delta \Rightarrow
	|G(y) - G(x)| \lt \epsilon
\end{align*}
$$
である.
実際上記を満たす$y$を任意にとると$F(y+)$の定義より$\delta_2 \gt 0$が存在して,
$$
\begin{align*}
	0 \lt z-y \lt \delta_2 \Rightarrow 
	|F(z) - F(y+)| \lt \epsilon /2
\end{align*}
$$
ここで,$v$を$y \lt v \lt y+ \min\{\delta_1/2, \delta_2\}$を満たすようにとると,
$0 \lt v - x \lt \delta_1, 0 \lt v - y \lt \delta_2$が成立するので,
$|F(v) - F(x+)| \lt \epsilon /2 \land |F(v) - F(y+)| \lt \epsilon /2$である.
ゆえに,$|F(y+) - F(x+)| \lt \epsilon$つまり,$|G(y) - G(x)| \lt \epsilon$

Proof.$\mu_F(A) = \mu_G(A) \quad (A \in \mathcal{C})$
> 始めに$G((-\infty)+) = \lim_{x \downarrow - \infty} G(x) = F(-\infty)$を示す.

任意に$\epsilon  \gt 0$をとると,$F(-\infty)$の定義より,$C \lt 0$が存在して,
$$
x \lt C \Rightarrow |F(x) - F(-\infty)| \lt \epsilon / 2
$$
が成立.このような$x$を任意にとると,$G(x)$の定義より$\delta \gt 0$が存在して,
$$
0 \lt y - x \lt \delta  \Rightarrow
|F(y) - G(x)| \lt \epsilon / 2
$$
である.ここで$z = x+ \min\{\frac{c-x}{2}, \delta /2\}$とすると,
$$
(z \lt C) \land (0 \lt z -x \lt \delta)
$$
であるので,
$$
\big(
	|F(z) - F(-\infty)| \lt \epsilon /2
\big) \land
\big(
	|F(z) - G(x)| \lt \epsilon / 2
\big)
$$
が成立.ゆえに,$|G(x)- F(-\infty)| \lt \epsilon$

次に本題の証明に入る.
定義より$F((-\infty)+) = F(-\infty)$とright continuousであることに注意すると,$\mu_F(A) = \mu_G(A) \quad (A \in \mathcal{C})$は明らか.

Proof.(b)
$(a_k, b_k]$を$b_{i+1} \le a_i$となるように並び替えても一般性を失わない.
$$
\begin{align*}
	F(b) - F(a) =& F(b) - F(b_1) \\
			&+ F(b_1) - F(a_1) + F(a_1) -F(b_2)\\
			&+F(b_2) - F(a_2) + F(a_2) - F(b_3)\\
			&\dots\\
			&+F(b_{k-1}) - F(a_{k-1}) + F(a_{k-1}) - F(b_k)\\
			&+F(b_{k}) - F(a_{k-1}) + F(a_{k-1}) - F(a_k)\\
			&+F(a_k) - F(a)\\
	=&F(b) - F(b_1) + F(a_k) - F(a) + \sum_{i=1}^{k-1} F(a_i) - F(b_{i+1}) + \sum_{i=1}^k F(b_i) - F(a_i)\\
	\ge& \sum_{i=1}^k F(b_i) - F(a_i)
\end{align*}
$$
ここで,両辺の極限をとると以下が成立.
$$
F(b) - F(a) \ge \sum_{i=1}^{\infty} F(b_i) - F(a_i)
$$
Proof(c)
> 始めに以下を示す.
> $$
> \begin{align*}
> &[c,b] \subset \bigcup_{i=1}^K (a_i, d_i)
> 	\quad (-\infty \lt c \le b \lt \infty, a_i \lt d_i) \\
> \Leftrightarrow
> &F(b) - F(c) \le \sum_{i=1}^k F(a_i) - F(d_i)
> \end{align*}
> $$

$(a_i, d_i)$を以下のように並び替える.
$a_0 = b$
for i=1 ++:
$\quad$if $a_{i-i} < c$:
$\quad$$\quad$break
$\quad$else:
$\quad$$\quad$$(a_i,d_i)$は $a_{i-1} < d_n$を満たす$(a_n, d_n)$の組のなかで$a_n$が最小のもの.
上で選ばれたものを$\{(a_i,d_i)\}_{i=1}^{K'}$とする.つまり,
$$
	\bigcup_{i=1}^K (a_i, d_i) 
		= \bigcup_{i=1}^{K'} (a_i, d_i) \cup 
			\bigcup_{i=K'+1}^{K} (a_i, d_i) 
$$
と表すことにする.このとき,$[c,b] \subset \bigcup_{i=1}^{K'} (a_i, d_i)$と$a_{i-1} \lt d_i$であることに注意すると,
$$
\begin{align*}
	F(b) - F(c ) &= F(b) - F(a_1) + 
			\sum_{i=1}^{K'-1} \big\{F(a_i) - F(a_{i+1})\big\} + 
			F(a_{K'}) - F(c)\\
		&\le F(d_1) - F(a_1) + 
			\sum_{i=1}^{K'-1} \big\{F(d_{i+1}) - F(a_{i+1})\big\} +
			F(a_{K'}) - F(c)\\
		&\le \sum_{i=1}^{K'} \big\{F(d_{i+1}) - F(a_{i+1})\big\}\\
		& \le \sum_{i=1}^K F(a_i) - F(d_i)
\end{align*}
$$
本題の証明に入る.
任意に$\eta \gt 0$をとる.
$$
F(c) - F(a) \lt \eta, F(d_n) - F(b_n) \lt \frac{\eta}{2^n} \quad (n \ge 1)
$$
を満たすように$c (\gt a)$と$d_n (\gt b_n)$をとる.このとき,
$$
[c,b] \subset (a,b] = \bigcup_{n \ge 1} (a_n, b_n] \subset \bigcup_{n \ge 1} (a_n, d_n)
$$
であることに注意すると[Heine-Borel theorem](https://www.math.utah.edu/~bobby/3210/heine-borel.pdf)よって$K \in \mathbb{N}$が存在して,
$$
[c,b] \subset \bigcup_{i=1}^K (a_i, d_i)
$$
とできる.
ここで,$(a_i,b_i)$の1番目からK番目までは上記に対応するものに並び替えておく.このとき,$[c,b] \subset \bigcup_{i=1}^K (a_i, d_i)$であるので,
$$
\begin{align*}
	F(b) - F(c) &\le \sum_{i=1}^K F(d_i) - F(a_i)\\
		&= \sum_{i=1}^K F(d_i) - F(b_i) + F(b_i) - F(a_i)\\
		&\lt \eta(1 - (1/2)^K) + \sum_{i=1}^K F(b_i) - F(a_i)\\
		&\lt \eta + \sum_{i=1}^K F(b_i) - F(a_i)
\end{align*}
$$
ゆえに,
$$
\begin{align*}
	F(b) - F(a) &= F(b) - F(c) + F(c) - F(a)\\
		&\lt \Big( \sum_{i=1}^K F(b_i) - F(a_i)\Big) + 2 \eta\\
		& \le \Big( \sum_{i=1}^{\infty} F(b_i) - F(a_i)\Big) + 2 \eta
\end{align*}
$$
