# 大纲

- 总目标，总的消元公式A=LU
- 讨论一些矩阵的乘法（消元矩阵的乘法）

---

$$
\underbrace{\begin{bmatrix}1&0\\-4&1\end{bmatrix}}_{E_{21}}
\underbrace{\begin{bmatrix}2&1\\8&7\end{bmatrix}}_A = 
\underbrace{\begin{bmatrix}2&1\\0&3\end{bmatrix}}_U
$$

$$
\underbrace{\begin{bmatrix}2&1\\8&7\end{bmatrix}}_A =
\underbrace{\begin{bmatrix}1&0\\4&1\end{bmatrix}}_{L} 
\underbrace{\begin{bmatrix}2&1\\0&3\end{bmatrix}}_U
$$

$$
E_{21}A=U
\to
E_{21}^{-1}(E_{21}A)=E_{21}^{-1}U
\to
(E_{21}^{-1}E_{21})A=E_{21}^{-1}U
\to
IA=LU
$$
L为下三角阵，D为对角阵，U为上三角阵
$$
\underbrace{\begin{bmatrix}1&0\\4&1\end{bmatrix}}_{L} 
\underbrace{\begin{bmatrix}2&0\\0&3\end{bmatrix}}_{D} 
\underbrace{\begin{bmatrix}1&1/2\\0&1\end{bmatrix}}_{U}
$$
#### 乘积的逆

两矩阵相称，且它们的逆已知，那么AB的逆是什么？

$AA^{-1} = I=A^{-1}A$ 

$(AB)(B^{-1}A^{-1})=I=(B^{-1}A^{-1})(AB)$ 

$(AA^{-1})^T=I=(A^{-1})^TA^T$ 

$(A^{-1})^T = (A^T)^{-1}$ 

#### $m_{3*3}$的情况：忽略换行
$$
E_{32}E_{31}E_{21}A=EA=U
\to
A=E_{21}^{-1}E_{31}^{-1}E_{32}^{-1}U=LU
$$
$A=LU$如果不存在行互换，消元乘数（即消元步骤中需要乘以并减去的那个倍数）可以直接写入L中，这是关于消元的全新认识，以矩阵形式进行消元更深刻的认识，令人着迷的是E逆的反顺序乘积，轻松得到L.

#### 置换矩阵（P）

$$
I=\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}
$$
$$
P_{12}=
    \begin{bmatrix}
        0&1&0\\
        1&0&0\\
        0&0&1
    \end{bmatrix},
P_{13}=
    \begin{bmatrix}
        0&0&1\\
        0&1&0\\
        1&0&0
    \end{bmatrix}...
$$

得到交换任意几行的置换阵，只需要互换单位阵中的相应行即可 ，3x3的置换阵有6个，包括单位阵。

特性：$P^{-1}=P^T$  



__微积分考虑的是连续情况下的“求和”，线性代数是离散的__ 