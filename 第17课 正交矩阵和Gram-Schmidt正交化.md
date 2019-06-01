正交空间：行空间和零空间

__正交基__和__正交矩阵__“_标准正交_”，__标准__表示长度是__单位长度__ 

标准正交基怎样让情况变好？

- 它让整个计算方便了很多，
- 许多数值线性代数都建立在__标准正交向量__的基础上
- 容易操控，从不上溢或下溢


正交矩阵一般用$Q$表示：
$$
Q=\begin{bmatrix}\vdots&\vdots&\vdots \\ q_1&q_2&q_3 \\\vdots&\vdots&\vdots\end{bmatrix}
$$

$$
Q^TQ = 
\underbrace{
	\begin{bmatrix}\dots&q_1^T&\dots\\\dots&q_2^T&\dots\\\dots&q_3^T&\dots\end{bmatrix}
}_{Q^T}
\underbrace{
	\begin{bmatrix}\vdots&\vdots&\vdots\\ q_1&q_2&q_3\\\vdots&\vdots&\vdots\end{bmatrix}
}_{Q}=
\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{I}
$$
__性质：__ 

- $q_i^Tq_j=0$

- 如果$Q$是方阵，$Q^TQ=I \rightarrow Q^T = Q^{-1}$ 

__标准正交__且为__方阵__才叫__正交矩阵__ 



例：
$$
\underbrace{\begin{bmatrix}0&0&1\\1&0&0\\0&1&0\end{bmatrix}}_{Q}
\underbrace{\begin{bmatrix}0&1&0\\0&0&1\\1&0&0\end{bmatrix}}_{Q^T}=
\underbrace{\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}_{I} \\

\underbrace{\begin{bmatrix}cos\theta&-sin\theta\\-sin\theta&cos\theta\end{bmatrix}}_{Q}
\underbrace{\begin{bmatrix}cos\theta&sin\theta\\-sin\theta&cos\theta\end{bmatrix}}_{Q^T}=
\underbrace{\begin{bmatrix}1&0\\0&1\end{bmatrix}}_{I}
$$





令$Q$表示标准正交列向量的矩阵，假设投影到列空间中，其投影矩阵是什么？
$$
P=Q(\underbrace{Q^TQ}_{I})^{-1}Q^T= (Q\underbrace{Q^T)(Q}_{I}Q^T) = QQ^T \\ 
(Q^TQ)^{-1} = Q^TQ\\
Q是方阵\rightarrow QQ^T=I
$$
标准公式：
$$
A^TA\hat{x}=A^Tb\\
A用Q来代替 \rightarrow Q^TQ\hat{x}=Q^Tb \rightarrow I\hat{x}=Q^Tb \\
\rightarrow \underbrace{\hat{x}_i = q_i^Tb}_{*重要方程*}
$$



格拉姆-施密特正交化法，使列向量标准正交，缺点在于，这些列向量都必须是单位向量。

> 例：$\vec a,\vec b$线性无关，得到$\underbrace{q_1,q_2}_{标准正交化向量}$ 
>
> 将$\vec a$与$\vec b$,标准正交化成$q_1,q_2$，先求正交$A$和$B$，再到标准正交化$q_1,q_2$，(__除以自身长度__)  
>
> 施密特：$q_1=\frac{A}{\|A\|},q_2=\frac{B}{\|B\|},q_3=\frac{C}{\|C\|}$ 
>
> 格拉姆：
> $$
> A=a \\
> B=b-\underbrace{\frac{A^Tb}{A^TA}A}_{A上的分量} \\
> \rightarrow A^TB=A^T(b-\frac{A^Tb}{A^TA}A)=A^Tb-\frac{A^Tb}{A^TA}A^TA = A^Tb-A^Tb \\
> 
> C= c-
> 	\underbrace{\frac{A^Tc}{A^TA}A}_{A上的分量}-
> 	\underbrace{\frac{B^Tc}{B^TB}B}_{B上的分量}
> $$
>
>



> 例：已知两个向量，求格拉姆--施密特标准正交基的__矩阵表示__ 
> $$
> a=\begin{bmatrix}1\\1\\1\end{bmatrix};
> b=\begin{bmatrix}1\\0\\2\end{bmatrix};
> B=\underbrace{\begin{bmatrix}1\\0\\2\end{bmatrix}}_{b} - 
> 	\frac{3}{3}\underbrace{\begin{bmatrix}1\\1\\1\end{bmatrix}}_{A} = 
> 	\begin{bmatrix}0\\-1\\1\end{bmatrix}\\
> A_N=\begin{bmatrix}1&1\\1&0\\1&2\end{bmatrix};
> Q=\begin{bmatrix}q_1&q_2\end{bmatrix}=
>     \begin{bmatrix}
>         \frac{1}{\sqrt3} & 0\\ 
>         \frac{1}{\sqrt{3}}&-\frac{1}{\sqrt{2}} \\
>         \frac{1}{\sqrt{3}}&\frac{1}{\sqrt{2}}
>     \end{bmatrix};
> A_M=\begin{bmatrix}1&0\\1&-1\\1&1\end{bmatrix}
> $$
> $A_N$是原空间很不错的__基组__，还__不够好__，__不正交__ 
>
> $A_M$是__正交基组__，还__不够好__，__不标准__
>
> Q是__标准正交基__，__投影__和__所有__想做的__计算__都会变得很__简单__ 
> $$
> A=LU;A=QR\\
> \underbrace{\begin{bmatrix}\vdots&\vdots\\a&b\\\vdots&\vdots\end{bmatrix}}_{A}=
> \underbrace{\begin{bmatrix}\vdots&vdots\\q_1&q_2\\\vdots&\vdots\end{bmatrix}}_{Q}
> \underbrace{\begin{bmatrix}a_1^Tq_1&b_1^Tq_1\\a_1^Tq_2&b_2^Tq_2\end{bmatrix}}_{R}\\
> R是一个上三角阵\\
> a_1^Tq_2=0
> $$
>
>



