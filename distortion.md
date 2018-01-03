# Distortion

## Brown-Conrady model

The Brown-Conrady model corrects both for radial distortion and for tangential distortion caused by physical elements in lens not being perfectly aligned. The latter is also known as decentering distortion.

```
x_u = x_d + (x_d-x_c)(K_1*r^2+K_2*r_4+K_3*r_6) + (P_1*(r^2 + 2*(x_d-x_c)^2)+2*P_2*(x_d-x_c)*(y_d-y_c))*(1+P_3*r^2+P_4*r^4+...)

y_u = y_d + (y_d-y_c)(K_1*r^2+K_2*r_4+K_3*r_6) + (P_2*(r^2 + 2*(y_d-y_c)^2)+2*P_1*(x_d-x_c)*(y_d-y_c))*(1+P_3*r^2+P_4*r^4+...)
```
where:

`(x_d, y_d)` = distorted image point as projected on image plane using specified lens,

`(x_u, y_u)` = undistorted image point as projected by an ideal pinhole camera,

`(x_c, y_c)` = distortion center (assumed to be the principal point),

`K_n` = n th radial distortion coefficient,

`P_n` = n th tangential distortion coefficient,

`r = sqrt((x_d - x_c)^2 + (y_d - y_c)^2)`

## Divison model

To model radial distortion, the division model typically provides a more accurate approximation than Brown-Conrady`s even-order polynomial model:

```
x_u = x_c + (x_d - x_c) / (1+K_1*r^2+K_2*r_4+K_3*r_6)

y_u = y_c + (y_d - y_c) / (1+K_1*r^2+K_2*r_4+K_3*r_6)
```