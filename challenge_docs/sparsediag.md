# Sparse Diagonal Block Matrices

A diagonal matrix is a matrix where only the elements on the principal diagonal can be non-zero.

Let there be a matrix A, of dimensions nk x nk. A is made up of k x k non-overlapping diagonal matrices.

Example:

```
n, k = 2, 3

A = np.array(
    [[0, 0, 0,  3, 0, 0],
     [0, 1, 0,  0, 4, 0],
     [0, 0, 2,  0, 0, 5],

     [6, 0, 0,  9, 0,  0],
     [0, 7, 0,  0, 10, 0],
     [0, 0, 8,  0, 0, 11]]
)
```

Write a class `DiagonalBlockMatrix` that efficiently stores matrices like A, by **only saving the diagonal elements** (and discarding the zeros). That is, if `A` is an (nk, nk) matrix, DiagonalBlockMatrix will store (n, n, k) diagonals.

Some starter code has been given below:

```
import numpy as np

class DiagonalBlockMatrix():
    """Class for efficiently storing the nk x nk diagonal block matrices.

    Attributes
    ----------
    n : int
        How many blocks
    k : int
        Size of each diagonal matrix block
    diags: np.ndarray
        Diagonals of each block.
    """
    def __init__(self, A: np.ndarray, n: int, k: int) -> None:
        assert A.shape == (n * k, n * k), "Incorrect shape!"
        self.n = n
        self.k = k

        self.diag = None  # Your task is to store A's block diagonal values in self.diag,
                          # which will be an (n, n, k) array of block diagonals
        
        #####################
        # YOUR SOLUTION HERE
        #####################

    def __repr__(self):
        return f"{self.__class__.__name__}(n={self.n}, k={self.k}, diags=\n{self.diags})"
```

Example usage:

```
n, k = 2, 3

A = np.array(
    [[0, 0, 0,  3, 0, 0],
     [0, 1, 0,  0, 4, 0],
     [0, 0, 2,  0, 0, 5],

     [6, 0, 0,  9, 0,  0],
     [0, 7, 0,  0, 10, 0],
     [0, 0, 8,  0, 0, 11]]
)

>>> DiagonalBlockMatrix(A, n, k)

DiagonalBlockMatrix(n=2, k=3, diags=
[[[ 0  1  2]
  [ 3  4  5]]

 [[ 6  7  8]
  [ 9 10 11]]])

```

Now write a function `sparse_matmul` that takes two `DiagonalBlockMatrix` objects `A` and `B` and efficiently computes the matrix multiplication between them. `A` and `B` also must have the same `n` and `k`; they are both square matrices and have the same shape.

The result should also be a `DiagonalBlockMatrix` object.

(i.e. it is possible to compute C = A x B from the diagonal values of the blocks only.)
```
def sparse_matmul(A, B):

    #####################
    # YOUR SOLUTION HERE
    #####################
    pass
```

Example usage:

```
n, k =  2, 3
X = np.array(
    [[0, 0, 0,  3, 0, 0],
     [0, 1, 0,  0, 4, 0],
     [0, 0, 2,  0, 0, 5],

     [6, 0, 0,  9, 0,  0],
     [0, 7, 0,  0, 10, 0],
     [0, 0, 8,  0, 0, 11]]
)
Y = 2 * X

A = DiagonalBlockMatrix(X, n, k)
B = DiagonalBlockMatrix(Y, n, k)

>>> sparse_matmul(A, B)

DiagonalBlockMatrix(n=2, k=3, diags=
[[[ 36  58  88]
  [ 54  88 130]]

 [[108 154 208]
  [198 256 322]]])

# verify

>>> X @ Y

array([[ 36,  0,  0,    54,  0,  0],
       [  0, 58,  0,     0, 88,  0],
       [  0,  0, 88,     0,  0,130],

       [108,  0,  0,   198,  0,  0],
       [  0,154,  0,     0,256,  0],
       [  0,  0,208,     0,  0,322]])
```
(Feel free to import any additional library if necessary.)

<details>
  <summary> [Bonus] </summary>
  
    It is possible to solve this in a vectorized way, without any for loops.
  
</details>