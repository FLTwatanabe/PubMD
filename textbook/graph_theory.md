### 目的
sourceとsinkが複数ある場合でもフロー分解が成立することを証明する.  

### 定義
source集合を$S$,sink集合を$T$とする.    
今後考えるグラフ$G := (V,E)$はsource->sourceもしくはsink->sinkを繋ぐ有効枝は存在しないとする.つまり,
$$
(s_1, s_2) \notin E \quad (\forall s_1, s_2 \in S)\\
(t_1, t_2) \notin E \quad (\forall t_1, t_2 \in T)
$$

またフロー$x:E \rightarrow \mathbb{R}_{\ge0}$が与えられたとき,
任意の頂点$v$に対して,正味の流出量$b(v)$を以下のように定める.
$$
b(v) = \sum_{e\in E(v,V)} x(e) - \sum_{e\in E(V,v)} x(e)
$$
また,フロー$x$のフロー値$f(x)$を以下で定める.  
$$
    f(x) 
    = \sum_{s \in S} \sum_{e \in E(s, V)} x(e) - \sum_{s \in S} \sum_{e \in E(V, s)} x(e)
    = \sum_{s \in S} b(s)
$$
さらにフロー$x$が以下の条件を満たすとき,$S$-$T$フローと呼ぶ.  
$$
b(s) \ge 0 \quad (\forall s \in S)\\
b(t) \le 0 \quad (\forall t \in T)
$$


#### 補題2.1 フロー分解のためのcutに関する補題
頂点集合の部分集合$A \subseteq V$に対して$A$からの流出量$x^{out}(A)$と$A$への流入量$x^{in}(A)$を以下のように定める.
$$
x^{out}(A) := \sum_{e = (v,w) \in E, v \in A, w \in V \setminus A} x(e)\\
x^{in}(A) := \sum_{e = (v,w) \in E, v \in V \setminus A, w \in A} x(e)
$$  

$S \subseteq A$かつ$T \subseteq B$を満たす頂点集合$V$の分割$V = A \sqcup B$を$S$-$T$カットと呼び,$S$-$T$カットの容量$c(A,B)$を
$$
c(A,B) := \sum_{(v,w) \in E, v \in A, w \in B} x(e)
$$
と定義する.  
このとき以下が成立
> $x$を任意の$S$-$T$フローとし,($A$,$B$)を任意の$S$-$T$カットとする.  
> このとき$f(x) = x^{out}(A) - x^{in}(A)$

(Proof)  
$$
\begin{align*}
    f(x)  &= \sum_{s \in S} b(s)\\
          &= \sum_{v \in A} b(v) \quad (\because \text{フロー保存則})\\
          &= \sum_{v \in A}
            \left(
                \sum_{e \in E(v, V)} x(e) - \sum_{e \in E(V, v)} x(e)
            \right)\\
          &= \sum_{v \in A}
            \left(
                \sum_{e \in E(v, A)} x(e) + \sum_{e \in E(v, B)} x(e)
            \right)
          - \sum_{v \in A}
            \left(
                \sum_{e \in E(A, v)} x(e) + \sum_{e \in E(B, v)} x(e)
            \right)\\
          &= \left(
                \sum_{v \in A} \sum_{e \in E(v, B)} x(e)
            -   \sum_{v \in A} \sum_{e \in E(B, v)} x(e)
            \right) +
            \left(
                \sum_{v \in A} \sum_{e \in E(v, A)} x(e)
            -   \sum_{v \in A} \sum_{e \in E(A, v)} x(e)
            \right)\\
          &= x^{out}(A) - x^{in}(A)
\end{align*}
$$

#### 補題2.1 フロー分解

>
$x$をネットワーク $N = [G = (V,E);S,T,u]$上の($S$-$T$)フローとする.  
このとき$x$は流量が正であるsourceからsinkへの有限個のパスと流量が正である有限個の閉路に分解することができる.  
さらに閉路の個数は最大で|E|個で,パスと閉路の個数の総和は最大で$|E| + |V|$になるようにできる.

(Proof)  
$b(s_0) > 0$となる$s_0 \in S$が存在する限り以下の操作(操作1)を繰り返す.  
(この操作が有限回で終了することは最後に示す)  
$b(s_0) > 0$より$e_0 = (v_0, v_1) \in E$かつ$x(e_0) > 0$を満たすアーク$e_0$が存在する.$v_1 \in T$であるならsinkに到達する流量が正のパス$P$が得られたことになる.そうでない場合はフロー保存則($v_1 \notin S \cup T$の場合)もしくは$b(v_1) \ge 0$($v_1 \in S$の場合)という仮定から$e_1 = (v_1, v_2)$かつ$x(e_1) > 0$を満たすアーク$e_1$が存在する.この議論を繰り返し行うことで,頂点$V$が有限個であることから    
(1) sinkに到達するパス$P$が得られる(終点を$t_0$とおく)  
(2) 1度訪れたノードに到達するパスが得られる  
かのいずれかが起こる.  
(1)の場合  
$\delta := \min \{ b(s_0), -b(t_0), \min_{e \in P} x(e)\}$とし,フロー$x$からパス$P$に流量$\delta$を流したフローを除く操作を行う.すなわち,新しいフローを$x'$とすると
$$
x'(e) =
\begin{cases}
    x(e) - \delta \quad &\text{if } e \in P\\
    x(e) \quad &\text{otherwise}
\end{cases}
$$  
(注意)  
$\delta := \min_{e \in P} x(e)$でなく$\delta := \min \{ b(s_0), -b(t_0), \min_{e \in P} x(e)\}$とすることにより新しいフローも($S$-$T$)フローとなっていることに注意する.  

(2)の場合  
流量が正の閉路$C$が得られるので,$\delta := \min_{e \in C} x(e)$と定義し,フロー$x$から閉路$C$に流量$\delta$を流したフローを除く操作を行う.すなわち
$$
x'(e) =
\begin{cases}
    x(e) - \delta \quad &\text{if } e \in C\\
    x(e) \quad &\text{otherwise}
\end{cases}
$$  

次に上記の操作1が終了した後の操作(操作2という)について述べる.  
初めに操作1が終了した時点で全ての頂点$v \in V$に対して$b(v) = 0$となっていることを示す.  
$v \notin T$ならば,操作1とフロー保存則より$b(v) = 0$であるので,$v \in T$である場合について考える.  
上記のcutに関する補題より,
$$
\begin{align*}
f(x) 
&= \sum_{s \in S} b(s) \\
&= x^{out}(V \setminus T) - x^{in}(V \setminus T)\\
&= -\left(
    x^{out}(T) - x^{in}(T)
    \right)\\
&= - \sum_{t \in T} b(t)
\end{align*}
$$
であり, $b(s) = 0 \,\,(\forall s \in S)$かつ$S$-$T$フローの条件より$b(t) \le 0 \quad (\forall t \in T)$であるので,$b(t) = 0 \,\, (\forall t \in T)$となる.  
続いて操作2について述べる.  
$x(e) > 0$となるアークが存在する限り以下の操作(操作2)を繰り返す.  
全ての頂点$v \in V$においてフロー保存則$b(v) = 0$が成立していることを考慮すると,操作1と同じ議論から流量が正の閉路が得られるので,$\delta := \min_{e \in C} x(e)$とおきフロー$x$から閉路$C$に流量$\delta$を流したフローを引く.  

操作2が終了した時点で全てのアークの流量は0となるので,フローを分解出来たことになる.  
最後に操作1と操作2は有限回で終わることを証明する.  
操作1,2のいずれかの操作を1回行うことによって次の3つのうちいずれかが起こる.  
(a)少なくとも1つのアークの流量が0となる.($\delta := \min_{e \in C} x(e)$となるとき)  
(b)少なくとも1つの$v \in S \cup T$について$b(v) = 0$となる.  ($\delta := b(s_0)$ or $-b(t_0)$となるとき.)  
操作1と操作2のいずれかの1回の操作によって,流量が正である$S$-$T$パスもしくは閉路が得られるのでパスと閉路の個数の総和は最大で$|E|+|V|$となるようにできる.また1回の操作によって,閉路が除かれる場合は(a)の場合のであるので,閉路の個数は最大で$|E|$個となるように分解できる.  
(補足)  
>操作1が終わった段階で$x(e)>0$となるアークが存在した場合$e$を通る流量が正の閉路が存在する.  

(Proof)  
上記の証明より$x(e)>0$となるアークが存在した場合には流量が正の閉路が存在するがその閉路が$e$を含む場合は証明終了.含まない場合はフローを更新した後も$x(e) >0$となるので同様の操作を繰り返すことができる.もし,この操作を何回繰り返しても$e$を含む閉路が得られないとするとこの操作は有限回で終了しないことになり矛盾.


