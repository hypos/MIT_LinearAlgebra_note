怎么求解一阶方程？

怎么求解一阶导数？

怎么求解__常系数线性方程__？

将它们__转换__成__线性代数__问题的思路是__常系数线性方程解__是__指数形式__的。如果找一个__指数形式__，得找到__指数__是多少？及它的__系数__是多少？然后就是__线性__的活了， 这会和__矩阵的乘幂__完全平行

---

> 例：微分方程
> $$
> \frac{\mathrm du_1}{\mathrm dt} = -u_1+2u_2\\
> \frac{\mathrm du_2}{\mathrm dt} = u_1-2u_2\\
> \to A=\begin{bmatrix}-1&2\\1&-2\end{bmatrix}
> $$
> 初始值$u(0)=\begin{bmatrix}1\\0\end{bmatrix}$ 
> $$
> A=\begin{bmatrix}-1&2\\1&-2\end{bmatrix} \\
> 
> \begin{align}
> 	\to\begin{vmatrix}A-\lambda I\end{vmatrix}
> 		&=\begin{vmatrix}-1-\lambda&2\\1&-2-\lambda\end{vmatrix}\\
> 		0&=ad-bc \\
> 		0&= (-1-\lambda)(-2-\lambda)-2 \\
> 		0&=2+\lambda+2\lambda+\lambda^2-2\\
> 		0&=\lambda^2+3\lambda \\
> 		0&=\lambda(\lambda+3)\\
> \end{align}\\
> 
> \to \lambda_1=0;\lambda_2=-3
> $$
> $\lambda = -3$ 
> $$
> \begin{align}
> 	A\lambda x & = \begin{bmatrix}-1-(-3)&2\\1&-2-(-3)\end{bmatrix}
> 				   \begin{bmatrix}x_1\\x_2\end{bmatrix} \\
> 			 0 & = \begin{bmatrix}2&2\\1&1\end{bmatrix}
> 				   \begin{bmatrix}x_1\\x_2\end{bmatrix} \\
>              0 & = \begin{bmatrix}2x_1+2x_2\\x_1+x_2\end{bmatrix}
> \end{align}\\
> \to \begin{cases}2x_1+2x_2=0\\x_1+x_2=0\end{cases} 
> \to x_1=-x_2
> $$
>
>
> $\lambda = 0$ 
> $$
> \begin{align}   
> 	A\lambda x & = \begin{bmatrix}-1&2\\1&-2\end{bmatrix}                   						   \begin{bmatrix}x_1\\x_2\end{bmatrix} \\                     
>    			 0 & = \begin{bmatrix}-x_1+2x_2\\x_1-2x_2\end{bmatrix}
> \end{align}\\
> 
> \to
> 	\begin{cases}-x_1+2x_2=0\\x_1-2x_2=0\end{cases}
> $$
>
> $$
> \to
>     \begin{cases}
>         \begin{align}
>             -x_1+2x_2 &= x_1-2x_2\\
>             -2x_1&=-4x_2 \\
>             x_1&=2x_2
>         \end{align}
>     \end{cases}
> $$
>
> $$
> x_1=\begin{bmatrix}2\\1\end{bmatrix}\\
> 
> Ax_1=\lambda_1x_1 
> 	\to 
> 		\begin{bmatrix}-1&2\\1&-2\end{bmatrix}\begin{bmatrix}2\\1\end{bmatrix}=
> 		0\begin{bmatrix}2\\1\end{bmatrix}
> 	\to
> 		\begin{bmatrix}-1\times2+2\times1 = 0\\1\times2+-2\times1=0\end{bmatrix}=
> 		\begin{bmatrix}0\times2=0\\0\times1=0\end{bmatrix}\\
> 		
> x_2=\begin{bmatrix}1\\-1\end{bmatrix}\\
> 
> Ax_2=\lambda_2x_2 
> 	\to
> 		\begin{bmatrix}-1&2\\1&-2\end{bmatrix}\begin{bmatrix}1\\-1\end{bmatrix}=
> 		-3\begin{bmatrix}1\\-1\end{bmatrix}
> 	\to
> 		\begin{bmatrix}-1\times1+2\times-1 = -3\\1\times1+-2\times-1=3\end{bmatrix}=
> 		\begin{bmatrix}-3\times1=-3\\-3\times-1=3\end{bmatrix}
> $$
>
>
>
> 函数$u$，自变量$t$ 
>
> $$
> u(t)=c_1e^{\lambda_1t}+c_2e^{\lambda_2t}\approx c_1\lambda_1^kx_1+c_2\lambda_2^kx_2
> $$
>
> 导数
> $$
> \frac{\mathrm du}{\mathrm dt} = \lambda_1e^{\lambda_1t}x_1\\
> Au=Ae^{\lambda_1t}x_1 \\ 
> \frac{\mathrm du}{\mathrm dt} = Au
> \to \lambda_1x_1 = Ax_1\\
> 
> u(t) \underbrace{=}_{将x_1,x_2代入得}
> 		c_1e^{\lambda_1t}\begin{bmatrix}2\\1\end{bmatrix}+
> 		c_2e^{\lambda_2t}\begin{bmatrix}1\\-1\end{bmatrix}
> 		\underbrace{=}_{将\lambda_1,\lambda_2代入得}
> 		c_1e^0\begin{bmatrix}2\\1\end{bmatrix}+
> 		c_2e^{-3t}\begin{bmatrix}1\\-1\end{bmatrix}\\
> 		
> t=0;u(0) =	c_1e^0\begin{bmatrix}2\\1\end{bmatrix}+
> 			c_2e^0\begin{bmatrix}1\\-1\end{bmatrix}=
> 			\begin{bmatrix}1\\0\end{bmatrix}\\
> \to 
> 	\begin{cases}
> 		2c_1+c_2=1\\
> 		c_1-c_2=0
> 	\end{cases}\\
> 	
> \to c_1=c_2=\frac{1}{3}
> $$
>
>
>
>
>

