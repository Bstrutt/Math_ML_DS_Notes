As previously stated, I have a good knowledge of this subject but for the sake of 
consolidating that knowledge and aiming it towards machine learning I will be 
covering it again here.

# Linear Algebra

### General
* Vectors
  * A vector is an object which can be added with another vector or multiplied by some scalar,
    in both cases the result is another vector.
  * We generally think of vectors as n-tuples of real numbers
* Closure 
  * Defined vaguely in this text in the form of a question
  * "The set of all things that can result from my proposed operations"
  * In terms of vectors the result is a vector space

### Systems of Linear Equations
* Can formulate problems as systems of linear equations
* We can solve these systems to get solutions to our problems
* For real-valued systems we obtain 1, 0, or infinite solutions
* A systematic approach to solving SoLE is within the book
  * This approach boils down to making vectors out of coefficient columns
    then making a matrix out of these. Afterwards we make a vector out of 
    the variables and matrix multiply these equalling the product vector.
  * Contained on page 22 for reference
  
### Matrices
* A matrix A is an m*n tuple of elements
* Elements can be located using a coordinate scheme ie. A<sub>12</sub>
* Matrix addition adds elements to their corresponding elements in separate
matrices. A<sub>12</sub> + B<sub>12</sub> = C<sub>12</sub>
* Matrix multiplication involves multiplying rows with corresponding columns
and adding the products together. A<sub>row</sub> * B<sub>col</sub> = C<sub>row col</sub>
* Matrices Are
  * Associative (AB)C = A(BC)
  * NOT Commutative AB != BA
  * Distributive (A+B)C = AC+BC && A(C+D) = AC+AD
* AX=I=XA , X is the inverese of A, denoted A<sup>-1</sup>
  * If the inverse exists A is regular/invertible/nonsingular
* Transpose is just columns made into rows. Changes the structure for benefits
in manipulation.
  * Symmetric is when A = A<sup>T</sup>
* Scalar multiplicaton is simply scaling each element by some scalar $\theta$

### Solving SoLE
* Row Echelon form can be used to solve SoLE
  * Carried out by transforming the matrix to have a more simple solution
  * It's in the book if you forget. Just look on page 30.
* Gaussian Elimination works well for systems of thousands of variables but not
for millions. Methods for millions include stationary iterative methods such as: Richardson, Jacobi, GauB-Seidel, successive over-relaxation, Krylov subspace methods.

### Vector Spaces
I'm a fan of the definition of vector spaces here being "a structured space in which 
vectors live" That's much easier than the incredible vague definitions given in trad
linear algebra books.
* Groups
  * Considering a set G and an operation x a group exists if the following hold
    * Closure: z,y in G -> zxy in G
    * Associativity: z,y,w in G -> (zxy)xw =zx(yxw)
    * Neutral element: zxe = z
    * Inverse element: zxy = e = yxz
* Vector Spaces
  * Contains both an inner operation like a group but also an outer operation
  like scalar multiplication
* Vector Subspaces
  * Subsets contained within the vector space. 
  * Operations on these will only produce vectors within the subspace, we cannot "leave"
  this space in a sense.
  * Key in machine learning for "dimensionality reduction"
  
### Linear Independence
* Linear Combination
  * A vector created out of a vector space using any combination of 
    vector addition and scalar multiplication.
* Linear Independence
  * If a vector in a vector space cannot be represented by a linear combination of 
  any of the other vectors.
  * This has always made sense to me but when it comes to the implications of a linearly independent space or a linearly independent vector I am a bit confused and unsure.
  * A set of linearly indepenedent vectors consists of vectors with no redundancy. If we remove any of them we lose some information. 
