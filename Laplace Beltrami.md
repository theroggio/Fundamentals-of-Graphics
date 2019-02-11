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

### Heat Kernel

A numerical solution for the heat diffusion on surfaces is obtained by using the integral { kernel(x,y) * u_0(y) } where the **heat kernel** of surface X describes the amount of heat transferred from point x to point y in time t. It is a property of the manifold that does not depend on the initial configuration. 

Let's assume an initial configuration as Dirac delta at point z. It satisfies the sampling property. 

So the solution is simple, and it's the kernel itself.

#### Properties

In Rn is given by  ( 1 / n-root(4 pi t) ) * exp ( - quadratic norm ( x - y) / 4t )

Distance can be recovered by Varadhan's result: - lim (t -> 0) 4t log(kernel).

If T is an isometry then the kernel on surface X (point x,y) has the same value of the kernel on surface Y (point T(x),T(y)).

### Spectral Decomposition

Any solution can be written in the Laplacian eigenbasis as the sum of c * lambda * eigenfunction. 

Thus we can write the partial derivative on the left-side as a sum over partial derivative of c * eigenfunction. 

Then we obtain **partial derivative c = - c * lambda**.

The final solution is **u(x,t) = sum d{i} * e ^ (- lambda{i] * t) * eigenfunction{i}**.

To find the coefficientd d{i} we use the initial condition comouting at t = 0.  For which we obtain that u_0(x) = sum d{i} * eigenfunction{i}. 

If the initial condition was a dirac delta_y (x) then d{i} = <eigenfunction{i},dirac{y}> = eigenfunction{i}(y).

In matrix notation:     **K{t} = FI * diag(exp(-lambda{i} * t) * transpose(FI)**.

### Heat Kernel Signature

We use the property of isometry T to define a **local descriptor**. The heat kernel signature is defined as the diagonal of the above matrix. 

If the two surfaces are isometric then we expect corresponding points to behave similarly. 

### Diffusion Distance

The heat kernel does not define a distance measure, but a family of diffusion distasnces can be obtained as the quadratic norm of the difference of kernel(x,+) and kernel(+,y). This is indeed a metric, diffusion time behaves like a scaling factor

The interpretation is that when two points are very close there is a large probability of transition from one to the other. 

<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/heatdist.jpg'/>


