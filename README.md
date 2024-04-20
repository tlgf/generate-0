# generate-0

My goal with this project is to create two pieces of software
with the functionalities:

## `generate`

Generates a stream of images representing the trajectory of a 2D particle and
a target trajectory.
_In other words, a line following exercise._

### Particle Trajectory

The particle's trajectory is determined from 2 inputs to the program:

1. Heading - an angle between 0 and 180 degrees.
2. Velocity - a scalar between 0 and 100, to be related to a distance/time quantity.

These can be provided by
A human via a USB HID device (keyboard)
OR
A binary interface (TBD but thinking `sockets`)

### Target Trajectory

The target trajectory will be generated randomly as a curve.
There will be constraints (TBD) on the sharpest radius etc allowable.

## `0`

Process the stream of images from `generate` to determine:

* Current coordinates of the particle
* Delta of the particle from the target trajectory

These values then are consumed by a control algorithm to output:

1. Heading
2. Velocity

And pack these values into the expected binary interface format expected by `generate`.
It will send/post this data structure using the transport (likely `sockets`).
