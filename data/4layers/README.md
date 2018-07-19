# 4 Layers model

This simple model has :
 * 4 Layers
 * 21 surfaces ( 3 internal surfaces and 18 boundary surfaces)

This model is divided into 10 paritions.
Each partition contains a set of tetrahedra and triangles.

Because of the ParaView/VTK formalism, we distinct:
 * The vertices (with 3D coordinates)
 * The elements (in this case, tetrahedra and triangles).

As a consequence, a property has to be defined on every vertices OR on every elements.

Here we have:

## Properties on vertices

 * _original point_ This is a global numbering of the points. Indeed, the vertices
 which are on a partition boundary could be collocated with another point on another partition.
 In this case, boths points will have the same _original value_, which could be convenient
 for FEM

## Properties on elements

 * _partition_ This indicate the partition in which the element is.
 * _region_ This indicate wether the layer index if this property is read on a tetrahedron, or
 the boundary surface index if this property is read on a triangle.
 * _original index_ This a global continuous numbering for tetrahedra (going fron 0 to the
 total number  of tetrahedra) and for boundary triangles (going form 0 to the total number of
 triangles)
