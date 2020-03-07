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
  * 
