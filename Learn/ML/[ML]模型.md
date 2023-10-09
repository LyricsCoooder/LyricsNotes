# 模型

在监督学习过程中，模型就是所要学习的条件概率分布或决策函数，模型的假设空间包含所有可能的条件概率分布或决策函数.假设空间中的模型一般有无穷多个.

#### 决策函数—非概率模型

假设空间用 $\mathcal F$ 表示，用假设空间可以定义为这些决策函数的集合：
$$
\mathcal F=\{f{|}Y=f\left ( {X}\right )\}
$$
其中，$X$ 和 $Y$ 是定义在输入空间 $\mathcal X$ 与输出空间 $\mathcal Y$ 上的变量，这时的 $\mathcal F$ 通常是由一个参数向量决定的函数族，参数向量 $\theta$ 取决于 $n$维的欧式空间 $\mathbf R^n$ ,所以 $\theta$ 被称为参数空间：
$$
\mathcal F=\{f{|}Y=f_{\theta}\left ( {X}\right ),\theta\in \mathbf R^{n}\}
$$

#### 条件概率分布—概率模型

假设空间也可以定义为条件概率的集合：
$$
\mathcal F = \{P|P\left ({Y|X}\right)\}
$$
其中，$X$ 与 $Y$ 都是定义在输入空间 $\mathcal X$ 与输出空间 $\mathcal Y$ 上的随机变量，这时的 $\mathcal F$ 通常是由一个参数向量决定的条件概率分布族：
$$
\mathcal F = \{P|P_\theta\left ({Y|X}\right),\theta\in \mathbf R^{n}\}
$$

---

