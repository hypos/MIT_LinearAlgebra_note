目标：$AX=b$,有解或无解。有解包括唯一解或多解

---

方程组左侧各行的线性组合得到0，那么右侧常数相同组合必然也等于0

$$
\underbrace{
    \left[\begin{array}{cccc|c} 
        1&2&2&2&b_{1}\\2&4&6&8&b_{2}\\
        3&6&8&10&b_{3}\end{array}
    \right]
}_{A}\\
\rightarrow
    \left[\begin{array}{cccc|c} 	
        1&2&2&2&b_{1}\\0&0&2&4&b_{2}-2b_{1}\\
        0&0&2&4&b_{3}-3b_{1}\end{array}
    \right]\\
\rightarrow
    \left[\begin{array}{cccc|c} 
        1&2&2&2&b_{1}\\0&0&2&4&b_{2}-2b_{1}\\
        0&0&0&0&b_{3}-3b_{1}-b_{2}-2b_{1}\end{array}
    \right]
\rightarrow 
    \left[\begin{array}{cccc|c} 
        1&2&2&2&b_{1}\\0&0&2&4&b_{2}-2b_{1}\\
        0&0&0&0&b_{3}-b_{2}-b_{1}\end{array}
    \right]
$$
__可解性：__b满足什么条件，才能让$AX=b$总有解？

- 从列向量看，当b属于A的列空间时，也就是b必须是A各列的线性组合

- 从行向量看，A各行的线性组合得到零行，b中元素的同样组合必然也是零


 求$AX=b$的所有解：

​	1.将所有自变量设为0，解出主变量（列二，列四同时为0），得到剔除后的方程：

​		   $$\left \{ \begin{array}{} x_1+2x_3=1 \\ 2x_3=3\end{array} \right.\Rightarrow \left\{\begin{array}{1}x_1=-2\\x_3=3/2 \end{array} \right\}$$  

 	 	 $X$特解为向量$(-2，0，3/2)$ 

​	2.零空间的所有$X$ 

1+2为方程的所有解。



$$
X_{p}+X_{n}=A\\
\begin{eqnarray*}
AX_P=b \tag{1.1} \\
AX_n=0 \tag{1.2}
\end{eqnarray*}\\
(1.1)+(1.2) = A(X_P+X_n)=b+0=b\\

X_{complete}=
\underbrace{\begin{bmatrix}-2\\0\\3/2\\0\end{bmatrix}}_{X_{p}}+
\underbrace{
    C_{1}\begin{bmatrix}-2\\1\\0\\0\end{bmatrix}+
    C_{2}\begin{bmatrix}2\\0\\-2\\1\end{bmatrix}
}_{X_{n}}
$$

$X_n$为穿过$X_p$的二维平面，由子空间从原点平移上来得到的平面。



考虑"秩"$r$的$m*n$矩阵$A$

- $r$与$m$的关系，$r \leq m$ 
- $r$与$n$的关系，$r \leq n$  

__首先讨论：__

 列满秩的情况$r=n$,没有自由变量，$N(A) = \{0向量\}​$ 

$AX=b$的解，$X=X_p$有唯一解或无解。

例：

$$
A=\begin{bmatrix}1&3\\2&1\\6&1\\5&1\end{bmatrix} R=\begin{bmatrix}1&0\\0&1\\0&0\\0&0\end{bmatrix}
$$

唯一解：$b=A_{col_{1}}+A{col_{2}}$ 

行满秩的情况$r=m$,消元时，不会出现零行$AX=b$,对任意$b$,$AX=b$都有解

自由变量的个数$n-r$满秩情况总有解，总共$n-m​$个自由变量

$$
A=\begin{bmatrix}1&2&6&5\\3&1&1&1\end{bmatrix}\\
R=\begin{bmatrix}1&0&0&0\\0&1&0&0\end{bmatrix}
$$



__总结:__

$r=m=n$ 得到可逆阵

$A=\begin{bmatrix}1&2\\3&1\end{bmatrix} R=I$ 有唯一解



$r=n<m$

$R=\begin{bmatrix}I\\0\end{bmatrix}​$ 可能有0个或1个解



$r=n<m$

$R=\begin{bmatrix}I&F\end{bmatrix}(I与F可能混搭，可能 F在前面)$ 总有解，无穷多解



$r<m,r<n$

$R=\begin{bmatrix}I&F\\0&0\end{bmatrix}$ 要么无解，要么无穷多解



__矩阵的秩，决定了方程组解的数目，秩$r$包含所有信息，除了具体计算结果之外__ 