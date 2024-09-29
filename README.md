# P1 Robotica Movil

## OBJECTIVE

In this practice the main task is to create a reactive algorithm implemented with a finite state machine for a working vacuum cleaner.

## FSM DIAGRAM

There's four states in this fsm:
1. Starting state: does an spiral to clean more area, until it bumps something.
2. Backward state: goes back for 0.8 seconds.
3. Forward state: goes forward until it bumps something.
4. Turn state: turns to a random direction, it last a random amount of time between 0.5 to 1.5 seconds.


  ![FSM MACHINE DIAGRAM](https://github.com/user-attachments/assets/2f87d625-794d-4bc2-babe-656a56f946ee)

## PROBLEMS

In this excercise the main problem was to find a good method to clean the whole house without using any map or self location. Problems I've found are related to what do when it bumps, later on I'll explain most of the ideas I have proven to try to solve this problem. With all this said, I will make a list of some of the encountered problems:

1. Adjusting velocities.
2. Sometimes bumper event last longer than expected.
3. Find better ways to turn the vacuum cleaner.
4. Create an spiral with less gaps inside.
5. Check if the robot clean nicely.

## PROVEN IDEAS

Here I am going to show some I have tried in the course of the practice, but at the end they did not work well or I found better ways to make them.

### Turn ways

When we talk about turning I tried five different ways of making the turn, they are listed right here:

1. When there was a hit on the left side I turned right ans the same for the other side. (rejected)
2. Turn a random angle during a stablished time. (rejected)
3. Turn a random angle during a random time. (worked better but rejected)
4. Turn a stablished angle but random direction during a stablished time. (rejected)
5. Turn a stablished angle but random diraction during a random time. (selected)

After many tries, last option work significally better tan others.

### Forward ways

I tried two different ways of going forward.
1. Just go straight.
2. Go straight and turn a little to the side where it had turned in the turn state.

Both worked well, but the second way prone to get stuck more times. So I decided first way.

### Backward ways

This time I only adjust the time to go back

### Spiral 

In this case I tried two main ways:

1. More angular speed
2. More linear speed

In my case worked better the linear. After deciding this I had to prove how much increment worked better, which ended up being += 0.001

## CODE SNIPPETS

In this section there's nothing really exciting to show as the practice does not show much difficulties, any ways I will show a snippet on how to decide the direction.

```python

# If the random number is over 0.5 turns to left
            # else to right
            angle = 1.2
            direction = random.uniform(0, 1)
            if direction >= 0.5:
                angle *= -1
            # It also takes a random time to rotate




            time_rotating = random.uniform(0.5,1.5)

```

## VIDEO

[p1_robotica_movil_x2_new.webm](https://github.com/user-attachments/assets/9f16bd43-bc35-4852-8636-1c4e10d78e80)


