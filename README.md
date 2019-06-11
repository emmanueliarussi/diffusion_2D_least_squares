# Least Squares for 2D Color Diffusion in Python

Many Computer Graphics problems can be seen as finding the best set of parameters for a model, given some data. In particular, 2D diffusion consist on propagating color constrains smoothly everywhere over a target image. This algorithm interpolates colors to the full set of pixels setting up a linear system of smoothness constraints (check the docs folder and [this link](https://en.wikipedia.org/wiki/Linear_least_squares#Derivation_of_the_normal_equations) for more details).

![Diffusion result usign 4 input colors.](https://github.com/emmanueliarussi/diffusion_2D_least_squares/blob/master/interpolation_sample.png)

Color constraints for each color channel are specified as follows: 
```python
constraints_r = [(15,30,255,10.),(30,15,127,10.),(45,30,255,10.),(30,45,128,10.)]
constraints_g = [(15,30,0,10.),(30,15,255,10.),(45,30,128,10.),(30,45,128,10.)]
constraints_b = [(15,30,255,10.),(30,15,0,10.),(45,30,0,10.),(30,45,255,10.)]
```
The first two values in the 4-tuple correspond to (x,y) possition of the color constraint. The third value is the R/B/G component and the fourth correspond to the individual weight for the constraint. The example image above shows the interpolation result using 4 different colors. 
