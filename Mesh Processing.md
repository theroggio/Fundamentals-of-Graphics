# Mesh Processing

### Adjacency Matrix

The mesh connectivity can be encoded in this type of matrix. 

#### Vertex to Vertex

It's a matrix n-by-n (n = number of vertices) where the generic element a{ij} is 1 if vertex v{i} is connected to vertex v{j}. 

This means the matrix has only 0 and 1; it's symmetric, the diagonal is 0 and each row and column has at least one 1 (the case of edges, all the other have more than one 1). 

#### Vertex to Triangle

It's a n-by-m matrix (n = number of vertices, m = number of triangles) and the generic element a{ij} is equal to 1 if vertex v{i} belongs to triangle t{j}. 

This means every column has exactly three value equals to 1. Each row has at least one 1. 

#### Vertex to Vertex Co-occurrence

If we multiply the vertex to triangle P as P * transpose(P) we obtain a matrix that is n-by-n and where the generic element a{ij} counts the number of triangles where v{i} and v{j} both occur. The diagonal is the number of triangles for each vertex. 

The generic element is 0 (vertices does not share any edge), 1 (the edge is at the boundary) or 2 (interior edge). 

#### Triangle to Triangle

It's computed as transpose(P) * P and it's a m-by-m matrix. The generic element a{ij} counts the number of vertices that triangles i and j share. 

The diagonal it's all 3. The other values can be 0 (triangles distant from each other), 1 (connected in a fan) or 2 (connected by and edge). 

### Powers of Adjacency

The k-th power of the adjacency matrix is the k-th order adjacency. It can be applied to any 'adjacency' type, vertex to vertex, triangle to triangle, vertex to triangle.

### Adjacency as operators

We can apply adjacency to functions, for example we can define a function g = A * f. So the function g is defined on the vertex i as the sum of f(vk) for every k that is adjacent to vertex i. 

### Point Clouds Adjacency

The adjacency is difficult to compute without connectivity, for point clouds we can compute neighbours as the points closer than a threshold **e** using appropriate distance measures.

### Graph Laplacian

Given a mesh (or just its graph, so the vertex and edges) let's consider the equation that is satisfied for vertices that are the barycenter of their neighbours. We define the mtrix encoding this information as the graph laplacian L.

Seeking an embedding satisfying the equation for every vertex we can assume m **anchor** for which we know the position and solve a linear system with least square meshes.

<a href='https://github.com/theroggio/Fundamentals-of-Graphics/blob/master/scan/graph%20laplacian.pdf'>  **Graph Laplacian and Least Square** </a>
