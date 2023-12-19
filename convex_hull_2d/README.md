# Maxwell's Cut and Build Convex Hull Algorithm

An algorithm that constructs the convex hull of a pointset using a method I call the "Cut and Build" method. Visuals highlighting the process are printed along the way.

-----------

* Generate a set of points
* Using the left-most point and the right-most point, draw a line. Use that line to divide remaining points into sets above that line and below that line
* Arrange those two sets in order of ascending angle relative to an anchor point
    * For the above list, anchor point is "lower left corner" of plot, with angle relative to the "ground"
    * For the below list, anchor point is "upper right corner" of plot, with angle relative to the "ceiling"
* We now generate a list of convex hull points using an incremental algorithm over the set of above points and below points. We start the convex hull with the left and right endpoints for both the above pointsets and below pointsets
* Using the dot-product of two vectors, we determine if each next iterated point forms a convex angle. If it does, add it to the list. If it does not, keep removing points until the angle is convex again
