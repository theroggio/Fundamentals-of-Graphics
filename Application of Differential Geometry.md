# Differential Geometry Applied

### First fundamental form

The first fundamental form of a regular surface at a point p is the quadratic form I : T -> R (it computes the norm of the input vector w as dot product).

For now consider x{u} and x{v} the basis spanning the tangent plane. Any vector w in the tangent plane is tangent to a prametrized curve. 

I(w1,w2) = I(a * x{u} + b * x{v}, c * x{u} + d * x{v}) = ac * <x{u},x{u}> + (ad + bc) * <x{u},x{v]> + bd * <x{v},x{v}> = ac * E + (ad + bc) * F + bd * G

E,F and G are the coefficients resulting from the dot product between the basis vectors - if they are all smooth we have a Riemannian manifold. This allow us to write it as a matrix 2-by-2 [E , F ; F , G].

From the first lessons of differential geometry we remember that the inner product between basis vectors are the partial differentiates; so this matrix just found - that we'll call **g** from now on - can be seen as g = transpose(J) * J.

##### Properties

Let's look at the coefficients, they give us a lot of infos about how the tangent plane is. 

If F = 0 means that the dot product between the basis vectors is zero, so it's a orthogonal parametrization.

If F = 0 and G = E is called conformal and if they're equals and their value is 1 is isometric.

The first fundamental form does not depend on the parametrization - so scaling the length of basis vectors or tangent plane, or their orientation will modify only the coefficients of the basis vectors multiplying u' and v' to have the same final results.

Two surfaces are **locally isometric** if they have the same firs fundamental form (or g matrix).

In this sense we can parametrize the sphere itself, having the accuracy of cutting a hole on a 'pole' (otherwise it would be impossible).

#### Discretization

From the charts of our triangle mesh we can see that the vectors **u** and **v** we use are basically ( v2 - v1 ) and ( v3 - v1 ) which in a canonical representation in 3D where the lengths of the triangle's sides are 'standard basis vectors' are e{21} and e{31}. 

Building the metric tensor g = [ quadratic norm e{21} , <e{21},e{31}> ; <e{21},e{31}> , quadratic norm e{31} ].

### Lengths

We can write a curve as a parametrization from a: (0,T) -> S. Being a length 'contuous' we need a integral calculus from 0 to T of the norm of a'. 

From the first fundamental form we know that the norm of a' is the square root of I(a') so it's the integral { square root { I } }.

We can consider the **arc length element** as the square root above, so that any length of a curve *c* is the integral of the arc length element along the curve itself.

### Areas

As before we need a starting domain to compute the integral, this can be express as the 'pairs' which are mapped into the region we want to compute the area of. So A(R) =  double integral { norm { x{u} x x{v} } }.

In this sense the area of a region is defined as the sum of little areas of parallelograms tangent to that surface region. 

<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/arealength.jpg'/>

As before we can express the root of det(g) as de **area element** (also called Riemannian volume form) and compute A(R) as the integral of the area element along the region.

#### Discretization

Remembering the u and v parametrization we can build the double integral computing the determinant of g (which we have built on the previous discretization section). 

### Integral of a function

The substitution rule in classical multivariate calculus can be replaced by our previous statements.

integral { f } = double integral { f(u,v) * det(g) } 

So we use a sort of weights given by det(g), 

#### Discretization 

Having a function which behaves linearly within each triangle and it's totally defined by its values at the vertices we can use the previous sections informations. 

<img src = 'https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/matrixintegralfunction.jpg'/>

So over a region we can sum up the itnegral of the function over all the triangles within the region.

### Gradient of a function (on surfaces)

We cannot define it as in R2 because some points in R3 does not belong to the surface; we cannot either use a parametrization because then the gradient would depend on it (we want a measure that's real and referred only to the surface). 

From the geometric meaning a gradient is a vector, pointing in the direction of steepest increase; length proportional to the strength of the increase. The directional derivative can be used and we can find that df(v) = <nabla(f) , v>. 

This is an application of Riesz representation theorem: the gradient of any differentiable function is the nabla(f) for which the above formula holds, every function in the dual space of the inner product space can be written uniquely as an inner product.

If we know how to write down df(v) then we can solve for nabla(f). 

<img src = 'https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/gradient.jpg'/>

#### Discretization

We already know the matrix g for every triangle. The partial derivatives df/du and df/dv (where f is in the parameter domain) can be approzimated as f(v2) - f(v1) and f(v3) - f(v1).

The discrete gradient is then computed exactly as explained above. We can also compute its norm from which we see that being the function linear (and the coefficient costants within each triangle) the gradient is constant in each triangle. 

### Total Variation 

The total variation of a function is the sum over all the triangles of the norm of the function. 

<img src = 'https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/totalvariation.jpg'/>

