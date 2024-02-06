# Fork

This fork of https://github.com/intel-health/Equirec2Perspec adds RunEquirec2Perspec.py which calls GetPerspective 100 times and times the amount
of time taken to do 100 calls to the function.  It uses a large image that is consisent with other work described in the Blog series related to
optimizing equirectangular conversion to rectilinear views.  The initial blog can be found at
https://intel-health.github.io/optimizing-equirectangular-conversion/1-Introduction%20to%20360%20Degree%20Representation/index.html.

# Equirec2Perspec
## Introduction
<strong>Equirec2Perspec</strong> is a python tool to split equirectangular panorama into normal perspective view.

## Panorama
Given an input of 360 degree panorama
<center><img src="src/image.jpg"></center>

## Perpective
Split panorama into perspective view with given parameters
<center><img src="src/perspective.jpg"></center>

## Usage
```python
import os
import cv2 
import Equirec2Perspec as E2P 

if __name__ == '__main__':
    equ = E2P.Equirectangular('src/image.jpg')    # Load equirectangular image
    
    #
    # FOV unit is degree 
    # theta is z-axis angle(right direction is positive, left direction is negative)
    # phi is y-axis angle(up direction positive, down direction negative)
    # height and width is output image dimension 
    #
    img = equ.GetPerspective(60, 0, 0, 720, 1080) # Specify parameters(FOV, theta, phi, height, width)
```

