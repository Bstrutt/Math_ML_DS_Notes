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
* Row Echelon form can be used to solve SoLE
  * Carried out by transforming the matrix to have a more simple solution
  * It's in the book if you forget. Just look on page 30.
* Gaussian Elimination works well for systems of thousands of variables but not
for millions. Methods for millions include stationary iterative methods such as: Richardson, Jacobi, GauB-Seidel, successive over-relaxation, Krylov subspace methods.
