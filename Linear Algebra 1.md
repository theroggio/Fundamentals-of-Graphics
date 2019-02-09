# Linear algebra 1

### Vector Space

A vector space is a set in which are defined addition and scalar multiplication answering some properties: commutativity, associativity, additivite identity, additive inverse, multiplicative identity, distribution. 

Their elements can be vectors (as we knoe them, list of elements) but more in general are objects. 

Shapes are not vector spaces: if we sum up to vertices in general we do not obtain a third vertex on the shapes itself. 

### Subspaces

A subset of a vector space is a subspace if it's all contained in a vector space and it's a vector space itself. 

### Bases

A basis of V is a collection of vectors that are lineraly independent and that can span all the vector space. For example in R2 the vectors ( 0 1 ) and ( 1 0 ) are independents and using them (w scalars and sum) we can obtain every point of R2.

These type of vectors are called **indicators** and the basis they form it's the **standard basis**.

Hat functions are a basis for the piecewise linear functions. We can compute a basis for functions R -> R as a set of 'R' functions that are 0 everywhere excet in the point i and are called **indicator functions**.

#### Mesh 

On a mesh we can consider indicator functions the set of functions selecting just one vertex. Or we can use hat functions one for each vertex. 

#### Dimensions

Any vector space has one dimension and every basis will have a number of vectors equal to the space dimension. 

### Linear Maps

A linear map is a function with additivity and homogeneity. 

Linear maps form a vector space. We also have a definition of product between linear maps, it's the common composition of functions g ° f. Remember this operation is not commutative.


### Matrices

A matrix expressing a linear map between two vector spaces (with basis v and w) encodes how basis vectors are mapped and it is enough to map all the other vectors (because a vector V is a linear combination of vector basis vi, so we can compute the vector W as the linear combination of wi where wi = map(vi) ).

Matrices representsd linear map depending on the chosen bases. A vector, chosen a basis, can be expressed as only the coefficients to multiply the basis.

Addition has sense only if we use the same basis (otherwise we're summing apples and peaches). 



