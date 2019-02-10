# The Laplace Beltrami Operator

For a subset of R2 the diffusion of ehat is described by the **heat equation** : 
- d/dt u(x,t) = laplacian u(x,t)
- u(x,0) = u_0(x)

Where the laplacian = - div(nabla(u)) = summing of second order partial derivaties.
We need to know how compute the laplacian on a surface!

### Inner product on manifolds

Given two scalar functions defined on a manifold, their inner product is the integral over the whole manifold of their product. Discretized this becomes transpose(f) * diag(A) * g , where A contains the area elements at each vertex.

Given two tangent vector fields? Their inner product is the integral { inner product }.

### Geometric Intuition of the laplacian

From the geometric definition of laplacian = - div(nabla(f)).

- nabla(f) is the direction of the steepest increase of f in every point
- div(f) is the scalar density of an outward flux of f from an infinitesimal volume around every poit

So the laplacian is the scalar difference between f(x) and the average of f on an infinitesimal shape around x. 

### Adjointness

Both gradient and divergence are negative adjoint operators. The inner product on a tangent field between F and nabla(f) is equal to the negative inner product on the surface (not on the tangent field) between divF and f. 

Important difference is the passing from vector fields to scalar functions!

### Finite Elements Method

In the discretization of the Laplace Beltrami operator we'll use  anew approach. Considering an equation as laplace(f) = g we want to build g and then solve for the laplace operator (similar to what we've done looking for the gradient).

We first look at a weak formulation on scalar fields < laplace(f) , h > = < g , h >. Remember h{i} is the hat basis function defined at every vertex of the mesh. 

<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/laplaciandiscrete.jpg'/>

The matrices are sparse, symmetric, with a structure similar to the adjacency matrix. S is positive semi-definite and they can be computed easily and efficiently for any mesh.

<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/massandstiffness.jpg'/>


