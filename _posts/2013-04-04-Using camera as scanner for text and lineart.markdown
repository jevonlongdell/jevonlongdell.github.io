---
layout: post
title:  "Using a camera as scanner for text and lineart"
date:   2013-03-04 12:00:00 +1300
categories: photos tramping 
---
A quick way to add a diagram to lecture notes is to take a picture with your camera, you then have the problem of converting the photo into a monochrome image. To speed this up I wrote a gimp plugin to do this. It basically follows the method outlined in [http://www.gimp.org/tutorials/Sketch_Effect/](http://www.gimp.org/tutorials/Sketch_Effect/) and uses [Otsu's method](http://en.wikipedia.org/wiki/Otsu's_method) to decide on the threshold.

To install it put the [python file](https://github.com/jevonlongdell/gimp-plugins/blob/master/makemono.py)
into `~/.gimp-2.8/plugins` making sure it is set executable.

To use it select "Make monochrome" from the "Image" menu in Gimp.


Some examples are:

![picture of tap]({{site.baseurl}}/images/small_tap.gif)
![picture of tap]({{site.baseurl}}/images/small_tap.jpg)

![picture of piston]({{site.baseurl}}/images/small_piston.gif)
![picture of piston]({{site.baseurl}}/images/small_piston.jpg)

![picture of text]({{site.baseurl}}/images/small_text.gif)
![picture of text]({{site.baseurl}}/images/small_text.jpg)

### Update for Ubuntu 20.04:


- The location that the plugin should be placed is `~/config/GIMP/2.10/plug-ins/`
- Python gimp plugins don't work on Ubuntu 20.04 out of the box, see [this discussion](https://discourse.ubuntu.com/t/gimp-woes-in-20-04/15828/8). The commands below should fix this.

```bash
wget http://archive.ubuntu.com/ubuntu/pool/universe/p/pygtk/python-gtk2_2.24.0-6_amd64.deb
wget http://archive.ubuntu.com/ubuntu/pool/universe/g/gimp/gimp-python_2.10.8-2_amd64.deb

sudo apt install gimp gimp-plugin-registry gimp-gmic
sudo apt install python python-cairo python-gobject-2

sudo dpkg -i python-gtk2_2.24.0-6_amd64.deb
sudo dpkg -i gimp-python_2.10.8-2_amd64.deb
````

- I had to alter the plug-in code very slightly (see github)
