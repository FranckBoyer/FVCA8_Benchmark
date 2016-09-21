# Benchmark on finite volume schemes for incompressible flows 

!(./Cartesian/mesh_cart_1.png)

##  The format of the 2D meshes

We provide two different formats for the meshes

 `*.typ1`  and  `*.typ2`

### Format .typ1

This file format is particularly designed for triangular or quadrangular control volumes. Each file contains the following informations:

*  the keyword `vertices`
*  the total number of vertices
*  the coordinates of the vertices
*  the keyword `triangles`
*  the total number of triangles (possibly 0)
*  for each triangle, a list of three integers representing its three vertices ordered clockwise
*  the keyword `quadrangles`
*  the total number of quadrangles (possibly 0)
*  for each quadrangle, a list of four integers representing its four vertices ordered clockwise
*  the keyword `edges of the boundary`
*  the total number of edges belonging to the boundary of the domain
*  for each boundary edge, a list of two integers representing its two vertices
*  the keyword `all edges`
*  the total number of edges ( intersection of two control volumes or of a control volume and the boundary of the domain)
*  for each edge, a list of four integers
   * the first two are the numbers of the two vertices of the edge
   * the last two are the numbers of the two control volumes (either triangle or quadrangle) defining the edge. By convention the fourth number is 0 if the edge lies on the boundary
   
 

*******************************************************************************

### Format .typ2 

This format files is adapted to any kind of polygonal control volumes

*  the keyword `Vertices`
*  the total number of vertices
*  the coordinates of the vertices
*  the keyword `cells`
*  the total number of control volumes
*  for each control volume, a list of `N` integers :
   *  The first integer is the number of sides of the control volume. It should be equal to `N-1`
   *  The last `N-1` integers are the numbers of the vertices of the control volume ordered clockwise

*******************************************************************************
 
### Example 

We consider a mesh of the unit square named `test` with 3 control volumes
      `[0,0.5]x[0,1]` , `[0.5,1]x[0,0.5]` , `[0.5,1]x[0.5,1]`


The corresponding file **`test.typ1`** is	

	vertices
	8
	0.0 0.0
	0.5 0.0
	1.0 0.0
	0.5 0.5 
	1.0 0.5
	0.0 1.0
	0.5 1.0
	1.0 1.0
	triangles
	0
	quadrangles
	3
	1 2 7 6
	2 3 5 4
	4 5 8 7
	edges of the boundary
	7
	1 2
	1 6 
	2 3
	3 5
	5 8
	6 7
	7 8
	all edges
	1 2 1 0
	1 6 1 0
	2 3 2 0
	2 4 1 2
	3 5 2 0
	4 5 2 3
	4 7 1 3
	5 8 3 0
	6 7 1 0
	7 8 3 0
	
The corresponding file **`test.typ2`** is
	
	Vertices
	8
	0.0 0.0
	0.5 0.0
	1.0 0.0
	0.5 0.5 
	1.0 0.5
	0.0 1.0
	0.5 1.0
	1.0 1.0
	cells
	3
	5 1 2 4 7 6
	4 2 3 5 4
	4 4 5 8 7
