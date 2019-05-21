[TOC]



## 実数の構成

* 自然数の構成  
    * ペアノの公理を満たす集合の構成(英語)(ZF公理系 分出公理等を仮定!?)  
    https://math.stackexchange.com/questions/68659/set-theoretic-construction-of-the-natural-numbers
    
* 実数の構成  
    * 実数の構成(日本語)  
        * 概要  
        ピアノの公理を満たす集合を自然数とすることから出発して(公理を満たす集合が存在することは証明しない)、整数、有理数、実数、複素数を順に構成する教科書です。順序、絶対値、最大公約数、素数なども扱ってます.  
        * 主な内容    
        自然数の整列性、有理数・実数の稠密性、実数の完備性、Archimedesの性質  
        * 特徴  
        丁寧だが、似たような証明が続くため分量が多いです。数学科の学生なら事前知識は必要ありません。  
        * テキスト  
        http://mathematics-pdf.com/pdf/construction_of_numbers.pdf  
        Local:`/Users/akirat/study/textbook/construction_of_numbers.pdf`  

## 代数

* 体上の多項式に関する除法定理(Remainder Theorem)
http://mnishi.my.coocan.jp/mnishi/11A1/note/chapter2.pdf
* 複素数係数の多項式の因数分解  
http://www.ms.u-tokyo.ac.jp/activity/documents/tsuji.pdf#search='%E4%BB%A3%E6%95%B0%E5%AD%A6%E3%81%AE%E5%9F%BA%E6%9C%AC%E5%AE%9A%E7%90%86'
* 多項式の積の可換(associativity) 証明
https://math.stackexchange.com/questions/77671/how-to-show-associativity-of-multiplication-of-polynomials-in-rx-where-r



## 微積

### 基礎

* 全体の教科書
  Calculus / Michael Spivak
* [各点収束,一様収束周り](./calculus_compl)
  * 各点収束,一様収束,絶対一様収束の定義
  * 収束列の定数倍は収束列
  * 一様収束の同値条件(Cauchy)
  * Mテスト
  * 無限和の交換
  * 点列と関数列の極限の交換の定理
  * 各点収束先と一様収束先は一致する
  * 有限和と極限の交換
  * 絶対収束するなら収束する

* 連続・微分・1変数積分
  https://math.dartmouth.edu/~doyle/docs/calc/calc.pdf
  Local:`/Users/akirat/study/textbook/calculus1.pdf`  
* ロルの定理の証明(英語)  
  https://oregonstate.edu/instruct/mth251/cq/Stage7/Lesson/rolles.html  
  Local:`/Users/akirat/study/textbook/Rolle.pdf`
* 平均値の定理の証明(英語)  
  https://www.math.hmc.edu/calculus/tutorials/mean_value/proof_mean.html
  Local:`/Users/akirat/study/textbook/MeanValue.pdf`
* ベクトルで微分  
  https://qiita.com/AnchorBlues/items/8fe2483a3a72676eb96d
  ​      
* 陰関数定理で偏微分の値が0でない条件はなぜ必要かを直感的に説明している教科                                                                                                                                                                                                        書
  https://lecture.ecc.u-tokyo.ac.jp/~nkiyono/kiyono/16_6-12.pdf

### 初等関数

- 乗冪(有理数乗冪まで)
  - 全体テキスト  
    http://www.math-konami.com/lec-data/ch23.pdf  
    Local:`/Users/akirat/study/textbook/exponent.pdf`  
  - n乗根の存在の証明  
    http://ckottke.ncf.edu/neu/3150_fa15/nthroots.pdf  
    Local:`/Users/akirat/study/textbook/nthroot.pdf`
- 乗冪(実数に拡張)
  - https://math.stackexchange.com/questions/55068/can-you-raise-a-number-to-an-irrational-exponent  

 

## 集合

* [有限集合の濃度は一意に定まることの証明](./set)
* 濃度の基礎(実数全体と自然数の部分集合全体の濃度は等しいなど)  
  説明が不十分な部分があるため別の資料などを参考にして用いると良い.  
  ※なおベルンシュタインの定理はWikipedia等を参考にすると良い  
  URL>3章 集合の濃度  
  http://www.math.titech.ac.jp/~kotaro/class/2011/set/lecture.pdf  
  Local:`/Users/akirat/study/textbook/cardinality.pdf`  
* 有限集合の部分集合は有限集合の証明(英語)  
  URL>第一段落、Fact2. A subset of a finite set is finite  
  http://math.uga.edu/~pete/settheorypart1.pdf  
  Local:`/Users/akirat/study/textbook/finite_subset.pdf`  
* 有限集合の和集合は有限集合(英語)  
  * 概要  
  証明はないが上記"有限集合の部分集合は有限集合の証明"を用いれば(a)は簡単に示せて、(b),(c)の証明も比較的容易  
  * テキスト  
  　URL>Theorem 3 (Fundamental Properties of Finite Sets)  
  　https://sites.math.washington.edu/~lee/Courses/300-2017/finite-sets.pdf  
* 任意の無限集合は加算無限集合をもつ
  https://math.stackexchange.com/questions/1403416/infinite-set-always-has-a-countably-infinite-subset
* 無理数の濃度と実数の濃度は等しい(証明の概略のみ)
  https://detail.chiebukuro.yahoo.co.jp/qa/question_detail/q11110681666
* Ramsey's theorem  
  https://en.wikipedia.org/wiki/Ramsey%27s_theorem#Infinite_Ramsey_theorem
* Ordered Set (Partial/Total, Well Ordering)
  https://www.whitman.edu/mathematics/higher_math_online/section05.03.html
* Any infinite totally ordered set contains a monotone sub-sequence ($x_0 \le x_1 \le x_2 \dots$ or $x_0 \ge x_1,\dots$)  
  https://math.stackexchange.com/questions/716461/proof-verification-every-sequence-in-bbb-r-contains-a-monotone-sub-sequence
* The cartecian product of a finite amount of countable sets is countable
  https://math.stackexchange.com/questions/2357899/the-cartesian-product-of-a-finite-amount-of-countable-sets-is-countable

## 位相空間

* オススメ教科書の紹介(英語)  
    https://math.stackexchange.com/questions/7520/best-book-for-topology  
    Local:`/Users/akirat/study/textbook/TopologyWithoutTears.pdf`  
* Topology without Tears  
http://www.topologywithouttears.net/topbook.pdf  
    * second contable base contains a countable base, hence separable.
      http://www.southalabama.edu/mathstat/personal_pages/jbarnard-archive/teaching/F08-434-542/hwk3sol.pdf
    * uncountable set with cofinite topology is not 1st countable
      https://math.stackexchange.com/questions/546123/let-x-be-any-uncountable-set-with-the-cofinite-topology-answer-the-three-questi
    * Dense subset of $\mathbb{R}$ with the Eucliean topology is dense in Sorgenfrey line.
      https://etd.auburn.edu/bitstream/handle/10415/393/GREIWE_REGINA_16.pdf?sequence=1
    * Sorgenfrey line is not second countable
      https://etd.auburn.edu/bitstream/handle/10415/393/GREIWE_REGINA_16.pdf?sequence=1
    * Lindelofspace  
      Every uncountable subset of $\mathbb{R}$ contains one of its limit points for Euclidean topology.  
      https://dantopology.wordpress.com/2010/05/29/the-lindelof-property-of-the-real-line/
    * Exercises4.3-#8-(ⅰ)  
https://math.stackexchange.com/questions/2668271/countable-subspace-of-uncountable-set-is-indiscrete-or-t-0
    * Exercises4.3-#8-(Ⅱ)  
      https://math.stackexchange.com/questions/2319667/cofinite-discrete-subspace-of-a-t1-space
    * Exercises4.3-#8-(Ⅲ)  
      Every 
      https://math.stackexchange.com/questions/533051/every-infinite-hausdorff-space-has-an-infinite-discrete-subspace
    * Exercises4.3-#8-(IV),(V)
      https://math.stackexchange.com/questions/2326313/subspace-homeomorphic-to-initial-final-segment-topology
    * Any subspace of separable metric space is seperable
      https://alanmath.wordpress.com/2011/06/07/any-subspace-of-a-separable-metric-space-is-separable/
    * Open subset of Polish space is Poli space (Lemma3.4)
      http://www.math.uconn.edu/~solomon/notes/desc2.pdf
    * A subset of Polish Space is Polish if and only if it is a $G_{\delta}$ set there.  
      P6 > Theorem 7   
      http://individual.utoronto.ca/jordanbell/notes/polish.pdf  

* 線形位相空間(Topological Vector Space)
    * 概要:  
    http://www.ma.huji.ac.il/~razk/iWeb/My_Site/Teaching_files/TVS.pdf

* ノルム空間
    * 有限次元ノルム空間の任意のノルムは同値(p26 A.5)
    http://www.ma.noda.tus.ac.jp/u/sh/pdfdvi/13fa-s.pdf
    * 有限次元線形写像の連続性
    https://ja.wikipedia.org/wiki/%E4%B8%8D%E9%80%A3%E7%B6%9A%E7%B7%9A%E5%9E%8B%E5%86%99%E5%83%8F
    * Subset of finite dimensional norm equal to 1 is compact
    https://math.stackexchange.com/questions/895142/proof-of-compactness-for-sets-of-norm-equal-to-one-in-finite-dimensional-normed
    * Matrix Norm  
    https://www.uio.no/studier/emner/matnat/ifi/nedlagte-emner/INF-MAT4350/h08/undervisningsmateriale/chap13slides.pdf
    * Calculation of operator norm when p = 2
    https://math.stackexchange.com/questions/1877202/why-is-the-operator-norm-so-hard-to-calculate
    * $L_p$ノルム空間
        * $0 < p < 1$のとき,$\sum_{i=1}^n \| x_i - y_i \|^p$は距離を定める.
            * $(a+b)^p \le a^p + b^p$の証明
            https://matthewhr.files.wordpress.com/2012/09/lp-spaces-for-p-in-01.pdf
        * $1 \le p$のとき, $ \left( \sum_{i=1}^n | x_i |^p \right)^{1/p}$
            * $\lim_{p \rightarrow \infty} \| x \|_p = \| x \|_{\infty}$
            https://math.stackexchange.com/questions/326172/the-l-infty-norm-is-equal-to-the-limit-of-the-lp-norms/326266
            * p-norm is monotone decreasing
            http://emis.impa.br/EMIS/journals/IJOPCM/Vol/10/IJOPCM(vol.3.2.5.J.10).pdf

## グラフ理論

* Algorithm Design / Jon Kleinberg, Eva Tardos-1st. ed.  
    `ds:/backup/share/text/Algorithm_Design`  
    URL:http://www.icsd.aegean.gr/kaporisa/index_files/Algorithm_Design.pdf

    * Detail  
        ISBN 0-321-29535-8  
        Prepress and Manufactureing Caroline Fell  
        Printer: Courier Westford  

        Complement:  
        https://www.evernote.com/l/AVonLh--  gHtAgZIdCQnceqjpI1ogDDR6hbA  

* 最小費用流(Minumum Cost Flow)  
    http://perso.ens-lyon.fr/eric.thierry/Graphes2010/amaury-pouly.pdf  
    https://www.evernote.com/l/AVojuJInPBVDFZ_V_shJDzLFfat9cIh-N1I  

* スペクトラル・クラスタリング  
    https://www.evernote.com/l/AVr6FzsGIMtDT7KoFy_0ea_xi3_haAJOpEc  

* 神山先生おすすめ

    * ネットワーク・大衆・マーケット ―現代社会の複雑な連結性についての推論




## 多変量解析

* [異常検知と変化検知 (井出剛 杉山将)](./異常検知と変化検知)
* [入門 機械学習による異常検知 Rによる実践ガイド(井手剛)](機械学習による異常検知)  



## 線形代数

* 線形空間と線形写像
    * [テキスト1](http://staff.miyakyo-u.ac.jp/~k-taka2/pdf/linalg/chap5.pdf   )
    * [テキスト2](http://wwwa.pikara.ne.jp/yoshifumi/FLA/FLA-7.pdf  )
      Prop7.1.7 線形写像が同型(全単射)である必要十分条件  
    * [行列式(det)は連続関数であることの証明(英語)](https://math.stackexchange.com/questions/1314411/proof-that-determinant-is-continuous-using-epsilon-delta-definition)
    * [半正定値行列の同値条件(対称行列,エルミート行列)](https://risalc.info/src/positive-semi-definite-properties.html)

* 行列  
    * 特異値分解(singular value decomposition)
      https://wiki.math.ntnu.no/_media/tma4205/2017h/svd.pdf  
      https://people.mpi-inf.mpg.de/~bast/seminar-ws04/lecture2.pdf



## 確率(probability)

### 並び替え(sort)

* [重み付きランダムソート(Weighted Random Sampling)](./WRS)



### 測度論からの確率論

+ [Measure Theory and Probability Theory](measure_and_probability_theory)
  
+ ベイジアンネットワーク

    * [グラフィカルモデル 渡辺 有祐](./PGM_TB01)

+ 多変量正規分布について良さそうな教科書

    http://www012.upp.so-net.ne.jp/doi/math/anova/m_normal.pdf

## 最適化(Optimization)

+ 0-1整数計画  
    整数計画法における定式化入門  
    http://web.tuat.ac.jp/~miya/fujie_ORSJ.pdf

+ SDPA  
    + Constraints of SDPA p59  
    `/Users/akirat/study/textbook/SDP/sdpara_ipdps14_submit_final.pdf`  
    + format    
    `/Users/akirat/study/textbook/SDP/SDPA_format.pptx`  
    + paper  
    `/Users/akirat/study/textbook/SDP/SDPA-100721.pdf`  
* least squares problem
    * Linear Least Square Problem  
    $ \nabla f(x) := A^T (A x -y)$  
    $ \nabla^2 f(x) = A^T A$   
    http://www2.aueb.gr/users/douros/docs_master/Least_Square_pr.pdf
      
    * Rank-Deficient Linear Least Square Problem
    https://www.math.uwaterloo.ca/~tfcolema/articles/LS-paper.pdf  
    http://www2.aueb.gr/users/douros/docs_master/Least_Square_pr.pdf
    
    * Least Square Problem
    http://www4.ncsu.edu/~mtchu/Teaching/Lectures/MA529/chapter4.pdf

## 測度論

* ルベーグ測度(未読)
  https://www.math.nagoya-u.ac.jp/~yamagami/teaching/topics/integral2018.pdf

* [濃度を表す関数は測度](./set)
## 凸関数

* First and second order characterization  
$f(y) \ge f(x) + \nabla ^T f(x) (y-x)$  
$\nabla^2 f(x) \ge 0$ 
http://www.princeton.edu/~amirali/Public/Teaching/ORF523/S16/ORF523_S16_Lec7_gh.pdf

* Monotonity of $\nabla f(x)$  
$\langle \nabla f(x) - \nabla f(y),  x - y  \rangle \ge 0$  
https://www.math.cuhk.edu.hk/course_builder/1617/math6211a/cvxop.pdf

* stationary point is a global minimum  
https://people.seas.harvard.edu/~yaron/AM221-S16/lecture_notes/AM221_lecture8.pdf

* 二階微分が非負(second derivative is nonnegative everywhere implies convex)  
http://math.ucr.edu/~res/math133/convex-functions.pdf



## 深層学習

[深層学習まとめ](deep_learning)

VAEの解説

https://nzw0301.github.io/notes/vae.pdf

鍛冶先生が深層学習について共有 20181002  
https://arxiv.org/pdf/1805.12324.pdf



## 幾何学

* [楕円](./ellipse.md)
* [離心率について分かりやすい資料](http://examist.jp/mathematics/math-3/quadratic-curve/risinritu/)



## マップマッチング

* [地理緯度と地心緯度との関係](http://www.infra.kochi-tech.ac.jp/takagi/Geomatics/2GeoCoord.pdf)

  

***
All TextBook :  
`local:/Users/akirat/study/textbook/`  
MacDown:`Bitbucket>akirat1993/macdown.git/Files/textbook.md:Jan 30 14:39:04`  