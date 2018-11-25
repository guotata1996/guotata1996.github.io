Changchun Bridge in Haidian District, Beijing, is an overpass to the south of Summer Palace between the 3rd and 4th Ring Road. I used to cycle across the bridge quite often in my undergraduate.

![Google Map](https://github.com/guotata1996/roadbuilder/raw/master/docs/capture/map.png)

This bridge is a typical Beijing-style overpass, featuring long connections perpendicular to the main road between high & low level.  Obviously this is designed for place & cost saving, but not for high speed traffic. Although constructed in the last century, it's concise design still caught my eye when viewd in Google Map.

## Modelling
The image of 2-D Google Map is used directly as the ground texture to ensure everything is drawn at the right place and scale. I mainly used staight lines and bezier curves. As a limitation of the current version, all intersection angles should be greater than 25 degrees to achieve good visual effects.
It took 10 minutes to draw all the segments. Optimation is needed to simplify the meshes, as the termination of the program took some 20 seconds on my mbp.

## Screen Captures
**Bird eye's view towards the North**
![view towards the North](https://github.com/guotata1996/roadbuilder/raw/master/docs/capture/1123_1.png)

**Bird eye's view towards the East**
![view towards the East](https://github.com/guotata1996/roadbuilder/raw/master/docs/capture/1123_4.png)

**Top View**
![top view](https://github.com/guotata1996/roadbuilder/raw/master/docs/capture/1123_5.png)

**Close View of the SE approach bridge**
![the SE approach](https://github.com/guotata1996/roadbuilder/raw/master/docs/capture/1123_2.png)

**From another end**
![the SE approach from another end](https://github.com/guotata1996/roadbuilder/raw/master/docs/capture/1123_3.png)
