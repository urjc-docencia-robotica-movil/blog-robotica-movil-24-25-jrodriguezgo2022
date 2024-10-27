# P2 Robotica Movil

## OBJECTIVE

In this practice the main task is to configure a F1 car to avoid obstacles while it follows certain checkpoints given by the profesosrs

## ALGORITHM

I am implementing a VFF algorithm for this practice, I will explain it dividing it in to pieces:

1. Gets the target
2. Checks if has arrived to it
3. Generates the attractive force
4. Generates the repulsive force
5. Calculates the resultant
6. Asigns a speed to V and W
7. Repeat!

## PROBLEMS

In this practice I have got some problems, those are listed below:

1. Generate a good repulsive vector
2. Try the better module for the attractive speed
3. Balance attractive force with repulsive force
4. Asigns speed to each case

These three are the niggest problems I have encountered.

## REPULSIVE VECTOR

In the repulsive vector I did some trials:
1. I just took all measures an do the average (did not work well).
2. I gave weights to all them depending on the angle
3. I restructured the weights so from a certain angle it is zero
4. Finally I made the repulsive force only 90º or -90º, it remains part 3 weights

I also discard laser distances over 3 meters.

Lastly, I will put in here the function I used for generate the vector, as it is not a common function:

<p style="font-size:18px">The function is defined as:</p>

$\[
f(x) = \frac{150}{1 + e^x}
$\]

Being x the distance to the objective.

## ATTRACTIVE VECTOR

Vector which leads you to the target the max is set to three and the min to 1.5.

## CODE SNIPPETS

Like this I made the vector 90º or -90º:

```python

    if my_coord[1] > 0: 
        x_coord = new_module * math.cos(-math.pi/2)
        y_coord = new_module * math.sin(-math.pi/2)
    else:
        x_coord = new_module * math.cos(math.pi/2)
        y_coord = new_module * math.sin(math.pi/2)

```

## VIDEO

Note: for some reason this practice goes so laggy on my pc, even with it makes the circuit entirely.

Video of obstacle avoidance x2:

[obstacle_avoidance_p3_x2.webm](https://github.com/user-attachments/assets/8fe1b3bd-2c77-4edb-aa22-4fa1d09588d8)
