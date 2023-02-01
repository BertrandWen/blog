# Boolean satisfiability problem (SAT)

## 基本背景

布尔可满足性问题 (Boolean satisfiability problem, aka SAT) 是第一个被证明是 NP 完全的问题。
其定义为，对于一个由若干布尔变量构成的表达式 (formula)，问是否存在一组变量取值使得表达式为 True（也即 satisfiable）。

更详细地来说，该表达式应为合取范式（conjunctive normal form, CNF），即其一般形式为 $F = c_1 \land c_2 \land ... \land c_n$.  
其中，$c_i = x_1 \lor x_2 \lor \lnot x_3 \lor ...$.  
对于以上符号，有一套特定的称呼：
- $F$: 表达式（formula），在此处由一串**子句（clause）**的**与**组成
- $c_i$: 子句（clause），由一些**文字（literal）**的**或**组成
- $x_i$: 文字（literal），其为变量（$x_1$）或变量的否定（$\lnot x_3$），取值为 *True* 或者 *False*

实际中，借助推导或者真值表，一切布尔表达式都可被转化为 CNF 的形式，因此其求解也可以被转化为 SAT 的求解，因而 SAT 求解在许多如硬件设计和安全协议验证的问题中存在广泛的应用。

## SAT 学习路径

以下整理自蔡少伟老师的微博分享：

- 主要路线
  -  Handbook of SAT Chapter 2: 
     -  1 month 
  -  Handbook of SAT Chapter 3-4: 
     -  4 month 
     -  实践：miniSAT 实现
  -  Stochastic Local Search: Foundation and Applications 
     -  3 month 
     -  实践：SLS 算法实现
-  参考资料
   -  Handbook of SAT 第二版，主要是前四章
   -  TAOCP Volume 4, Fascicle 6: Satisfiability: 主要关注encoding, backtracking, clause learning


## 相关学者或工作

一些做 SAT 的团队：
- 滑铁卢大学的 [Vijay Ganesh](https://ece.uwaterloo.ca/~vganesh/)
- 德国 University of Freiburg 的 [Armin Biere](http://fmv.jku.at/biere/)，如今的 SAT 协会主席，也是 Handbook of Satisfiability 的主要作者之一
- 国内中科院软件所的[蔡少伟老师](https://people.ucas.ac.cn/~caisw)在经典的 SAT 求解路线（CDCL + Local search）有相当多的工作
- 澳洲 Monash University 的 [Alexey Ignatiev](https://alexeyignatiev.github.io/)，其本人也是 [pysat](https://github.com/pysathq/pysat) 的主要开发者之一（这个包的模块和接口设计都好得让我惊叹）
- 加拿大 University of Alberta 的 [Martin Müller](https://webdocs.cs.ualberta.ca/~mmueller/) and [Jia-Huai You](https://webdocs.cs.ualberta.ca/~you/)
- 法国 University of Picardie Jules Verne 的[李初民老师](https://home.mis.u-picardie.fr/~cli/)

另外，国内上交严骏驰老师做了基于机器学习的组合优化问题的工作，其团队整理了一份 Machine Learning for Combinatorial Optimization 的资源，其中 [SAT 部分](https://github.com/Thinklab-SJTU/awesome-ml4co#boolean-satisfiability) 的也很值得 follow。

部分 SAT + ML 论文：
- [Learning a SAT Solver from Single-Bit Supervision](https://openreview.net/pdf?id=HJMC_iA5tm) ICLR, 2019 [[code](https://github.com/dselsam/neurosat)]
- [Learning To Solve Circuit-SAT: An Unsupervised Differentiable Approach](https://openreview.net/pdf?id=BJxgz2R9t7) ICLR, 2019
- [Learning Local Search Heuristics for Boolean Satisfiability](https://proceedings.neurips.cc/paper/2019/file/12e59a33dea1bf0630f46edfe13d6ea2-Paper.pdf) Neurips, 2019
- [SATNet: Bridging deep learning and logical reasoning using a differentiable satisfiability solver](https://arxiv.org/pdf/1905.12149.pdf) ICML, 2019 [[code](https://github.com/locuslab/SATNet)] [[slides](https://powei.tw/satnet_slide.pdf)]
- [Transformer-based Machine Learning for Fast SAT Solvers and Logic Synthesis](https://arxiv.org/pdf/2107.07116.pdf) ArXiv, 2021
- [Machine Learning Methods in Solving the Boolean Satisfiability Problem](https://arxiv.org/pdf/2203.04755.pdf) ArXiv, 2022

## 有用的资源

- [Conflict Driven Clause Learning 的可视化介绍（强烈安利！）](https://cse442-17f.github.io/Conflict-Driven-Clause-Learning/)
- [Handbook of Satisfiability - Chapter 4: Conflict-Driven Clause Learning SAT Solvers](https://www.cs.princeton.edu/~zkincaid/courses/fall18/readings/SATHandbook-CDCL.pdf)
- [Understanding SAT by Implementing a Simple SAT Solver in Python](https://sahandsaba.com/understanding-sat-by-implementing-a-simple-sat-solver-in-python.html)

## SAT 周边

- [中科院软件所蔡少伟专访](https://mp.weixin.qq.com/s/XOps4NT84tLOJaInW8pD8A)
- [解决中国“卡脖子”问题：研究求解器的少数者](https://www.leiphone.com/category/academic/rArjum9yhqL4G9Rc.html)
- [追求最优，「约束求解」这一小拨人的问题与实践](https://hub.baai.ac.cn/view/9982)