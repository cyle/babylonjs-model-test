# Babylon.js model weirdness test

This is just a repo to demo some weirdness with the [Babylon.js](https://github.com/BabylonJS/Babylon.js/) Blender exporter.

By default, it swaps Y and Z coordinates. If you switch this functionality around in the exporter, it works and renders the models in the same way they were made in Blender, but the textures behave strangely.

I uploaded this repo to demonstrate it for the creator of Babylon.js.

## Files

`index.html` contains all of the logic for the scene. Load it up to see the demo. You will see: a trio of cubes (green = Y axis, red = X axis, blue = Z axis) and two rectangles that have one end smaller than the other. They are both the same Blender model (`dummy.blend`) but using two different exporters. The one on the left is using the standard exporter, the one on the right is using a modified exporter.

The `Babylon` directory holds all of the Babylon.js javascript files for Babylon.js version 1.3.2.

`dummy.blend` is the 3D model used to test the Y/Z flip issue. If you open it in Blender (it was created with Blender 2.68a), you will see that the "nose" of the model points along the Y axis.

`io_export_babylon_cyle.py` is my modified version of the Babylon.js-Blender exporter, which simply flips the Y and Z coordinates back to what they "should" be. You can install it into Blender as an addon to test it out.

The `models` directory holds the two versions of the exported `dummy.blend` file -- the "standard" one that was exported with the regular Babylon.js exporter, and the "cyle" one that was exported with my modified exporter.