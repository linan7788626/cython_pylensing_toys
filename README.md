# cython_pylensing_toys

## Introduction
This is an improved version of my **_Glensing Toy_** with **_Cython_** boosting. **_Glensing Toy_** is a software to demonstrate what gravitational lensing is. By using some combinations of mouse and keys, you can control sources and lenses. **_Glensing Toy_** shows both sources (white balls) and lensed images (blue arcs). Moreover, caustic and critical curves of this lensing system are shown by default (Figure 1). By pressing "f" or "g", you can also take a look at the properties of lenses (Figure 3), and the simulated observation of the lensing system (Figure 2). 


Figure 1:
![Figure 1](./screen_shots/figure0.png)
Figure 2:  
![Figure 2](./screen_shots/figure1.png)
Figure 3:
![Figure 3](./screen_shots/figure2.png)


1. Dependences:  
	* [Python2.7](https://www.python.org), [Numpy](http://www.numpy.org), [Pygame](http://www.pygame.org), [Cython](http://cython.github.io) and [SDL](https://www.libsdl.org).
	* If you are using Linux, you can install all these packages using the default package manager, for example, apt-get for Debian and Ubuntu, yum for Fedora and Redhat,  pacman for Archlinux and so on.
	* If you are using Mac, I would recommend [Macports](https://www.macports.org) or [Homebrew](http://brew.sh) to install these packages.
	* My favorite way to install all the dependences is using [Anaconda](https://store.continuum.io/cshop/anaconda/). Once you installed Anaconda, the environment of python2.7 is ready.

	THEN

	```bash
	$ conda install -c https://conda.binstar.org/quasiben pygame
	```
	If your SDL is not installed in /usr/local/lib, you need to link it to the default directory.
	```bash
	$ sudo ln /opt/local/lib/libSDL-1.2.0.dylib /usr/local/lib/libSDL-1.2.0.dylib
	```
	* I have got the first version of a standalone APP for Mac using [py2app](http://pythonhosted.org/py2app/). You can find it here: [Lensing Toy](https://www.dropbox.com/s/uuaf13nfcoet44c/Lensing%20Toy.zip?dl=0).
	

2. Installation:  
	* Clone it or download it,    

	THEN
	```bash
	$ cd libs
	$ python2.7 setup.py build_ext --inplace
	```
	OR
	```bash
	$ cd libs
	$ ./make_so
	```
3. Code Running:  

	```bash
	$ cd ../
	$ python2.7 multiple_sources.py
	```


##Usage

1. How to control sources:  
You can use the left click of the mouse to control the sources, but first of all, you need to hold one NUM key to choose a source you want to handle. Here, "1" stands for the first source, "2~9" stand for the added sources. Defaultly, one source is hown. Furthermore,  bullets below show the details on controling the source you pick.
  * Holding a NUM key to pick a source you want to play with. 
  * Holding "w" and left click, you can move you mouse to move the position of the source.
  * Holding "s" and left click, you can move you mouse vertically to change the size of the source.
  * Holding "e" and left click, you can move you mouse vertically to change the ellipticity of the source, or, horizontally to change the orientation of the source.

2. How to control lenses:  
You can use the right click of the mouse to control the lenses.
Similar with the source, at the same time, you need to press on number key to claim which component you want to control (Here, "1" stands for the main halo, "2~9" stand for the sub halos. ) and  press one key to claim what properties you would like to change. For example, if you want to change the ellipticity and orientation of the main halo: please hold "1", "e" and right click, then move vertically, the ellipticity of the main halo will be changed, move horizontally, the orientation of the main halo will be changed. Because we are using Non-singular Isothermal Ellipsoid (NIE) model in this code, so when you press "s" to change the size of the lens, there are two sizes, one is the Einstein Radius (move your mouse vertically), the other one is the core radius (move your mouse horizontally). If you want to control the subhalos, please hold "2" first, then do everything you want.  
  * Holding a NUM key to pick a component you want to play with. 
  * Holding "w" and right click, you can move you mouse to move the position of the chosen component of the lens.
  * Holding "s" and right click, you can move you mouse vertically to change the Einstein radius of chosen component, or, horizontally to change the Core radius of the chosen component.
  * Holding "e" and right click, you can move you mouse vertically  to change the ellipticity of the chosen component, or, horizontally to change the orientation of the chosen component.

3. How to add or remove satellite galaxies and sources: 
There is only one subhalo intrinsically. However, in our code, we can also add or remove subhalos if needed. So far, you can only add 8 subhalos at most. Similarly, you can also control the number of sources.
  * Hold "=", click the right click to add a subhalo.
  * Hold "-", click the right click to remove the last added subhalo. 
  * Hold "=", click the left click to add a source.
  * Hold "-", click the left click to remove the last added source.

4. Toggles:  
Try "f" and "g". :-)

##Todo List
1. Sources
 - [x] More sources.
 - [x] More models of sources (Sersic, Moffat, Disk\+Bulge...).
 - [ ] Real galaxies images.
 - [ ] Arbitrary pictures (for fun).

2. Lenses
 - [ ] More models of lenses (PIEMD, GNFW, NFW\+Hernquist, Burkert...).
 - [x] Directly input mass sheet.
 - [ ] More satellite galaxies?
 - [ ] Realistic images of satellite galaxies.

3. Algorithm 
 - [ ] Anti-Aliasing.
 - [ ] Better caustic drawer.

5. Time Delay
 - [x] Implementing in twinkles branch.

6. Competition Model
 - [ ] Input lensed images by one person.
 - [ ] Reconstruct it by another one.
 - [ ] Score the matching.

7. Input and Output
 - [ ] Save the parameters of current lensing system, including lenses and sources.
 - [ ] Make the catalog of lensing system to be an input file.
 - [ ] Show all the parameters of current lensing system in real time.
