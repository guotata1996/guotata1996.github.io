## Statement
As one of the most tricky limitations of the current design of system, the following freeway exit is not allowed. 
![realexit](https://github.com/guotata1996/guotata1996.github.io/raw/master/img/post2/realexit.png)

If you try doing it, you'll probably achieve one of these unwanted results:
![realexit](https://github.com/guotata1996/guotata1996.github.io/raw/master/img/post2/failure.png)

## Analysis
The answer to this failure is quite straightforward: two constraints prevent us from the realistic effect:
1.  Every road is generated with its center exactly on its curve; offset is not allowed. That is to say, if you have a line (on the XY plane) x = 2, then you cannot draw a road with center on line x = 1.
2. All the roads' curves connected to one node must meet at the same point.

Let's analysis the difficulty of removing either of the constraints:
1. If we allow offset when rendering road, then the same curve may represent two or more roads, which could lead to tricky bugs in geometry calculation. Most of the interfaces & implementations in geometry library must be modified, which would affect nearly half of all codes.
2. If we allow the node to have several child nodes (eg. the node at the center of the red zone has yellow child nodes) with one curve attached to each child node, then it would become even more counterintuitive that untouching curves could intersect and form a node. Let alone the complexity of rewritting Node.cs, the UI is also hard to design.
![realexit](https://github.com/guotata1996/guotata1996.github.io/raw/master/img/post2/realexit_label.png)

Does it mean there's no solution to this problem? Note that all statmemts above are based on one assumption: **the red zone is represented as a node**(with smoothening curves).

What if we represent it with a road?

Immediately, this type of road has two significant differences from the current roads:
1. It connects to more than two nodes.
2. It does not have constant width.

Additionaly, it has a property that could simplify the coding job:
- No intersection is allowed at the middle.

Fortunately, this is an addition more than modification to the current functions; neither of the two properties undermines the current system. The curve.cs doesn't need any modification as rendering it doesn't need new curve types. You can simply create two nodes upon generation in roadManager. The biggest modification should be in class "Road". Also, "Approximation a point to current road" should be modified to support nodes not on existing curves.

On the other hand, the UI should include a new road type which allows different number of lanes at two ends.