---
title: "Blender tricks"
---

# Blender tricks

This page is to serve as a collection of tricks using [Blender](https://blender.org).

## Generating cubed decorations

Used in my map [Median](/pages/maps#median), this serves as a generator for the decorations in the map.  
The goal was to generate a square or rectangle of cubes all having randomized height.

Start by adding your template cube into your Blender project.  
In this case, we are using a 1x1x1m standard cube.

![Black and white cube in the centre of the Blender viewport.](https://sharex.777.tf/ShareX/2023/08/blender_2JCIaVFx6G.png)

You can then hide it and add a second sample Plane Mesh.  
On that Plane, add a new Geometry Node system then use this arrangement.

![Screenshot of the Blender Geometry Nodes showing how to generate an array of cubes with randomized height.](https://sharex.777.tf/ShareX/2023/08/blender_sI7pidnQed.png)

Don't forget to select your template cube in the `Object Info` so it gets reproduced everywhere.  
It should result in something like this.

![Screenshot of Blender showing a generated bunch of cubes with variable heights.](https://sharex.777.tf/ShareX/2023/08/blender_woYeH8oNOR.png)

But wait, now you cannot export it like this.  
For now, you can hide the Plane Mesh and create once again a new one.  
Create a new Geometry Node setup on it using the following one.

![Screenshot of Blender showing a simple three node design to be able to export geometry nodes.](https://sharex.777.tf/ShareX/2023/08/blender_Yvnqwzavxs.png)

Now select this last object and export it.  
Congrats, you now have nice decorations!
