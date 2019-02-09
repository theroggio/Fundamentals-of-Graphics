# Differential Geoemtry

Differential geometry gives us the tools to compute lengths, areas, integrals, gradients... on surfaces!

### Charts

Let's see a chart as a mapping, smooth and invertible (called diffeomorphism).

If we have a **regular surface** in R3:
- cut pieces of a plane (R2 charts)
- deform the pieces
- glue them together to have no sharp edges or overlappings (regularity)

Regularity allow us to speak about tangent point for every point of the surface (there would not exist at edges, like vertices of a cube). 

A chart is regular is there exist a tangent plane for every resulting point. A point where we cannot define the tangent plane is a **singular point**.

### Parametrized Curves

A parametrized curve is a map to R3 that uses a parameter as (x(t), y(t), z(t)) uses the parameter t. The three functions should be differentiable so we can compute the tangent at t as (x'(t), y'(t), z'(t)) easily. 

The parametrization is not unique. 

### Tangent Plane

We can denote a tangent plane at a point p as T{p}S, it's the plane defined by the set of tangent vectors to all possible parametrized curves on surface S passing through p. 

### Differential

At a given point the differential of the map is given by the differential of the composition between map and parametrization. This composition is in fact a liner map from tangent vectors to tangent vectors.

<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/differentialmapmatrix.jpg'/>

### Mesh Parametrization

We deal with a discrete setting of triangles, the solution is a chart for every triangle. 


<img src='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/discretechart.jpg'/>
