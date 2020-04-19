I've never approached this subject, or at least this subject under this name. My hope is
that I can move through it with haste so that I can get to more practical machine learning
techniques.
# Analytic Geometry
Adding geometric interpretation to the concepts of linear algebra.
Inner products, norms, and metrics are used to develop support vector machines later.

### Norms
* Norm 
  * defined as a function that assigns lengths to vectors such that these hold
    * Absolutely Homogenous: ||*theta*x||=|*theta*|||x||
    * Triangle Inequality: ||x+y|| <= ||x||+||Y||
    * Positive Definite: ||x|| >= 0 and ||x|| = 0 <=> x = 0
### Inner Products
Allows for intuitive geomtrical concepts.
* Dot Product
  * The sum total of each corresponding element in 2 vectors being multiplied. x<sup>T</sup>
* General inner products
  * Bilinear Mapping
    * Linear mapping with two arguments, linear in each argument
  * Symmetric
    * If the order of arguments does not matter
    * Q(x,v) = Q(v,x)
  * Positive Definite
    * For all n nonzero arguments, the result is positive. The inner product is a good example
  * Inner Product (General)
    * a positive definite, symmetric, bilinear mapping Q: VxV -> Real Numbers
Inner products and norms are closely related in that inner products produce norms and can be useful for calculating the length of vectors. The Manhattan norm is a good example of a norm without an inner product.

Depending on which inner product you choose the resulting norm and length can be different because math is all made up to confuse normies

* Distance
  * Defined as d(x,y) := ||x-y|| = root(<x-y,x-y>)

If we use the dot product as our inner product then the norm we get is the Euclidean distance.

A mapping d: V x V -> R 
 (x,y) -> d(x,y) is called a metric.
 
A metric satisfies being positive definite, symmetric and the triangle inequality

Metrics and Inner proudcts looks similar however, they act in opposite directions.
A small difference in x and y will result in a large inner product result and a small 
metric result.

### Angles and Orthogonality

We can tell more about the geometry of two vectors via inner products. Using the Cauchy
Schwarz innequality we can find the angly between two vectors which can tell us how 
similar their orientations are.
cos(w) = (<x,y>)/(||x|| ||y||) then w is the angle between vectors x and y. 

I have questions about which inner product we are supposed to use because it seems like 
they would come up with different results. Usually I think we use the dot product but 
the general form stands as above.

The tightest thing about the inner product is that we can characterize orthogonality.

* Orthogonality
  * Two vectors being zero in the inner product. <x,y> = 0. We write x ⊥ y
  * If vectors are ||x|| = 1 = ||y|| then they are orthonormal.

Got my answer to a question I had above. Vectors can be orthogonal with respect to one
inner product and not another. Just be consistent with which inner product we use.
It's still usually the dot product.

* Orthogonal Matrix
  * A square matrix iff AA<sup>T</sup> = I = A<sup>T</sup>A
  * This implies A<sup>-1</sup> = A (inverse by transpose)

These matrices are useful becausethe length of a vector is not changed when transformed 
using an orthogonal matrix. Additionally, the angle between two vectors is not changed
either. Orthogonal matrices define rotations which preserve angle and length.

### Orthonormal Basis

The special case in which basis vectors are each of length 1 and are each orthogonal to each other. At first I thought that any basis vector would be orthogonal because basis vectors are linearly independent. This is not the case because linear independence does not imply orthogonality. Orthogonality does imply linear independence. The first counter example I saw was the case where we have basis (1,1) (0,1). This is a basis for R<sup>2</sup> but is not orthogonal.

We can use the Gram-Schmidt process to iteratively build and orthonormal basis and while the book EXPLAINS how to do this, it does not provide ample enough evidence to SHOW how to do this.

These are important when we do support vector machines and principal component analysis.

### Orthogonal Complement

We have two vector spaces. The first, V, has D dimensions, the second, U, has M dimensions and is a subspace of V. The orthogonal complement U<sup>T</sup> of the second vector space has D - M dimensions, is also a subspace of the first, and contains all vectors in the first which are orthogonal to every vector in the second. 

A vector w with ||w|| = 1 which is orthogonal to U, is the basis vector of the second subspace U<sup>T</sup>. All vectors orthogonal to w must lie in the plane U. w is called the normal vector of U.

Orthogonal complements can be used to describe hyperplanes in n-dimensional vector and affine spaces.

### Inner Product of Functions

We can think of vectors x(in)R<sup>n</sup> as functions with n function values. Furthermore, we can make inner products generalized to infinite entry vectors and coninuous valued functions. The sum over individual components just becomes a definite integral. This is where the inner product becomes particularly important. We need it to determine if things are orthogonal and we cant just place continuous valued functions side by side and see if they're at a right angle like we can with vectors. 

Unfortunately, inner products on functions may diverge and this requires getting into real and functional analysis.

Good examples of orthogonal functions are sin and cos. Page 81 in the book explains this well.

### Orthogonal Projections

Projections are important. We often have high dimensional data but this data is hard to analyze or visualize. Most often it only contains a few important dimensions. We compress this but we will lose some info. We project the high-dim data onto low dimension spaces to extract relevant patterns.

Some important things that do this. Principal component analysis Pearson(1901) Hotelling (1933) and Deep neural nets (Deng 2010).

* Projection
  * 

