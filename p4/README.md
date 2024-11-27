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

This is a screenchot of the map expanded:

![Captura desde 2024-11-27 22-18-44](https://github.com/user-attachments/assets/7e91da00-3265-4f4d-beee-0b69a918e393)

## MOVEMENT

Just find the minimun index of the submatrix, changing them to real coords, find the angle and making atan2 to them.


## VIDEO

Video of the car moving, and changing objective before arriving:

[Grabación de pantalla desde 2024-11-27 22-22-45.webm](https://github.com/user-attachments/assets/93238c90-62cc-435f-a8a6-f0c642334994)

