# Mid term Questions

### The flat shpere forms a metric space with the restricted euclidean metric. An alternative is using the shortest arch length. Are these two spaces isometric?

No, they're not isometric. We can show it considering first three points on the flat sphere (A,B,C) equidistants using the shortest arc length.

If we represent them with euclidean distance we found a triangle equilaterus.

If now we took the midpoints on the flat sphere (D,E,F), they correspod in the euclidean space to another equilaterus triangle with vertex at the midpoints of the first triangle's edges.

But the distance between the new points (D,E,F) on the spere is equal to the distance between the first trhee points (A,B,C) while in the euclidean space this is not true. So the spaces are not isometrics.

### Consider the space of scalar functions defined on a mesh. They form a vector space. Can this be also a metric space? How?

Yes, it is possible. If we fix an element 'v' of the surface and compute g(v) and f(v) we can compute their distance in a discrete way, 0 if equal and 1  if different. 

So in the generic setting of the whole surface we can denote as **gv** the real-valued vector resulting from applying g to the surface, and **fv** if we apply f. 

Now their difference is equal to the sum of all their components that are different one from the other. If **gv** = [ 1 , 0 , 5 , 8 ] and **fv** = [ 1 , 3 , 4 , 1 ] their distance is 3.

This definition of distance respects all the requirements for being a metric: 
- d(f,f) = 0 because the same function would output the same real-valued vector
- d(f,g) = d(g,f) 
- d(f,g) <= d(f,i) + d(i,g), this is not intuitive but if f and g have 3 different values, then using the two distances can only increase this value. 

If i == f or i == g or f == g it's trivial. In any other case to violate the inequality we should have that i is very similar to both f and g. But in the three 'differences' it can only be equal f/g (but then is different to g/f = +1) or different from both (+2).

### Consider a metric space and a furthest point sampling. Can it be obtained by a linear mapping? Why / How ?

No it's not possible. The furthest point sampling (for N points) needs at every iteration to compute a new 'distance matrix' from the set of points chosen. This matrix is used to take the point at 'max' distance and the max operator is not lienar.

The only 'linear part' could be, having already the set of indeces of selected point, to use a F matrix k-by-n (where k is the number of points we selects) multiplied for the vertices vector ; every k-th row has all zeros except for element j which is the selected element and it has value 1.

A sampling can be done in this way but to be totally linear it should not have any 'max' operator to use.

### Define the row rank of a matrix as the dimension of the span of its rows. Provide an explicit example with a square matrix, and one with a rectangular matrix, in which the row rank is equal to the classical column rank. Explain the examples.

Given a matrix the row rank is the number of linearly independent rows. It is proven that column rank and row rank are equals.

The classical square example uses the standard basis [ 0 , 1 ; 1 , 0 ] where row1 = ( 0 1 ), row2 = ( 1 0 ), column1 = ( 0 1 )' and column2 = ( 1 0 )'.

An example with a rectangular matrix can be [ 0 , 1 , 1 ; 1 , 0 , 1 ] which is a 2-by-3. Row1 = ( 0 1 1 ) and row2 = ( 1 0 1 ) are linearly independent. Column1 = ( 0 1 )', column2 = ( 1 0 )' are linearly indpendent while column3 = ( 1 1 )' is c1 + c2.

So both column and row rank are equal 2.

### Let G = (V,E) be the graph representing mesh connectivity; further denote by v{i} the location of vertex *i* and by d{i} the valence of vertex *i*. Consider the barycenter expression. Define the matrix A to write **AV = 0** and express what is A * A.

We can build A as a matrix n-by-n where n = number of vertices. The diagonal has all ones. Then for every edge e{ij} the element A{ij} must be equal to - 1/d{i}. 

The generic element of  A * A is 0 if the two vertex are not connected with neither one or two steps of edges, it's TO COMPLETE





