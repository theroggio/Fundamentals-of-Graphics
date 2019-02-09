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

# Linear Algebra 2

### Reduction of basis

First of all the rank of a matrix is the dimension of the span of its columns, it's clear that for the matrix of the basis vectors the rank is equal to the dimension of the vector space. 

The rank doesn't depend on the basis! 

It represents the expressive power of the basis. If I have a n-dimensional space and choose only the first k basis' vectors, I would not be able to represent all my space but just a subset. 

A permutation matrix n-by-n has rank = n (because it encodes a one-to-one correspondence so all its vectors are linearly independent). 

### Invariant Subspaces

A subspace U of V is called invariant under a mapping T:V -> V is for every element u, T * u is still in U. 
This means that T:U -> U.

We call 'lambda' an **eigenvalue** of T:V -> V is for some v (not 0) holds T * v = 'lambda' * v. And v is its associated **eigenvector**. When the same 'lambda' has this property for more than a vector than it spans and **eigenspace**. 

This equations can hold for m different pairs of (lambda{i}, v{i}) that are proven to be linearly independent, m <= dim(V). 

In this sense eigenvectors provide a decomposition of V into subspaces (1-dimensional). If V is a function space then the eigenvectors are **eigenfunctions**. 

### Inner Product 

It's a function <u,v>: VxV -> R.

It is non negative, definite (is zero only if both u and v are zero), with proeprty of additivity, homogeneity, symmetry.

For real values vectors the inner product is the sum of component one-by-one multiplication.

On the vector space of functions continuous in [-1,1] it's the integral of the product of the two functions. 

Each inner product determine a **norm** (when it's between itself). 

If the inner product between two different elements is zero then the vectors are **orthogonal**. In R2 there's a definition that includes the cos(angle) and the two norms, so it encodes a general notion of angle between the vectors. 

A basis is **orthonormal** if every basis vector has norm = 1 and they are all mutually orthogonal. We can see that given an orthonormal basis, every vector can be written as the linear combination where the coefficients are the dot product between v and the basis vector. 

<a href='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/dotproduct.pdf'> **Inner product in matrix notation** </a>

