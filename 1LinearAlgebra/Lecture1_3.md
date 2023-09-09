## Lecture 1 求解线性方程组、方程组的几何解释

 ##### 1. n linear equations, n unknows

设想在n个线性方程组中，存在n个未知数，构造方程组：A**x** = b
$$
2x+3y=5
\\
3x-y=2
\\

A = \begin{bmatrix} 2 & 3 \\ 3 & -1 \end{bmatrix}
\quad
b = \begin{bmatrix} 5 \\ 2 \end{bmatrix}
\quad
x = \begin{bmatrix} x \\ y \end{bmatrix}
\quad
$$

 ##### 2. Row picture

行图像：以二维为例，则可以将解视为直线相交（2equations 2 unkonws）

如上例所示，方程组的解可以视为两条直线所在交点的坐标值

 ##### 3. Column picture

列图像：Linear combination of columns(vector)

注意：方程是否有解取决于这些Vectors能否生成整个N-demenssion

如上例所示，方程组的解可视为向量(2, 3)和向量(3, -1)可以怎样线性组合成(5, 2)

 ##### 4. Matrix Form

A**x** = b，矩阵A与向量b相乘，可以视为A的每一列与向量b的每一个对应值相乘，即Ax is a combination of columns of A

如上例所示，A中的每一个列向量与x中每一个值相乘（线性组合）即可得到结果b



## Lecture2 矩阵消元

##### 1. elimination

顺序消元->得到上三角矩阵U

注意：在消元过程中主元不能为0，如果0占据了主元位置，则行交换

##### 2. augmented matrix

对增广矩阵进行消元

##### 3. 回代

得到U**x** = c，并解方程

##### 4. 矩阵变换

①线性变换——初等矩阵

一个1*3的行向量，与矩阵A相乘，可视为第n列与A的第n行相乘再相加的结果；因此我们思考一个怎样的3X3矩阵与已知的A相乘能变成U？

我们把待求矩阵视为3个行向量，第n个行向量是矩阵A通过第n行的线性相加得到U的第n行；此处的待求矩阵称为初等矩阵

②行交换——置换矩阵

设想一个矩阵，若交换他的其中两行，是否可以左乘一个矩阵完成这个操作？这就是置换矩阵需要完成的事情

③列交换——置换矩阵

设想一个矩阵，若交换他的其中两列，是否可以右乘一个矩阵完成这个操作？这就是置换矩阵需要完成的事情

**总结：**矩阵乘法的几种方法

①行：行与矩阵的线性相加

②列：列的线性相加

③元素：Cij=∑Ai*Bj

##### 5. 矩阵乘法的重要性质

①结合律 

注意：没有交换律

##### 6. Inverses

$$
E^{-1}*E=I
$$

## Lecture3 乘法和逆矩阵

##### 1. Matrix multiplication

A*B需要确保A的列数等于B的行数

①行列法：用A的整行乘以B的整列，并相加得到元素值

②看列法：用矩阵A分别乘以B的每一列，得到C的每一列；因此C的每一列都可以看作为**A每一列**的的线性组合

③看行法：用矩阵A的每一行分别乘以B，得到C的每一行，因此C的每一行都可以看作为**B每一行**的线性组合

④列行法：AB=sum(A.col*B.row)，注意这里的行和列的编号要是一样的！

拓展：分块矩阵，可将块视作一个元素，使用方法①求解

##### 2. Inverses of A(square matrix) AB A^T

$$
A^{-1}*A=I=A*A^{-1}
$$

①矩阵可逆：non-singlar（非0），其列的线性组合不能为0





##### 3. Gauss-Jordan find A^(-1)：slove 2 equations at onece

思想：借助增广矩阵，采用消元思想，将[A | I]变为[A | A^(-1)]
