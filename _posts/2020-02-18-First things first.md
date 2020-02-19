---
title: The Waag FabLab 1/8 (3D Printing)
tags:
- Cura
- 3D Printing
- 3D Slicing
- Maker Tips

desc: Documentation about 3D printer in the lab
layout: post
---
First things first, the lab !
Today Michelle have introduce the lab's machines to me ( Or maybe she introduce me to the machine ?).
I've decided to write a guide for futur new people in the lab. Hope it will be useful... 
<!-- more -->

### 3D Printers
First of all, let's talk about the 3D printer of the lab.
The lab has 3 operationnal 3D printer at the moment. (Maybe two more with a bit of intern magic)

- IMG

The first one I've met is the Prusa I3mk3. This machine is basically a Prusa I3 clone but with a lot of improvement that are very appreciable.

- IMG

So when you already have a piece to print. You first need to slice it using a slicer (like Cura or Slic3r for example).
The simpler, the better. Cura v4.4.1 already have the Prusa I3 mk3 in its preset. So We're gonna use it.

When you lauch Cura for the first time, you'll have to add a new 3D printer.

<img src="{{site.baseurl}}/assets/img/post-fablab/cura-init.JPG">

In the list of the non-networked printers, select Prusa i3 Mk3/Mk3s in the Prusa3D category

<img src="{{site.baseurl}}/assets/img/post-fablab/cura-prusa.JPG">

The printer should now be added into Cura.
So now you can prepare your STL file to be printed.
I'll do a simple test with a calibration Cube like so :

<img src="{{site.baseurl}}/assets/img/post-fablab/cura-cube.JPG">

Before slicing our part. We need to setup the material we will be using. You can use generic PLA and ajust the temperature then onto the machine. But if you'll use often the same plastics, then you'd better to add a custom one.

To do so, click on the material dropdown :
<img src="{{site.baseurl}}/assets/img/post-fablab/cura-material.JPG">

If you click on "PLA", you'll discover that cura has a lot of material from different manufacturer in its presets. 
<img src="{{site.baseurl}}/assets/img/post-fablab/cura-material.JPG">

If your material isn't inside you may create your own... To do so click onto "Manage material". Then you may create a new material from scratch or by duplicate an existing one. Then you may ajust the melting temperature, the retractation distance ... according to the manufacturer or to your test. Their is a lot of calibration file online to tuned the settings of your printer or your material settings. Good luck !

It may be a bit time consumming to find the setting by testing, but it is a good way to learn about 3D printing and to be able to make a diagnostic if something wrong append to your print.

Let's assume that you have your material ready for now. Let's configure the print settings.
I wanted to test a cool feature of the new version of Cura, the adaptative filling.
When your are preparing your part to be 3D printed, you have to tuned a few setting on the right.

<img src="{{site.baseurl}}/assets/img/post-fablab/cura-setting.JPG">

First a all you have to choose the slice thickness of the print. As you may know, 3D printer work by adding melted platics layer by layer. This first parameters is basically the thickness of these layer. It is even considered as the "quality" of the print. But actually (and unfortunatly) its quality depends on lots of other thing. The more the layer thickness will be high, the less you'll be able to see the layer on the side of your piece.

<img src="{{site.baseurl}}/assets/img/post-fablab/cura-layer.JPG">

But remind that, the thinner your layers are, the more time it will required to be printed. The previous pictures is a good comparison to get that thing.

For our test, layer of 0.2mm is pretty decent. 
So lets move to the infill parameter. Infill is a very particular thing. To save time, developpers of 3D slicers added some very cool stratey for infilling a 3D part. The most common strategy is to build 3D grid pattern inside the part, instead of filling is completly. This is saving time, and plastic ! But it is influencing the solidity of the part as well as its quality.

If the infill is too low, the outer wall may deform during the print and the printhead won't be able to grow them anymore. For the same reason, the rooftop of the piece will probably be bad as well becaux its need support to print.

Generally setting the infill to 20% or 25% do the job. But you have a large plane parralel to the buildplate, then you may push the infill a bit further. That leads me to gradual infill. Gradual infill is a smart way of generating infill in your part. It is only recommended if you care about the aspect of your part. (And if you don't care about its mechanical performance).
This option will generate infill gradually (Low infill at the bottom, high infill at the top or under top surface). This way you'll have the perfect balance between time, material, quality. 

<img src="{{site.baseurl}}/assets/gif/post-fablab/cura-gradual.gif">

You may see some red spot on your piece like me :
<img src="{{site.baseurl}}/assets/img/post-fablab/cura-red.JPG">

These red region mean that there aren't support enough by the previous layers. And they may not be well printed. To prevent that, you may activate the "generate support" option. It will generate a kind of removable scaffolding under the red region. You can ajust the maximum support angle that your printer can achieve without failing doing test with calibration parts. After some time you may probabaly reach between 60° and 40° of angle with a decent printer.

<img src="{{site.baseurl}}/assets/img/post-fablab/cura-angle.JPG">

WIP













