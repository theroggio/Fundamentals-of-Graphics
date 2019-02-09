# Correspondences

### Comparing shapes

Let's think about two shapes, very different for a computer but enogh similar for us. For example your mother and your father, they are different but they are both humans (or aliens, I don't want to assume anything).

The shape matching is still an open problem, because the distance between two 'different' shapes can be computed in many ways (depending on why we are computing it) and usually it's a 'good' approximation. 

### Correspondence

With correspondences we can transfer informations across shapes. A correspondence between two sets is a set satisfying that the pair (x,y) exists for every x in X and for every y in Y. In other words we want at least one match for every point.

Any **surjective map** defines a correspondence (while it's not true the contrary, because a map have only one pair (xi,y) for every xi). 

### Metric distortion

For a map we can define its absolute distortion as the max of the absolute difference between dx and df (for every pair). It is the same for a correspondence, wehre df is the difference for the points that correspond to x1 and x2 in dx. 

This values are the same if the correspondence is itself a surjective map. If the map is an isometry then this distortion is zero (and it's true the contrary, if we find distortion 0 then the correspondence is an isometry).

We can call an epsilon-isometry the correspondence / map where the maximum error is smaller than a very small value (epsilon).

### Rigid Alignment

Let's consider the Hausdorff distance in its non-symmetric version (so considering only the max istance between every x point to the Y shape). 

Moving one shape or the other, or both, inside the ambient space means varying the distance. Rigidly alligning the shapes means finding the 'translation' for which we have minimum Hausdorff distance; basically we check over all the rigid isometries (roto-translations).

<a href='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/icp.pdf'> **Iterative Closest Point** </a>

<a href='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/correspondences%20and%20GH%20distance.pdf'> **Correspondences and Gromov-Hausdorff Distance** </a>

### Matrix of Correspondence

We can represent correspondences as a matrix m-by-n (m is the number of points from X and n is the number of points from Y). The matrix has only 0 and 1 - when the couple (xi,yj) is a correspondence. This matrix encodes in the standard basis a map between function spaces, so it's a map betwen a map that takes every point of X to R, and a map that takes every point of Y to R. It maps functions to functions. 

A **permutation matrix** has every row and column summing up to 1 (so they have just one value equal to 1 and all others are zeros). Permutations matrices encode one-to-one correspondences, bijective maps.

Finding the correspondence that minimize the distortion is a problem usually represented with a matrix where every element is the value of the distortion between (xi,yl) and (xj,ym).

<a href= 'https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/QAP.pdf'> **Quadratic Assignment Problem with matrix notation** </a>
