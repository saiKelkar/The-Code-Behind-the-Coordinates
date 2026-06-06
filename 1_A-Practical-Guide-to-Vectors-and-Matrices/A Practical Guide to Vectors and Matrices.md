**Sec. #1: Vectors (Rows and Columns) + The difference between vectors and matrices**
Vectors are usually in the form of rows or columns.
Matrices are usually square or rectangular (more than 1 row or column), whereas vectors are a singular row or column (special case of matrices).
In physics, vectors are usually called line with direction, but in math, it's just a list of numbers either along a row or a column. 

```
# row and column vector
row_vec = np.array([4, 2])
col_vec = np.array([ [-2], [3] ])

print("row vector:", row_vec)
print("column vector:\n", col_vec)

display(Math(sym.latex(sym.simplify(row_vec))))
display(Math(sym.latex(sym.simplify(col_vec))))
```

**Sec. #2: Linear Combinations (Adding vectors and Multiplying scalars)**
One vector (cv) = if we wary c, the combinations fill the 1D line running through the origin (unless v is a zero vector).
Two vectors (cv + dw) = most cases: fill the flat 2D space
special case: if w is a multiple of v, then lines overlap and they only fill the 1D space.
Three vectors (cv + dw + ez) = most cases: they fill the entire 3D space
special case: (2D) if the third vector z lies flat on the plane formed by v and w, they are trapped in a 2D plane
(1D) if all three points along the same path, they are trapped on a 1D plane.

c is a scalar and v a vector, so this is scalar multiplication
when we write something as cv + dw, we are multiplying scalars first with v and w and then adding two vectors. 
This is called linear combination. 

```
v = np.array([.5, 1])
s = [1, -.5, 2, .5]

for si in s:
	sv = si * v
	plt.plot([0, sv[0]], [0, sv[1]], 'o-', linewidth=3, label=f'$\\lambda$ = {si}')
	
plt.axis('square')
plt.axis([-3, 3, -3, 3])
plt.grid()
plt.legend()
plt.show()
```

```
v1 = np.array([-1, 2])
v2 = np.array([1, 1])

v3a = v1 + v2
v3b = np.add(v1, v2)

print(v3a, v3b)
```
**Sec. #3: Dot Product**
Dot product of two vectors = v . w
If a column vector v has elements $v_1$ and $v_2$ and another column vector w has elements $w_1$ and $w_2$, the dot product here is, v . w = $v_1w_1 + v_2w_2$ 
For an n-dimensional space (generalization), we multiply it to the very end ($\dots v_nw_n$)

The dot product of v . v tells us the squared length.
Where as a unit vector has the length as 1.
Perpendicular vectors have dot product as 0, v . w = 0
And if the vectors aren't perpendicular, 
$$\cos \theta = \frac{\mathbf{v} \cdot \mathbf{w}}{\|\mathbf{v}\| \|\mathbf{w}\|}$$

There are two important inequalities here:
1. Schwartz inequality
2. Triangle inequality

```
m_1 = np.arange(10, 20, 3)
m_2 = np.arange(5, 15, 3)

d_p = np.dot(m_1, m_2)
print(d_p)
```

**Sec. #4: Matrix Multiplication**
Matrices are usually defined with upper case letters such as A, M, R, etc. 
They have m rows and n columns

There are various types of matrices, such as identity matrix, diagonal matrix, triangular matrix, etc. 

```
A = np.random.randn(3, 2)
B = np.random.randn(2, 4)

C = A @ B
D = np.dot(A, B)

print(np.shape(C))
print(C)

print(np.shape D)
print(D)
```