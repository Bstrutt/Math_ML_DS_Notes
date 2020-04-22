# Matrix Decompositions

Haven't tried this before but I assume it's more linear algebra in essence. Eigenvalues
and determinants incoming.

### Determinant and Trace

* Determinant
  * Only defined for square matrices
  * det(A) or |A|
  * Simply maps a matrix onto a real number
Determinants can be used to prove invertibility. If Det(A) != 0 

For triangular matrices the determinant is the product of diagonal elements

Example 4.2 is a neat look at determinants giving volume to parallelograms.

* Laplace Expansion
  * Recursively computing det of an n by n matrix by computing the det of (n-1) by (n-1) matrices. Finally we compute det of 2 by 2 matrices.
  * This is a sick expansion. The math is tight.

Determinants have the following properties when A is a real square matrix

* det(AB) = det(A) * det(B)
* det(A) = det(A<sup>T</sup>)
* if A is inveritble then det(A<sup>-1</sup>) = 1/(det(A))
* Similar matrices have the same determinant {A = S<sup>-1</sup>AS}
* linearly combining rows/columns does not change det
* Multiplying a row/col with a scalar, scales det by the scalar
* Swapping rows/cols changes the sign of the det

To very easily compute det we can use a special Gaussian Elimination to get the matrix into triangular form and multiply the diagonal elements.

The trace of a square matrix is the sum of its diagonal elements and has the following properties

* trace(A+B) = trace(A) + trace(B)
* trace(sA) = (s)trace(A), s is scalar
* trace(I) = n where n is dimension
* trace(AB) = trace(BA) for A n by k and B k by n

4.21 has a good demo of basis changing to find traces of mappings

* Characteristic Polynomial
  * Subtract a scaled identity matrix, I, from the original matrix A. Take the determinant of the result. The coefficients of the equation found after taking the determinant make up your characteristic polynomial.

This is going to be a little free-form on Eigen values while I read through them more. I may come back to clarify or pretty things up.

Eigen values and their matrices are characteristic values for matrices. An eigen value is one of possibly many values that can be multiplied by a vector to produce the same result as multiplying the same vector by our original matrix. The values that accomplish this are known as our Original Matrix's eigenvalues. Eigen values are always one of the roots of the characteristic polynomial of the original matrix. That is why to find eigen values in class we found the characteristic polynomial and then its roots. 

The set of all eigenvectors of an original matrix which are associated with an eigenvalue spans of subspace called an eigenspace of the original matrix with respect to that eigenvalue. The set of all eigenVALUES is called the eigenspectrum. Matrices and their transpose have the same eigenvalues but not the same eigenvectors. Eigenvalues, determinants, and trace are all invariant under basis change. 

