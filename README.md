# Computational Geometry
###### RPTU Kaiserslautern - Winter term 2022/23
###### Based on [Computational Geometry - Algorithms and Applications](https://link.springer.com/book/10.1007/978-3-540-77974-2)
---
## Table of Contents
1. Introduction
2. Convex Hulls
3. Line Segment Intersection
4. Map Overlay
5. Polygon Triangulation
6. Quadtrees
7. kD-Trees and Range-Trees
8. BSP-Trees
9. Point Location
10. Voronoi Diagrams
11. Delaunay Triangulation
12. Recap
---

## Algorithm summary

| Problem class             | Approach            | 'Best' algorithm      | (Expected) runtime                                        | (Expected)memory              |
| ------------------------- | ------------------- | --------------------- | --------------------------------------------------------- | ----------------------------- |
| Convex hul                | Sweep line (radial) | Graham's scan         | $\mathcal{O}(n\log(n))$                                   | $\mathcal{O}(n)$              |
|                           | Sweep line (radial) | Jarvis' march         | $\mathcal{O}(nh)$                                         | $\mathcal{O}(n)$              |
| Line segment intersection | Sweep line          | Bentley-Ottmann       | $\mathcal{O}((n + \vert I \vert)\log(n))$                 | $\mathcal{O}(n)$              |
| Map overlay               | Sweep line          | MapOverlay            | $\mathcal{O}((n + k)\log(n))$                             | $\mathcal{O}(n)$              |
| Polygon triangulation     | Sweep line          | MonotonePartition     | $\mathcal{O}(n\log(n))$                                   | $\mathcal{O}(n)$              |
|                           |                     | TriangulateMonotone   | $\mathcal{O}(n)$                                          |                               |
|                           |                     | Triangulate           | $\mathcal{O}(n\log(n))$                                   |                               |
| Quadtrees                 | Spatial subdivision | Construction          | $\mathcal{O}((d + 1)n)$                                   | $\mathcal{O}((d + 1)n)$       |
|                           |                     | Query                 | $\mathcal{O}(d + 1)$                                      |                               |
|                           |                     | NeighborSearch        | $\mathcal{O}(d + 1)$                                      |                               |
| kD-trees                  | Spatial subdivision | BuildkDTree           | $\mathcal{O}(n\log(n))$                                   | $\mathcal{O}(n)$              |
|                           |                     | RangeSearch           | $\mathcal{O}(\vert T \cap R \vert + n^{1 - \frac{1}{k}})$ |                               |
| Range-trees               | Spatial subdivision | Construction          | $\mathcal{O}(n\log(n)^{k-1})$                             | $\mathcal{O}(n\log(n)^{k-1})$ |
|                           |                     | RangeSearch           | $\mathcal{O}(\vert T \cap R \vert + \log(n)^k)$           |                               |
| BSP trees                 | Spatial subdivision | BSP2D (with AP)       | $\mathcal{O}^\ast(n^2\log(n))$                            | $\mathcal{O}(n\log(n))$       |
|                           |                     | BSP2D (without AP)    | $\mathcal{O}(n\log(n))$                                   |                               |
| Point location            | Spatial subdivision | TrapezoidalMap        | $\mathcal{O}^\ast(n\log(n))$                              | $\mathcal{O}^\ast(n)$         |
|                           |                     | PointQuery            | $\mathcal{O}^\ast(\log(n))$                               |                               |
| Voronoi diagrams          | Sweep line          | Fortune's algorithm   | $\mathcal{O}(n\log(n))$                                   | $\mathcal{O}(n)$              |
| Delaunay triangulation    | Randomized          | DelaunayTriangulation | $\mathcal{O}^\ast(n\log(n))$                              | $\mathcal{O}(n)$              |
