# P4 Robotica Movil

## OBJECTIVE

In this practice we are making a robo taxi which gets you to a position marked in the map

## ALGORITHM

The algorithm works like this:

If there's a new target:
1. Expand node with bfs until reaching the car and saves obstacles
2. Does some over iterations to reach behind the car
3. Adds cost to the grid around the obstacle

If we are navigating:
1. Takes a submatrix of all around values
2. Looks up for the minimun
3. Goes in that direction

## PROBLEMS

In this practice I have got some problems, those are listed below:

1. Generating right the map (Firstly i did the real distance to the endpoint, not accumulative)
2. As the matrix is in (y,x) instead of (x,y), there were some problems finding errors there
3. Lastly generating right the obstacles values

## COST MAP

The cost map is simply made by advancing node with the philosophy of breadth first search. I save the value to the center and then adds the diatnce from last node to actual node.
Also I had to save the obstacles to make the grid close to them weight more, so the car doesnt get close.

## MOVEMENT

Just find the minimun index of the submatrix, changing them to real coords, find the angle and making atan2 to them.


## VIDEO

Video of the car moving:
