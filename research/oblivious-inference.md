# Oblivious Inference: 不经意推断

## 背景

「Inference」在机器学习中指的是，对训练好的机器学习模型提供输入，进行计算从而得到输出这一过程，中文翻译过来叫做「推断」，通常也说「预测」（predict）（关于二者的差别有一些[相关讨论](https://www.datascienceblog.net/post/commentary/inference-vs-prediction/)，在此我们不作深究）。

所谓不经意推断（Oblivious Inference）指的是这样一个场景：服务器端 **S** 持有一个已训练好的模型 *M*，客户端 **C** 持有输入数据 *D*。
在进行推断/预测的过程中，输入数据 *D* 对服务器端 **S** 保密，同时模型 *M* 对客户端 **C** 保密。

在已有的研究中，该任务通常借助于 MPC 来实现：把模型结构编译成通用电路，把模型参数 *$\theta$* 和输入数据 *D* 分别当成 MPC 中两方的输入，电路的输出则为模型的推断结果。
**从理论上来说，该任务也可借助于 PFE 来实现：服务器端将模型（结构和参数）转化为 PFE 中的 *f*，客户端提供输入数据 *D* 从而交互进行计算，最后的计算输出即为推断结果。**

## 主要相关工作（按时间排序）

- [CryptoNets: Applying Neural Networks to Encrypted Data with High Throughput and Accuracy](http://proceedings.mlr.press/v48/gilad-bachrach16.pdf)
  - PMLR, 2016
- [SecureML: A System for Scalable Privacy-Preserving Machine Learning](https://eprint.iacr.org/2017/396.pdf)
  - S&P, 2017
- [Oblivious Neural Network Predictions via MiniONN Transformations](https://dl.acm.org/doi/pdf/10.1145/3133956.3134056)
  - CCS, 2017
- [Chameleon: A Hybrid Secure Computation Framework for Machine Learning Applications](https://dl.acm.org/doi/pdf/10.1145/3196494.3196522)
  - ASIACCS, 2018
- [GAZELLE: A Low Latency Framework for Secure Neural Network Inference](https://arxiv.org/pdf/1801.05507.pdf)
  - USENIX, 2018
- [XONN: XNOR-based Oblivious Deep Neural Network Inference](https://arxiv.org/pdf/1902.07342.pdf)
  - USENIX, 2019
- [On the Application of Binary Neural Networks in Oblivious Inference](https://openaccess.thecvf.com/content/CVPR2021W/BiVision/html/Samragh_On_the_Application_of_Binary_Neural_Networks_in_Oblivious_Inference_CVPRW_2021_paper.html)
  - CVPR, 2021

