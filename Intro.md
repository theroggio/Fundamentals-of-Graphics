# Introduction

### What is a shape?

There is not a 'correct' definition of shape, every domain has one for itself. 

In Computer Graphics shapes are matematical objects (**manifolds**). 

Common mistakes about shapes is identifying them as *images* - but shapes are not flat, they can be represented in many different ways not just pixels, we have no global parametrization, there is no correct 'calculus' or 'transformation' notion. 

In representing a shape we use **triangle meshes** and **point clouds**. Every point can have its attributes (color, improtance, etc..). 

### Triangle Meshes

It's a collection of connected triangles. In the course we've seen oriented manifold meshes - each triangle has a consistent orientation and a normal.

All edges have at most two incident triangles - having one means being at the boundary. Faces incident on a vertex form a fan (open or closed).

### Point Clouds

It's a collection of points, they can be oriented - with a normal vector for each one - and usually are results of a sensor. 

