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
