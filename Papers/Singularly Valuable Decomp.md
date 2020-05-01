# A Singularly Valuable Decomposition: The SVD of a matrix

This is a 2002 paper by Dan Kalman on singular value decomposition or SVD. I'm not yet comfortable with the grasp I have on SVD so reading this paper is an effort to improve that. I'm gonna try to summarize some of what is written here and throw in some analysis.

### Intro/Theory

* EVD
  * The eigenvalue decomposition 
  * Matrix A is symmetric, real n by n.
  * We have an orthogonal matrix V
    * Remember that orthogonal matrices are useful not only because we can get their inverse via transpose but also because they define mappings where angle and length is preserved.
  * Diagonal matrix D
  * A = VDV<sup>T</sup>
  
* SVD
  * Singular value decomposition
  * Matrix A is arbitrary m by n
  * The matrices U and V are orthogonal
    * More specifically U is m by m and V is n by n
  * Sigma is a diagonal matrix
    * Sigma is rectangular with the same dimensions (m by n) as A
  * A=USigmaV<sup>T</sup>
  
The next thing Kalman talks about is the fact that we can think about matrices as linear transformations. In the EVD when we have a matrix A (n by n) we have a transformation from the real numbers with n dimensions TO the real numbers with n dimensions. Since V is an orthonormal basis we can express vectors using this basis. 

Now we look at the SVD. Here we are transforming from real numbers in n dimensions to real numbers in m dimensions. Finding a natural basis for each of these is what we are doing when we get U and V. They are used to represent vectors in the n and m dimensions. Kalman says that from this perspective the SVD helps us to choose orthonormal bases so that the transformation is represented by a diagonal matrix.

But! How do we choose the bases V and U? By Av<sub>i</sub>=sigma<sub>i<sub>u<sub>i</sub>. Then we pick an orthonormal basis V for R<sup>n</sup> so that the first k elements span the row space of A and the remaining elements span the null space of A. THEN for each i we define u<sub>i</sub> to be a unit vector parallel to Av<sub>i</sub> and extend this to a basis for R<sup>m</sup>. 
  
Kalman mentions specifically here that there is no reason to expect the u's to be orthogonal. To me this doesn't make much sense because earlier he said that U was othogonal but I think he may explain that later.

The end of this first section is good for insights on the SVD. "the SVD encapsulates the most appropriate bases for the domain and range of the linear transformation defined by the matrix A" The relationship between these bases and the four fundamental subspaces associated with A is important. {The 4 subspaves are the range, nullspace, and the orthogonal complement of each} {The nullspace is the collection of vectors x such that Ax=0 and x != 0.} There's a nice picture of all this at the start of page 4.

It is common computationally to computoe the SVD for the purpose of finding the EVD without having to compute eigenvalues or eigenvectors. 

Something I think is important but hasn't really fit anywhere is this.

The right singular vectors must be the eigenvectors of A<sup>T</sup>

The left singular vectors must be the eigenvectors of AA<sup>T</sup>

Additionally, the singular values are the square roots of the nonzero eigenvalues which are common to the two matrices. 

To end this section Kalman mentions a bunch of different ways that SVD can be represented. It's kinda interesting but I don't see how each is useful yet. 

### Applications

SVD finds use in large or high dimensional matrices and a bunch of other places. Here's a short list of some places.

* Computing the EVD of A<sup>T</sup>A for principal component analysis and covariance matrices.
  * The A<sup>T</sup>A computation will lead to significant decrease in accuracy of results.
  * The SVD computaiton operates directly on A getting the eigenvectors and eigenvalues without having to compute A<sup>T</sup>.
* Numericallys reliable estimate of the effective rank of a matrix
  * In other words, we can tell which columns are linearly dependant despite measurement error.
* The generalized inverse of a matrix. Closely related to linear least squares.

A deeper dive on linear least squares. Kalman puts a whole section aside for this and I want to pay extra attention because linear least squares is pretty interesting.

### Linear Least Squares







