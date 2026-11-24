# Experiment 1: Exploring NumPy and Pandas

## Aim

To understand the use of NumPy and Pandas for performing basic data
manipulation and analysis in Python.

## Algorithm

1.  Import the NumPy library for matrix and numerical operations.
2.  Define a two-dimensional square matrix `A` and a vector `b`.
3.  Compute the transpose of matrix `A` to interchange rows and columns.
4.  Calculate the inverse of matrix `A` using `np.linalg.inv(A)` (ensure
    `A` is non-singular).
5.  Solve the linear equation `A × x = b` using `np.linalg.solve(A, b)`.
6.  Perform eigen decomposition to find eigenvalues and eigenvectors
    using `np.linalg.eig(A)`.
7.  Display the results for the matrix, transpose, inverse, solution
    vector, and eigenvalues.
8.  End the program.

## Formulas / Theory

-   **Transpose:** `Aᵀ` — interchange rows and columns.
-   **Inverse:** `A⁻¹ = adj(A) / |A|`, provided `det(A) ≠ 0`.
-   **Linear system:** `A × x = b  ⇒  x = A⁻¹b`.
-   **Eigen decomposition:** `A v = λ v`, where `λ` is an eigenvalue and
    `v` is an eigenvector.

## Coding

```python
import numpy as np

# Step 2: Define matrix A and vector b
A = np.array([[4, 2],
              [1, 3]])
b = np.array([10, 8])

print("Matrix A:\n", A)

# Step 3: Transpose
print("\nTranspose of A:\n", A.T)

# Step 4: Inverse (A must be non-singular)
print("\nDeterminant of A:", round(np.linalg.det(A), 2))
A_inv = np.linalg.inv(A)
print("\nInverse of A:\n", A_inv)

# Step 5: Solve A x = b
x = np.linalg.solve(A, b)
print("\nSolution vector x:", x)

# Step 6: Eigen decomposition
eigenvalues, eigenvectors = np.linalg.eig(A)
print("\nEigenvalues:", eigenvalues)
print("\nEigenvectors:\n", eigenvectors)
```

##  Output


Matrix A:
 [[4 2]
 [1 3]]

Transpose of A:
 [[4 1]
 [2 3]]

Determinant of A: 10.0

Inverse of A:
 [[ 0.3 -0.2]
 [-0.1  0.4]]

Solution vector x: [1.4 2.2]

Eigenvalues: [5. 2.]

Eigenvectors:
 [[ 0.89442719 -0.70710678]
 [ 0.4472136   0.70710678]]


> Note: the order and sign of the eigenvalues and eigenvectors may differ
> slightly depending on the NumPy version and platform.

## Result

The program was executed successfully. The transpose, inverse, solution of
the linear system and the eigenvalues and eigenvectors of the matrix were
computed using NumPy.

-   Transpose of `A` interchanges its rows and columns.
-   Since `det(A) = 10 ≠ 0`, the inverse `A⁻¹` exists.
-   The solution of `A x = b` is `x = [1.4, 2.2]`. Check:
    `4(1.4) + 2(2.2) = 10` and `1(1.4) + 3(2.2) = 8`.
-   The eigenvalues are `λ = 5` and `λ = 2`, which satisfy `A v = λ v`.

Thus, NumPy's linear algebra functions can be used to perform basic matrix
operations and analysis in Python.
