# Euclidean Embeddings

### Distorted Embeddings

We've said that the sphere cannot be embedded in any space, that's because knowing all of its points and distances creates errors between the original shapes and the others.

If we could tolerate an error would it be possible?

Let's consider for a moment to have just edges' lengths with no vertex informations. Shape modeling and shape optimization we can 'build' a geometry satisfying the lengths' property and solve for an Euclidean embedding.

This can be done using a gradient method minimizing a distortion measure. The disrtotion induced by a mapping can be quantified as follows:

- measuring the relative changes between metrics (dilation) as the ratio between dist(f1,f2) and dist(x1,x2). 
- measuring the absolute distortion as |df - dx|.

If the distance between the mapped points is the euclidean one, the embedded shape is the **canonical form** of the shape. 

### Canonical forms

Note that a canonical form has always a non-zero error (which is rarely obtainable).

It defines an isometry class in R{k}. So if we have nearly-isoemtric deformations of a shape [ Natsu Dragneel running (1), eating (2) and fighting(3) ] their canonical forms would be rigid transformation of the same one.

### Stress Measure

A global measure for distortion is the quadratic stress. It is the sum of the quadratic difference between dx and || fi - fj ||.

The minimization problem does not have a unique solution, so applying isometries to the optimizer will not change the stress.

<a href='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/stress%20computation.pdf'>**Mathemical demonstration of matrix form for the Quadratic Stress**</a>.

