# Hexapod Motion Simulation

This project simulates the movement of a hexapod robot using roll, pitch, and yaw angles. It involves both translations and rotations of the hexapod torso and legs, calculated via inverse kinematics. The hexapod model parameters, motion functions, and control logic are implemented to generate specific motions such as yawing, pitching, rolling, and pure translation.

## Project Structure

### Hexapod Dimensions
The global variables defining the hexapod's dimensions and positions:
- `x1256`, `y1256`: Coordinates of legs 1, 2, 5, 6.
- `x34`, `y34`: Coordinates of legs 3, 4.
- `hx1256`, `hy1256`, `hx34`, `hy34`: Helper variables for hexapod leg calculations.
- `a1`, `a2`, `a3`: Additional geometric parameters of the hexapod.
  
These variables are used to define the initial positions of the legs and the body of the hexapod.

```
global x1256 y1256 x34 y34 hx1256 hy1256 hx34 hy34 a1 a2 a3
a1 = 5;
a2 = 5;
a3 = 5;
hx34 = 4;
hy34 = 0;
hx1256 = hx34 * cos(pi / 3);
hy1256 = hx34 * sin(pi / 3);
x34 = hx34 + a2;
y34 = 0;
x1256 = x34 * cos(pi / 3);
y1256 = x34 * sin(pi / 3);

```
### Roll, Pitch & Yaw Angles
The hexapod's orientation is controlled via roll, pitch, and yaw angles, which are defined as:

```matlab
roll = pi / 12;
pitch = pi / 12;
yaw = pi / 12;

```
### Motion Call Functions

This section simulates different types of motions by adjusting the roll, pitch, and yaw angles. The loops allow the hexapod to perform specific actions such as yawing, moving up and down, and rolling.

- **Yaw Motion**: Rotating around the vertical axis (z-axis).
- **Up and Down Motion**: Translation along the z-axis.
- **Roll and Pitch Motions**: Tilting along the x-axis (roll) and y-axis (pitch).

```matlab
for i = 0:1:5
    yaw_motion = rpy(0, 0, yaw, 0);
    pause(0.25);
    yaw_motion1 = rpy(0, 0, 0, 0);
    pause(0.1);
    yaw_motion2 = rpy(0, 0, -yaw, 0);
    pause(0.25);
    yaw_motion3 = rpy(0, 0, 0, 0);
    pause(0.1);
end

for i = 0:1:5
    pitch_motion = rp(0, pitch);
    pause(0.25);
    pitch_motion1 = rp(0, 0);
    pause(0.1);
    pitch_motion2 = rp(0, -pitch);
    pause(0.25);
    pitch_motion3 = rp(0, 0);
    pause(0.1);
end

```
### Motion Call Functions

This section simulates different types of motions by adjusting the roll, pitch, and yaw angles. The loops allow the hexapod to perform specific actions such as yawing, moving up and down, and rolling.

- **Yaw Motion**: Rotating around the vertical axis (z-axis).
- **Up and Down Motion**: Translation along the z-axis.
- **Roll and Pitch Motions**: Tilting along the x-axis (roll) and y-axis (pitch).

```matlab
for i = 0:1:5
    yaw_motion = rpy(0, 0, yaw, 0);
    pause(0.25);
    yaw_motion1 = rpy(0, 0, 0, 0);
    pause(0.1);
    yaw_motion2 = rpy(0, 0, -yaw, 0);
    pause(0.25);
    yaw_motion3 = rpy(0, 0, 0, 0);
    pause(0.1);
end

for i = 0:1:5
    pitch_motion = rp(0, pitch);
    pause(0.25);
    pitch_motion1 = rp(0, 0);
    pause(0.1);
    pitch_motion2 = rp(0, -pitch);
    pause(0.25);
    pitch_motion3 = rp(0, 0);
    pause(0.1);
end
```


https://github.com/user-attachments/assets/9d920aff-6ca4-44bf-832e-cc613e1dab60






