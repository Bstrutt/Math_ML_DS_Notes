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
* Results of Linear Independence
  * Vectors are either linearly independent or linearly dependent
  * If a vector in a set is 0 then the vectors in the set are linearly dependent
  * The above holds if two or more vectors are identical
  Vectors are linearly dependent if at least one is a linear combination of the others
  * Gaussian elimination can be used to determine linear independence. Write all vectors as columns of a matrix. Get to reduced row echelon form. The pivot columns are independent. Non-pivot coloumns are linear combinations of the pivot columns to their left.
  
### Basis and Rank 
* A subset of a vector space which can create the vector space through linear combinations is called a "generating set"
* Sets are said to "span" vector spaces if they can represent the space through linear combination.
* A basis is a minimal subset that spans a vector space.
  * Basis implies that the set is maximal linearly independent so if anything is added it will become dependent.
  * Bases are not necessarily unique.
  * Bases do have the same number of elements.
* Dimension is defined as the number of basis vectors of a vector space, NOT the number of elements in the vector.
  * The dimension can be thought of as the number of independent directions in the vector space.
* To find a basis, write the spanning vectors as columns, get the matrix to Row Echelon, pivot columns are your basis vectors.
* Rank is defined as the number of linearly independent rows/columns
  * rank(A) = rank(A<sup>T</sup>)
  * Columns of A<sup>m*n</sup> span a subspace U<sup>m</sup> with dim(U)=rank(A)
  * Rows of A<sup>m*n</sup> span a subspace W<sup>n</sup> with dim(W)=rank(A)
  * For A<sup>n*n</sup> A is invertible iff rank(A)=n
  * Full rank is defined as the largest possible rank for a matrix of a certain dimension. rank(A) = min(m,n) for a matrix A<sup>m*n</sup>
 
### Linear Mapping
* Linear mapping is defined in a nice one-liner on page 48 of this text.
  * a mapping Q, vector space V and W, vectors x and y, scalars i and j.
  * Q(ix+jy) = iQx + jQy
  * This linear mapping is said to preserve the structure of the vector space. 
  * Also called a vector space homomorphism, or a linear transformation
  * Linear mappings can be represented by matrices
* A mapping Q: V->W
  * Injective(one-to-one)- Q(x) = Q(y) implies x = y
    * Each input has a unique output. Different inputs will never get the same output
  * Surjective- Q(V)=W
    * Each element in W can be reached from V using the mapping
  * Bijective- Both injective and surjective
    * Can be reversed using a mapping inverse of Q
  * Isomorphic- V-> W Linear and Bijective
  * Endomorphic- V->V Linear
  * Automorphic- V->V Linear and Bijective
* Finite-dimensional vector spaces are isomorphic iff dim(V) = dim(W).
* We can organize an ordered basis to be multiplied by columnn vectors to represent individual vectors of the span of the basis.
* We do basis changes with linear mappings. We can change bases then map to other vector spaces and map onto other bases. It's all matrix multiplication.

### Kernel and Image
* Kernel is the set of vectors in input that map to the 0 element of output
* The image is the set of vectors in output that can be reached by input
* Nice diagram on page 59 of kernel and image relations
* Very important theorem
  * dim(ker(Q)) + dim(Im(Q)) = dim(V) for vector spaces V,W and mapping Q

### Affine Spaces
* A subspace which has been divorced from the point of origin. We can map to an affine subspace from our original vector space with something called a displacement vector or translations. To contrast, linear subspaces always contain the origin of the vector space.
* Affine mapping is a mapping between two affine spaces. Defined as follows. For vector spaces V, W, a linear mapping Q:V->W and a/in/W

q:V->W

x->a+Q(x)
* The vector represented as a in the previous equation is called the translation vector
* 
