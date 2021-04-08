# Wrapping error reprex

Reproducible example for IndexOutOfBounds error in OpenSim 4.1 visualizer. The visualizer throws an IndexOutOfBounds error when attempting to display a muscle that has a torus and ellipsoid wrapping surface. The error only occurs at knee angles that require the muscle to wrap around the ellipse. 

Disabling either of the wrapping surfaces eliminates the problem. This problem could likely also be fixed by replacing the torus wrapping surface with a fixed via point, but I would like to be able to reproduce an older SIMM model (Eng et al 2015) and compare it to a different model.

## To reproduce the error

* Open eng_simplified_error_reprex.osim in OpenSim 4.1
* Manually adjust knee_angle_r to 80 degrees or greater
* Visualizer freezes until knee angle is brought back below 80 or above 125 degrees (where the muscle "falls off" the wrapping ellipse) 
* The error is logged in the alert in the bottom right
     * See also `knee wrap error.log` for an example
