# Spectral Geometry as Analysis of Laplacian 

### Self-Adjointness

<nabla(f) , nabla(g)>TX = - <div(nabla(f)) , g>X = <laplace(f) , g>X = f , laplace(g)>X

### Eigenvalues

Let's consider the generic complex eigenvalue for the laplace operator ( laplace(fi) = lambda * fi ) with fi = eigenfunction.

lambda <fi, fi> = <lambda * fi, fi> = < laplacian(fi) , fi> = <fi, laplacian(fi)> =
= conj( <laplacian(fi), fi> ) = conj( <lambda * fi, fi> ) = conj(lambda) * <fi,fi>

Hence lambda is real (otherise it could not be equal to its conjugate.

### Eigenfunctions

Let's consider two pairs of eigenvalues - eigenfunctions (i,j); the equation <fi{i} , laplacian(fi{j})> = < laplacian(fi{i}) , fi{j}> is satisfied only if the inner product between fi{i] and fi{j} is zero (because they have different egeinvalues). Therefore they are **orthogonal** and they cna always be rescaled to be **orthonormal**. 

The theorem says that the eigenfunctions of laplacian operator form an orthonormal basis of the vector space of functions. 

#### Discretization 

<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/gep.JPG'/>

<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/eigenfunctionavg.JPG'/>

### Dirichlet Energy

<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/dirichletenergy.JPG'/>

### Discrete Spectrum

The eigenvalues of the Laplacian are countable and canonically with increasing order. They follow Weyl's asymptotic law, the value is equal pi * i / integral { area element }. Where i is the number of the eigenvalue ( for i = 0 we have the first that is indeed 0 ). 

#### Properties

Laplacian spectrum is very useful for shape analysis because it is isometry invariant, it depends continuously on the Riemannian metric, it's easy and efficient to compute and it encodes toplogical and metric info of the surface. 

#### Fourier Analysis

A function with domain in [- pi , pi] can be written as Fourier series. The fourier basis corresponds to the Laplacian eigenfunctions
