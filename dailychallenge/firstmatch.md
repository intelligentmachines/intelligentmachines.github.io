# First Match

Let there be two 2-D arrays, `A` and `B`, of shape `(R, N)` and `(R, M)` respectively. `A` and `B` have identical number of rows but different number of columns.

For each column in `B`, find the index of the *first matching column* in `A` -- or return `0` if no matches are found for that column.

## Example

```
A = np.array([
    [2, 1, 2, 6, 3, 3, 6, 8, 2, 2],
    [3, 2, 7, 4, 5, 6, 1, 5, 7, 2]
])

B = np.array([
    [1, 2, 1],
    [2, 7, 0]
])

>>> first_match(A, B)
array([1, 2, 0])
```

The first column in `B`, `(1, 2)`, appears at index `1` among the columns of `A`. Again, the second column in `B`, `(2, 7)`, appears at multiple positions in the columns of `A` -- at indices `2` and `8`. So the result for the second column is the first match, `2`. Lastly, the third column in `B`, `(1, 0)`, has no matches with any columns in `A`, thus getting a `0` as a result.



## Getting Started

Here is some boilerplate to help you get started.

```
import numpy as np


def first_match(A: np.ndarray, B: np.ndarray) -> np.ndarray:
    """Given an array A of shape (R, N), and an array B of shape (R, M), for each column in
    B, find the index of the first match in the columns of A. If no matches are found for a
    particular column, return 0 for that column.

    Parameters
    ----------
    A : np.ndarray
        2-D array of shape (R, N).
    B : np.ndarray
        2-D array of shape (R, M).

    Returns
    -------
    np.ndarray
        Output 1-D array of shape (M,).
    """

    assert A.ndim == 2 and B.ndim == 2, f"A and B must both be 2D arrays, but got dims {A.ndim} and {B.ndim}"
    assert A.shape[0] == B.shape[0], f"Number of rows must be same, but found {A.shape[0]} and {B.shape[0]}"


    #####################
    # YOUR SOLUTION HERE
    #####################

```

<details>
  <summary> Bonus </summary>
  
    While you can loop over and solve this problem, bonus points if you can do this in a single line of code!
  
</details>

## Solutions

Will be posted at a later time.