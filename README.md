# aseSlab 0.1


###### Official page: [kidmarscat.itch.io/aseslab](https://kidmarscat.itch.io/aseslab)

**Important: Since aseSlab has made enough money now to cover for the price of Aseprite — a sincerely bloated, broken, and incompetent piece of software as it still is — I feel free now to release the project as pay-what-you-want AND as Unlicense/CC0, that is, the code now is in the public domain, and everyone is free to use it, reuse it, improve it, and share it. Maybe if the Aseprite devs stop making stupid plushies, and sit down and actually add features that people obviously want (this was a hit beyond even my expectation), this script could be one of them. Otherwise, thank you to to everyone who purchased it. Fuck Aseprite. Peace.**

**P.S. You can still donate if you want, but only do so if you can.**

```aseSlab``` is a voxel suite for **Aseprite** that allows you to live preview your pixel art as a 3D voxel model for easy creation of voxel art right from the program itself, with multiple useful features such as:

* Custom voxel shape, size, and borders
* Two projection modes: orthographic and perspective.
* Full 3D rotation, with mouse support
* Depth map rendering
* ... and more!

Also included with the suite are sample projects to use as the basis for your own voxel models; examples for both live animation previewing and multi-layered rendering; and also, as a bonus, a Python script for converting Aseprite exports from ```.png``` to ```.vox``` (using Ken Silverman's Slabspri/Slab6 voxel standard). 

### What It Does:
- ```aseSlab``` will display the currently selected sprite in full 3D as a series of floating squares or "voxels", with multiple settings to choose from, to control the preview and test the resulting voxel model.
- The preview can also be rendered to sprite at any time, mostly preserving the preview's settings, on a transparent background and with the original sprite's palette.

### How to use it:
- Open the script from the ```File > Scripts``` menu. This will bring the dialog up with a preview of the sprite in 3D. You can move the preview around using the left mouse button if needed.
- Select "Render all layers" if the Aseprite project has been set-up with multiple layers in mind. This means that multiple 3D elements can be drawn separately and on top of each other, which will then be converted to flat slices in the live render.
- In the "Sprite settings" tab, select "Set the current sprite as the render target" if it isn't selected already by default. You can also use the grid settings or current selection to define the model's width and height.
- You may also want to adjust the tile size and the amount of tiles per column and row. The voxel model will be rendered by drawing each tile from back to front, going left to right and top to bottom, with the last frame in the grid representing the front of the model.
- In "Voxel settings", you can tweak the size, padding and roundness of the squares that make up the voxel model. These settings will also affect the "Render to Sprite" export.
- In "Camera settings", you can change the projection type, distance, and rotation, to test how the model will look from different angles. This can also be controlled with the right and middle mouse buttons.
- In "Render settings", you can toggle whether to draw borders around the voxels; whether to use the currently selected brush background color as the image background; to hide inner voxels in unoptimized models for faster render times; and to display the voxels as a depth map by displaying their distance to the camera as different shades of gray.
- In "Manual Input" you can set the values of multiple options that are otherwise only controllable using sliders, such as the camera rotation and voxel size.
- And finally, you can refresh the preview if it hasn't updated automatically; hide or show the settings for full screen preview; reset the view, which is useful for when the model moves outside the preview; reset the rotation with one click; render the current preview to sprite; get information about the current render (amount of voxels, and render time); and finally, exit the dialog.

### Other useful stuff:
- We have bundled in the "examples" subfolder three Aseprite projects showcasing features such as live animation previewing, multi-layer rendering, and a stress test for how the script will behave when the amount of voxels is in the five digits.
- We have also bundled in the "samples" subfolder another three Aseprite projects for models such as a sphere, cube and pyramid, to use as the basis for your own voxel creations.
- Finally, in the "extra" subfolder, we have included a Python script that can export to a ```.vox``` file, compatible with voxel art software such as [Magicavoxel](https://ephtracy.github.io) and [Slab6](http://advsys.net/ken/download.htm#slab6). For more information, read ```png2vox.txt```. Be aware that the script **requires** Python 3.10 or newer installed on your system.

### Important:
- For models that aren't optimized, i.e. they contain pixel data that will not be visible on the 3D render, it's very much encouraged for "hide inner voxels" to be turned on. However, the opposite is also true: The script may take more time trying to cull the voxels than actually rendering them when the model is already optimized, in which case it's better to turn the setting off.
- The rendering has been optimized to the limit of what a single Lua script can do within the constraints of the Aseprite API. However, do know that the graphics environment in which the preview is rendered is severely lacking in optimization, and that this accounts for most of the slow down when the voxel count reaches five digits.
- There are multiple bugs described in the script itself, which are outside of the script's control due to being the result of the Aseprite API, and also the underlying code of the Aseprite application itself. None of them should break the script's functionality, but do check out the provided help pop-ups in the program to learn more about these bugs and how to work with them. As soon as I find a solution around them, they will be implemented and available online for paying users.
- Finally, do understand that the goal of this script is to serve as a live preview for drawing voxels in Aseprite, and that any further features, such as more advanced rendering of voxels, exporting to popular voxel formats, and elaborate voxel art animations such as turntable rotations, should be made with more appropriate software, such as the aforementioned MagicaVoxel, Qubicle, Blender, etc.

### Setup:
- In **Aseprite**, go to ```File > Scripts > Open Scripts``` Folder. This should open an Explorer window at ```<Aseprite program folder>/scripts```.
- Copy the file ```aseSlab.lua``` to this folder and in ```File > Scripts``` select ```Rescan Scripts Folder```.
- The script should now be available for use.

In case of a bug, or any other kind of unintentional behavior, feel free to contact me at ```kidmarscat [at] gmail [dot] com``` or leave a comment on the ```aseSlab``` download page, [```kidmarscat.itch.io/aseslab```](https://kidmarscat.itch.io/aseslab)

### On a final note...
Developing scripts for Aseprite has mostly been a thankless effort, especially due to the total lack of support from the Aseprite developers in maintaining the API and fixing bugs that affect all script developers. In an ideal world, these kind of features would be available already — the existence of this script proves how easy it would be to implement them, if anyone gave a crap.

Do know that, in the end, it's less about the money than it is about making a point, with the hopes that one day this project is made obsolete by Aseprite itself. Edit: And I made my point fuck you David Capello you hack lmao.

### ChangeLog
| Date    | Version | What changed
| ------- | --------|-------------------------------------------------------
| 2024-09 | 0.1 | First release, including every essential feature considered for the project.
