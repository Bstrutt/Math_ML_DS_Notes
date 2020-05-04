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

### EigenValues and EigenVectors

This is going to be a little free-form on Eigen values while I read through them more. I may come back to clarify or pretty things up.

Eigen values and their matrices are characteristic values for matrices. An eigen value is one of possibly many eigen-values that can be multiplied by a certain vector to produce the same result as multiplying the same vector by our original matrix. The values that accomplish this are known as our Original Matrix's eigenvalues. Eigen values are always one of the roots of the characteristic polynomial of the original matrix. That is why to find eigen values in class we found the characteristic polynomial and then its roots. 

The set of all eigenvectors of an original matrix which are associated with an eigenvalue spans of subspace called an eigenspace of the original matrix with respect to that eigenvalue. The set of all eigenVALUES is called the eigenspectrum. Matrices and their transpose have the same eigenvalues but not the same eigenvectors. Eigenvalues, determinants, and trace are all invariant under basis change. 

The eigenvalues of an n by n matrix with n distinct eigenvalues are linearly independent which means that they form a basis of the real numbers. We get to be really mean to matrices here and call them defective if they have fewer than n linearly independent eigenvectors.

A neat little thing we can do to always get a symmetric positive SEMI-definite matrix is by A<sup>T</sup>A. ADDITIONALLY, if the rank of A, that is the max number of linearly independent rows/cols, is n then our resulting matrix is symmetric positive DEFINITE.

The determinant of the matrix is the product of its eigenvalues and the trace is the sum of its eigenvalues. This is a tight little sum-up of eigenvalues. I like that it all sort of comes together into one.

### Cholesky Decomposition

A square root equivalent operation on symmetric positive definite matrices. Useful in machine learning. In learning about LU decomposition I have come across something similar to this. (As an aside transpose is mirroring along the diagonal, I just thought of the word mirroring and didn't want to not write this down though it doesn't fit here)

A = LL<sup>T</sup>

Where L is a lower triangular matrix with positive diagonals. L is unique. L is called the Cholesky factor of A. Since L is a triangular matrix the determinant is the product of its diagonal entries.

### Eigendecomposition and Diagonalization

A matrix is diagonalizable if it is similar to a diagonal matrix. D =P<sup>-1</sup>AP. where A is our original and D is a diagonal matrix. Diagonalizing a matrix allows us to express the same linear mapping but in another basis which consists of eigenvectors of A. 

Eigendecomposition has a lot of caveats. D is a diagonal matrix whose entries are eigenvalues of A. This can only happen if the eigenvectors form a basis for the set of all real numbers.

Any symmetric matrix can always be diagonalized.

The motivation for finding diagonal matrices is that they can be raised to powers and have their determinants computed more efficiently than their original counter-parts (in most cases)

### Singular Value Decomposition

This is an important one so pay attention. The singular value decomp (SVD) is sometimes referred to as the fundamental theorem of linear algebra. It can be applied to all matrices and always exists. There's a nice paper by Kalman that goes over the details of the SVD. I think I'll read it.

A = U (sigma) V<sup>T</sup>

A is our rectangular matrix m by n, U is an orthogonal matrix m by m with columns 1-m, V is an orthogonal matrix n by n with column vectors 1-n, finally, Sigma is a unique m by n matrix with greater than 0 value for each diagonal entry and zero for each other entry. The diagonals of Sigma are called singular values and are ordered from largest at position (1,1) and proceeding smaller. U entries are the left-singular vectors, v entries are right singular vectors.

A superficial explanation is that our original matrix gets a basis change via U, then a scaling and reduction in dimensionality via Sigma, finally another basis change via  V<sup>T</sup>.

I'm gonna walk slowly through the explanation of the SVD because I want to understand it very well.

We have a transformation matrix L of a linear mapping from Real<sup>n</sup> to Real<sup>M</sup> with respect to the standard bases B of Real<sup>n</sup> and C of Real<sup>m</sup>. We also assume alternative bases B* and C* of Real<sup>n</sup> and Real<sup>m</sup> respectively.

Computing the SVD  of a matrix m by n is equivalent to computing the orthonormal bases of the respective codomains. From these bases we make our matrices U and V. Sigma has the same dimensions as our original matrix does.

I did a ton more notetaking on this subject in a different file. I read a paper specifically on the SVD and it was pretty eyeopening. It's located in the "Papers" directory.

### Matrix Approximation

The SVD allows us to represent A as a sum of low-rank matrices which gives us a matrix approximation which is cheaper to compute than the SVD.

