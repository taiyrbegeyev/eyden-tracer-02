# Practical Assignment 2
## Problem 2.2
### Encapsulate camera and primitives from main application logic (Points 5)
TBA
## Problem 2.3
### The Surface-Shader Concept (Points 10 + 10 + 30)
TBA
## Problem 2.4
### Phong Shading and Point Light sources
TBA
## Problem 2.5
### Shadows (Points 20)
To add more realism to the phong model we want now to incorporate shadows into it. Proceed as follows:
- Implement the method ```Occluded()``` in the ```CScene``` class, which should check if something blocks the light.
- Modify ```CShaderPhong::Shade()``` to check for occlusion.
If everything is implemented correct your images should look like this:

![]()
## Problem 2.6
### Area Lights (Points 20)
As you have learned in the last exercise, shadows can add important visual information to an image. Until now we have only considered point lights. Point lights create _hard shadows_ because a point light can not be partly occluded and is either blocked or not. To render more realistic shadows we need amore advanced light source. _Area Lights_ are able to produce _soft shadows_ which are more natural. In this exercise we implement a ```CLightArea``` (in LightArea.h) which is defined by four points in space:
- Calculate the normal and the area of the LightArea in the constructor.
- Calculate the intensity as described in the lecture by generating a random sample position on the area light (using ```dgm::random::U()``` and bi-linear interpolation).
- Add ```CLightArea areaLight(&scene, lightIntensity, Vec3f(-1.5f, 10.0f, -1.5f), Vec3f(1.5f, 10.0f, 1.5f), Vec3f(1.5f, 10.0f, -1.5f), Vec3f(-1.5f, 10.0f, 1.5f));``` to main.cpp and remove the point lights.
- Render an image with 1000 shadow rays per pixel
If everything is implemented correct your images should look like this:

![]()
