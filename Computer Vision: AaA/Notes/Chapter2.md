# Chapter2

### 2.1 Geometric Primitives and Transformations

Homogenous corrdinates can represent 2D points and lines. 

Points are represented by a 3-tuple. First 2 are coordinates and the 3rd is some relation to 
infinity

Lines are represented by a 3-tuple where the first 2 coordinates are a vector and the 
third is the distance to the origin. Intersection computed by cross product between lines
Line joining two points is the cross product between two points.

Other algebraic curves can be expressed with homogeneous equations/coordinates. 
Useful in multi-view geometry and camera calibration.

3D points can be represented in the same way except they will have 4-tuples. 3D planes are 
the same but they are represented with their normal vector and their distance to the origin.
3D lines are a little less elegant. Represent by r = (1-[lambda])p + [lambda]q.

