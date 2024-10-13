# P2 Robotica Movil

## OBJECTIVE

In this practice the main task is to configure a F1 car to follow a red line in the middle of the road.

## ALGORITHM

The algorithm implemented is easy to understand and I'll will divide in steps:

1. Set all the variables and the hsv filter
2. Call a function which return the image with a mask
3. Calculate the error to the middle of the road. As the camera is not centered the error is not in the middle of the image.
4. Applies the PID to the speeds.
5. Do it again!

## PROBLEMS

First problem was finding a good filter, I decided to go straight forward to hsv filter which helped to not configure it in every scenario.

Second, and most important, adjusting the PID. In both cases I used a PD. To configure it, it was a trial and error. For being more technical, first thing I did was to adjust the Kp until it finished the whole circuit and only then added the Kd and adjust it also.

For the ackerman was different, I adjusted the Kp worked and then the Kd, and I kept changing both of them until it mostly worked well. After all that, I started adding decimals until it worked the best I could.

## PROVEN IDEAS

Most of what I proved is related to the PID, but I liked how I did the linear speed, It was made with a constant speed to where I substracted the angular speed. With this idea its fast on straight lines and much slower on turns.

## CODE SNIPPETS

As code snippets I'll put the PID values for both of the PIDS:

```python

    # PID for no ackerman
    #Kp_angle = 0.0252
    #Kd_angle = 0.0229
    
    # PID for ackerman
    Kp_angle = 0.00721
    Kd_angle = 0.08359

```

## VIDEO

Note: both time and oscilations are bigger due the capture of the video. Time is almost 4 or 5 seconds higher. Also oscilation is more noticeable in Ackerman in non Ackerman is almost the same.

No ackerman video x2 speed:

[p2_no_ackerman.webm](https://github.com/user-attachments/assets/c4ef8824-1961-467f-801e-b96d684f828e)

Ackerman video x2 speed:

[p2_ackerman_x2.webm](https://github.com/user-attachments/assets/ab7997f5-03e5-44e8-8cd4-03c7b263f7f3)


