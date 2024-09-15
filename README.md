<div align="center">

<a href="https://mechmania.org"><img width="50%" src="https://github.com/MechMania-30/Wiki/blob/main/assets/mm30_logo.png" alt="MechMania 30"></a>

### [website](https://mechmania.org) | [python-starterpack](https://github.com/MechMania-30/python-starterpack) | [java-starterpack](https://github.com/MechMania-30/java-starterpack) | [visualizer](https://github.com/MechMania-30/Visualizer) | [engine](https://github.com/MechMania-30/engine) | wiki

</div>

# Airplanes Wiki
## Contents
- [Overview](#overview)
- [Map](#map)
- [Gameplay](#gameplay)
	- [Mechanics](#mechanics)
	- [Stats](#stats)
- [Planes](#planes)
- [Further Questions](#further-questions)

## Overview:
This will be a 1v1, turn-based game placed on a 2d plane. For each turn, both players will send commands to their airplanes, which then dictate how the planes fly until the next turn.

Each player controls a squadron of planes, and their goal is to shoot down every plane controlled by their opponent while avoiding having their own planes being shot down. The game ends when all planes on one side have been shot down, or the game reaches 500 turns. The winner will be whoever has the greatest number of surviving planes

### Tiebreakers:
Tiebreakers are in descending order
* If plane points left tied, whoever spent the least points shall win
* If points spent tied, whoever did the most damage shall win
* If damage tied, both players get 0.5 wins

## Map:
The map is two dimensional, but it is not grid based. Instead, each plane will be given two coordinates between [-50,50] to represent their position on an x-y grid. Planes that fly out of bounds will be destroyed. Planes spawn on opposite sides (top and bottom) of the map facing each other.

## Gameplay: 
Each plane has a speed, a turning speed, health, range, and spread, and attack. Each turn, a player sends a steer command to each plane, which the plane obeys until the next turn.

### Mechanics:
#### Attack Cone:
Each plane has an attack cone that faces in front of the plane, and any enemy planes with coordinates inside the attack cone at any point during a turn take damage equal to the attack of the plane. When a plane takes more damage than its health, it is destroyed at the end of the turn. The attack cone extends a distance of the range (r) and has a spread angle (θ) defined below.

#### Collision:
Planes also have a fixed size radius of 0.2. If two opposing planes are ever closer than both of their size radii combined, then they have collided, and both will be destroyed at the end of the turn regardless of their health. Note that friendly planes cannot collide.

#### Destruction:
When a plane collides, flies out of bounds, or is reduced to zero or less health, it is destroyed. The plane will then be removed from the map at the **end** of the turn.

#### Steering:
Each turn, you will give all of your planes a steer order between -1 and 1 inclusive. This will cause the planes to fly in the path of a circle corresponding to the plane's speed and turning speed. 

If steer has magnitude 1, then the plane's angle will change by its turning speed over the course of the next turn. Otherwise, steer is directly proportional to how much a plane's angle will change over the next turn. For example, a steer of 0.5 causes the angle to change by half of the plane's turning speed.

A positive steer turns the plane left and causes its angle to increase, a negative steer turns the plane right and causes its angle to decrease.

### Stats
* **Position**: Given as an ordered pair (x,y), this represents a plane's location on a 2d grid
* **Angle**: Given in degrees, this represents the direction a plane is facing. 0 degrees points towards positive x and 90 degrees points towards positive y.
* **Speed**: Each plane travels this distance per turn.
* **Turning Speed**: Each plane can change degrees by this much at most per turn.
* **Health**: Each plane can take this much damage before being destroyed.
* **Range** and **Spread**: These two values define a cone, and any enemy aircraft within this cone will take damage.
* **Damage**: This is how much damage a plane will do to enemy planes within its damage cone.

### Starting Positions:
Players will start will 1000 points with which to buy planes. Then, planes start at y = 45 or y = -45 depending on team, spaced evenly in the x direction.


## Planes:
|Name|Cost|Health|Turn Speed|Speed|Attack|Range|Spread|
|---|---|---|---|---|---|---|---|
|Standard Plane|200|20 hp|15°|2 units/turn|1 hp|5 ft|30°|
|Flying Fortress|300|40 hp|10°|1 units/turn|1 hp|8 ft|30°|
|Thunderbird|200|10 hp|15°|2.5 units/turn|1 hp|5 ft|30°|
|Scrapyard Rescue|100|8 hp|10°|1.5 units/turn|1 hp|4 ft|20°|
|Pigeon|10|1 hp|30°|.5 units/turn|0 hp|0 ft|0°|

# Further questions:
If you need something clarified, don't hesitate to ask! You can contact staff in the [MechMania 30 Discord Server](https://discord.gg/knWWFKTU) through the #ask-a-question-here channel. We'll be providing help throughout the competition!
