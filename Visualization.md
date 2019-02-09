# Visualization

### How to visualize shapes

A good visualization makes the key message clear, puts emphasis on relevan aspects, makes the reading enjoyable and - not to forget - can cover little mistakes. 

A bad visualization would confuse the reader, not enriching the text and probably giving a wrong message. 

### Piecewise-linear Approximation

Let's consider a common linear function that we want to represent in a discrete domain. We must found another functions (discrete) approximating my real one. We can use a combination of basis functions.

real_f is approximated by fake_f that is the sum{i} of coeff(xi)*hat_basis{i}.

This can be done with sampled coefficients (from the real function) both randomly sampled that uniformly. As well as the basis function, it can be different.

#### On meshes

Let's apply it to a triangle. If we have a certain coefficient f(xi) for every vertex i = 1,2,3 the function can be obtained for the face of the triangle by linear interpolation.

With point clouds we have no faces, so we use f(xi) as the value at the precise point and that is it.

Matlab Shading is our possibility to interpolate or not the values, it depends on what we want to visualize. On a common mesh a 'flat shading' with no interpolation can create triangles visualization (not pleasant), but it could be good when visualizing a Voronoi Decomposition where values are constant over regions and then need a radical change so we do not want interpolations.

### Matlab Functions for Visualization

** Ambient light ** is a nondirectional light for the whole scene. It affects shadows.

** Diffuse reflection ** is the reflecation of the surface - wood does not reflect, a diamond does. It affects brilliance of colors.

** Specular reflection ** is what we usually call the light point on a surface.

### Colormaps

Colormaps are N by 3 matrices. N = number of vertices, 3 is for the RGB intensity with values in [0,1]. It's a quantization. 

Usually a colormap is defined with a scale of values that goes from the min to the max and interpolates linearly. Sometimes we could desire it to be different to get a saturation or other effects for a better visualization. 

If we decrease the max then all the values over the max will have the same colors; same if we increase the minimum. These methods can be helpful for visualizing local max/min, emphasizing errors. 

Another useful thing is centring the color map, that will express better when values go low and when they go high. 

### Correspondences 

Because of their being they're very difficult to visualize. They could be one-to-many, sparse, dense, probabilistics. So there is no 'correct' visualization, it really depends on the purpose and result.

Bad choice: lines - they're confusing and if you have a lot of correspondences they are messy and not clear.

Good choice: points with colors.

If we have a dense correspondence matrix (nearly all the vertices) we could define a function that is transported and that should have same colors in same regions. 



