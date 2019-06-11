# Least Squares for 2D Color Diffusion  

Many graphics problems can be seen as finding the best set of parameters for a model, given some data. In particular, 2D diffusion consist on propagating color constrains smoothly everywhere over a target image. 

![Diffusion result usign 4 input colors.][https://github.com/emmanueliarussi/diffusion_2D_least_squares/blob/master/interpolation_sample.png]

Color constraints for each color channel are specified as follows: 
```python
constraints_r = [(15,30,255,10.),(30,15,127,10.),(45,30,255,10.),(30,45,128,10.)]
constraints_g = [(15,30,0,10.),(30,15,255,10.),(45,30,128,10.),(30,45,128,10.)]
constraints_b = [(15,30,255,10.),(30,15,0,10.),(45,30,0,10.),(30,45,255,10.)]
```
The first two values in the 4-tuple correspond to (x,y) possition of the color constraint. The third value is the R/B/G component and the fourth correspond to the individual weight for the constraint. The algorithm interpolates constraints to the full set of pixels using Least Squares (please, check the doc folder for more details). The example image above shows the interpolation result using 4 different colors. 
