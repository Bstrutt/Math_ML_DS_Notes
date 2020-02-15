# Chapter2

### 2.1 Geometric Primitives and Transformations
#### Primitives
* Homogenous corrdinates can represent 2D points and lines. 

  * Points are represented by a 3-tuple. First 2 are coordinates and the 3rd is some relation to 
infinity

  * Lines are represented by a 3-tuple where the first 2 coordinates are a vector and the third is the distance to the origin. Intersection computed by cross product between lines. The line joining two points is the cross product between two points.

* Other algebraic curves can be expressed with homogeneous equations/coordinates. 
Useful in multi-view geometry and camera calibration.

* 3D points can be represented in the same way except they will have 4-tuples. 3D planes are 
the same but they are represented with their normal vector and their distance to the origin.
3D lines are a little less elegant. Represent by r = (1-[lambda])p + [lambda]q.

#### Translations
* Translations can be written as the result being equal to the addition of your translation
to the original point.
This can be extended to homogeneous points by multiplying the point by [I t] where I is
the identity matrix and t is the translation.

* Rotation is done similarly but the result is equal to [R t]x where R is the orthonormal 
rotation matrix where RR^T = I and |R| = 1

* Projective transformation is when we make one side of something smaller. It gives a sort 
of dissapearing perspective. We do this by multiplying our homogeneous coordinate vector by an arbitrary homogeneous matrix. We must normalize to obtain an inhomogeneous resulting x.

* The basic transformations on 2D homogeneous vectors can be thought of as 3x3 matrix
multiplication. They nest into themselves nicely in terms of the features they preserve of your original shape.

#### 3D Translations

* 3D translations are very similar. Differences are the size of matrices go to 4x4 to match the 4-wide homogeneous vectors.

* 3D rotations are not as straightforward.
Author mentions specifically not to use Euler angles for some reason.

* Rodriguez equation can be used to rotate a 3D shape around a given axis vector n. The actual formula is within the book but it is best used for small rotations and when the rotation is expressed in radians.

* Quaternions can be derived from the axis/model. We can convert the Rodrguez formula
to the Quaternions formula where q = (v,w) = (sin(theta)/2 * n, cos(theta)/2) using some pretty simple quaternions.

* The only thing left is choosing which representation is better. Axis/Angle is minimal and easier to understand. Quaternions are good if you want to track smooth movement as the representation is continuous.

* May implement the slerp formula later as an exercise if it proves to be something that is frequently used.

#### 3D to 2D projections

* Simplest if you use orthography which just removes your depth coordinate from the homogeneous coordinate. This doesn't really give a good 3d "feel" more akin to TMNT games from back in the day. 

* Using Projection will keep that 3d "feel."



