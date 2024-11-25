# linear-algebra
## 1 二阶方阵的逆矩阵
A的逆矩阵： $AA^{-1} = A^{-1}A = I \Leftrightarrow A^{-1} = \frac{1}{\left|x\right|} A^{*}$

最重要的一点，我一直搞错了：矩阵A的**伴随矩阵( $A^*$ )**是**余子矩阵**的转置！！！

因此对于二阶矩阵A，

 $$A = \begin{bmatrix}
  a&b \\
  c&d
\end{bmatrix}$$

A的余子矩阵为：

$$B = \begin{bmatrix}
 d&-c \\
 -b&a
\end{bmatrix}$$

所以，

$$ A^{*} = B^{T}= \begin{bmatrix}
  d&-b\\
  -c&a
  \end{bmatrix}$$

所以，二阶矩阵的逆矩阵：

$$ A^{-1} = \frac{1}{\left|x\right|} \begin{bmatrix}
  d&-b\\
  -c&a
  \end{bmatrix}$$

参考：

-https://zh.wikipedia.org/zh-cn/%E4%BC%B4%E9%9A%8F%E7%9F%A9%E9%98%B5

-https://tchel.github.io/2018/09/29/The-Inverse-Matrix-of-2x2/

## 2 对称多项式
在n元置换下保持不变的多项式就是对称多项式。

例如: $f(x_1,x_2) = x_1^2 + x_1x_2 + x_2^4$ , 把 $x_1和x_2$ 互换位置，很显然多项式保持不变。

## 3 矩阵对角化和Jorand标准型
定义：一个矩阵A $\in R^{n\times n}$或者 $\in C^{n\times n}$ 能表示为：

$$ A = DPD^{-1} $$

其中D是可逆矩阵，而P是对角矩阵（只有对角线上有元素的矩阵），那就称A能够对角化。

很自然的，我们想知道矩阵对角化有啥用处，又或是什么情况下矩阵能够对角化呢？

i. 矩阵A可以对角化当且仅当：
- 矩阵A的所有特征值都不同，那么A总能对角化。
- 矩阵A的特征值有重根，需要满足：特征值对应的特征向量个数要等于特征根的重数。

ii. 具体步骤：
- $det\left|A - \lambda I\right| = 0$，求出 $\lambda_1, \lambda_2, ..., \lambda_n$。
- $对于每个特征值，(A - \lambda_{i}I)v_{i} = 0$，求出 $v_1, v_2,...,v_n$。
- 如果满足i中的要求, $D = [v_1, v_2,...,v_n]$, $P=diag(\lambda_1,\lambda_2,...,\lambda_n)$。

iii. 重要结论: 矩阵幂的递推

利用  $A = PDP^{-1}$ ，我们计算  $A^2$ ：

$$A^2 = A \cdot A = (PDP^{-1})(PDP^{-1}).$$

由于矩阵乘法的结合性和  $P^{-1}P = I$ （单位矩阵），得到：

$$A^2 = PD(P^{-1}P)DP^{-1} = PD^2P^{-1}.$$


类似地，计算  $A^3$ ：

$$A^3 = A \cdot A^2 = (PDP^{-1})(PD^2P^{-1}) = PD^3P^{-1}.$$


归纳得：

$$A^n = PD^nP^{-1}.$$

iv. 应用
- 简化矩阵的逆运算：
考虑一个人口模型，状态转移矩阵为：
  
$$A = \begin{bmatrix}
  0.8&0.4\\
  0.6&0.7
  \end{bmatrix}$$

目标：预测n年后的状态：$x_n = A^{n}x_o$
如果矩阵A可对角化，那就简单多了， A = $DPD^{-1}$， $A^n = DP^{n}D^{-1}$， $P^{n} = diag(\lambda_{1}^{n},\lambda_{2}^{n},...,\lambda_{n}^{n})$。

v. 例子

$$A = \begin{bmatrix}
4&1\\
3&2
\end{bmatrix}$$

$$det\begin{bmatrix}
4-\lambda&1\\
3&2-\lambda
\end{bmatrix} = (4-\lambda)(2-\lambda) - 3 = 5 - 6\lambda + \lambda^2 = (\lambda - 1)(\lambda - 5) = 0 $$

因此，特征值分别为： $\lambda_1 = 5$ 、 $\lambda_2 = 1$,对应的特征向量分别为: $v_1 =(1,1)$ 和 $v_2 = (-\frac{1}{3},1)$。

$$
A = PDP^{-1} = \left\{ 
\begin{bmatrix} 
1 & 1 \\ 
-\frac{1}{3} & 1 
\end{bmatrix} 
\begin{bmatrix} 
5 & 0 \\ 
0 & 1 
\end{bmatrix} 
\begin{bmatrix} 
1 & 1 \\ 
-\frac{1}{3} & 1 
\end{bmatrix}^{-1}
\right\}.
$$


