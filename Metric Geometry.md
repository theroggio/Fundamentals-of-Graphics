# Metric Geometry

### Distances

In a 3D domain distance can be computed in many ways. If I want to compute the distance between my head and toes I can do it as the euclidean distance between them or walking on my whole body (with its bumps and curves). 

Generally we can say that in R{k} the distance is a measure L{k} = (d(x1)^k + d(x2)^k + ... + d(xk)^k)^(1/k).

Euclidean distance is the L2 distance, L1 is called Manhattan distance, and so on.

### Metric Spaces

A set is a metric space if for every pair of points inside it there is a function (p1,p2) -> R (metric or distance measure). This metric must have:

- identity property = dist is 0 if p1 is equal p2
- simmetry = dist between p1 and p2 is equal to dist between p2 and p1
- triangle inequality

Considering a geodesic distance as measure we can commpute isolines as the lines connecting all points with same geodesic distance from a certain point.

#### Furthes Point Sampling

It's a way to compute a sampling of the surface the most uniformly possible. Even if 'uniform' is not defined on a manifold, the FPS algorithm it's based on euclidean distance and uses the most distant points between each others.

#### Voronoi Decomposition

Using a set of sampled points (from FPS or in any other way), we can divide the surface into regions. Every point not in the sample set can be assigned to a 'region' that is defined by a sampled point. This assignment can be done computing the minimal distance between the point and every sampled point.

### Ambient Space

Given a metric space and a shape inside of it (totalli contained) then the metric space can be callec **ambient space** and the metric can be used onto the shape using an adeguate **restriction** (basically we can compute it only on the shapes point, otherwise it has no sense).

### Isometries

Let's consider two metric spaces and a bijective map between them. The map is an **isometry** if the distance between two points on space 1 is equalt to the distance computed in space 2 between the resulting points of the mapping.

Rigid transformation are isometries: if I rotate mi phone it's screen width and length remain the same.

We often think about isometries as being 'the same shape', which actually are numerically nearly-isometries: a man sit on a chair and a man standing up (geodesical distance!).

### Distance between Shapes

The Hausdorff distance is computed between two subsets of the same metric space. It is the maximum value between v1 and v2. Where vi is the maximum distance between any point of surface i to surface j.

It is a common mistakes to believe that v1 = v2, but we must remember that the definition of distance between a point and a 'set of points' is its minimum value.

Note that modifying even just a point of the subsets can icnrease arbitrarily the H. distance.


The important thing was having an ambient space common between the shapes. If we don't have one can we still use this distance?

#### Embedding

The answer to the previous question is NO. It is basically because if we have different spaces we have different metric measures and we cannot assure them to be comparable. The right thing to do is embedding the shapes into a common domain with one metric to use in the right way.

An **isometric embedding** is a transformation preserving the original metrics. Usually the new metric space used is the one minimizing the Hausdorff distance, called **Gromov-Hausdorff distance** - metric on the isometry space.

An isometry class is a set of all shapes that are equal up to isometry: all the Bill Gates' poses, all the speck's ways to be rolled up.

*Attention*: the sphere is not embeddable. 



