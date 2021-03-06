READ ME: Spiraloid Blender 2.80 essentials setup

Unless stated otherwise, many of these scripts and addons are a collaboration of others from the blender open source community. 
I am posting the python scripts here because as I have updated or modified the code to suit my own workflows. 
No warranty or support should be implied. I am merely standing on the shoulders of others. 
I try to reference the original authors and link to forum posts or webpages as I can in the history. 
Any concerns, feel free to contact me and I can adjust. 
Just want to share as I get with other awesome blender users.

cheers.

-bay

Installation:

WARNING!!!: Blender users may wish to backup your current configuration before installing in case something goes wrong you can undo. For example on a Mac, creating a compressed zip archive of this folder:

~/Library/Application Support/Blender/2.80

(or on windows 10)

%APPDATA%\Blender Foundation\Blender\2.80\

is a good idea.
(This is where blender stores all your preference data)

Next

Install blender 2.80 (if you have not already done so) https://www.blender.org/download/releases/2-79/

This has been updated for use with daily build:
Date 2019-02-02 00:58
Hash: 4ef09cf937f2

you can download from here:
https://builder.blender.org/download/blender-2.80-0bbff8a71138-win64.zip

tip: copy the zip content folder named "blender-2.80.0-git.8c87af74409a-windows64" into your C:\Program Files\Blender\
run the blender.exe folder (set permissions to be admin so you can run scripts etc)

btw: there may be more recent version here:
https://builder.blender.org/download/

Open Blender and on the top bar choose: Edit “edit > Preferences”. 

Under the Add-ons section, use button at top right that says “Install...”

Browse to the folder where you downloaded this archive and install all add-ons in the addon folder as you would normally.

(word to the wise, be sure to activate them after you click "install add-on from file" immediately as it’s a long list to search through if you don't)

Next

Go to the keymap section, use button on top right that says “Import...”
be sure to turn off Keep Original as I turned off some of the default hotkeys to make mine work.

Againt, Browse to this folder and import “spiraloid_hotkeys.py” in the Startup sub folder.

Save user preferences.

Next

Open the startup_scene.blend file in the Startup sub folder (next to where you found the hotkeys)

If everything went according to plan, everything should be installed. if everything worked, hit the spacebar and the mirrored subdiv cube in front of you should bounce.

This is the fast preview playback script I wrote. Hit spacebar to stop playing time and note that the current frame has returned whatever frame you were editing before you hit spacebar.

CONGRATS! Everything is installed. hit “ctrl U” to save the startup scene and all the UI and settings so that every time your launch blender or hit file new, this is what you get. Home state.

--

Here’s a list of basic usage of my essentials.. Wherever possible I tried to leave it the default so you could still google. Right Mouse Button (RMB) to select, drag etc. x to delete. A to deselect all or Toggle. GXYZ RXYZ SXYZ alt-S to move on normal etc all still work.

My adjustments to the UI or hotkeys are made for me, so bear in mind I have a lot of habits from using nearly every 3D tool for the last 25 years in major productions. I understand that the hotkey memorization I do is abnormal, but this kind of configuration helps me switch tools and makes my work faster.

Quick Start of most frequently used changes. and more detailed guide cane be found here: https://github.com/spiraloid/Spiraloid-Toolkit-for-Blender/wiki

General 3D Navigation:

Alt LMB. orbits the camera. Alt RMB dolly’s the camera Alt Shift pans the camera. (I know I know. Trust me Maya users, alt shift drag to pan rocks. But I did put in alt MMB too for the SGI greybeards who like fighting the mouse wheel)

speaking of

Alt shift mouse Wheel dolly’s the camera in and out for 3D and 2D views.

Mouse wheel over a 3D view and the view will spin around the aimpoint like a sculptors turntable. If you have a weighted throw mouse wheel like an MX master25 this is amazing.

You can set the aimpoint by hitting alt-a (or cmd-a on a Mac). This is actually an add-on I had to write. It moves the cursor and aims to that. Trust me. Every other way to do this sucked.

Alt ` set view to current camera Alt 1 set view to front Alt 2 set view to left Alt 3 set view to top Alt 4 set view to right Alt 5 set view to bottom Alt 6 set view to back

Alt mouse wheel scrubs though frames Cmd mouse wheel scrubs though keyframes of selected objects.

Alt mouse wheel will grow and shrink bone selection in pose mode.


Up Arrow goes to first frame Down Arrow goes to last frame Left Arrow goes to next keyframe for selected object. Right Arrow goes to previous keyframe for selected object. Alt Right Arrow goes to next frame Alt Left Arrow goes to previous frame

Ctrl Return does a playblast of whatever window is under your mouse.

WEIGHT PAINT Mode Ctrl shift Drag will drag a radial gradient of the current weight, tool and strength. Ctrl ALT Drag will drag a radial gradient of the current weight, tool and strength.

EDIT Mode 1 vertices, 2 edges, 3 faces 

Addon notes:

(unless the addon states I wrote it, these are grabbed from elsewhere online and copyrtight, support etc stays with the original author. I'm just collecting them in this repo to have them in once place. See source code documentation of each addon for more info)

MirrorAllVertexGroups.py

this script adds a "Mirror all Vertex Groups" item to the vertex groups menu that will copy all vertex groups from one side of a model to the other for a symmetrical mesh. this means you can paint weights for the left hand, legs, torso etc and then mirror all weights to the other side (the other side weights are overwritten). There is a small options menu that comes up to let you choose an axis, copy direction etc.

FastPreview.py

This adds a "preview" button to the timeline. when pressed this will playback (or preview) the current range from the beginning and when pressed again, will return the current frame to the frame before preview. This is most usefull when refining a pose and wanting to see how it feels in motion without having to constantly place the edit frame over and over again. When animating, I recommend binding it to the spacebar using view3d.fast_preview (and moving the search to another key, like command+s) Note: when zoomed into a range in the graph editor, the fast preview will use that range. view all to play from beginning.

AimAtSelected.py

This adds an "Aim Selected" item to the view menu. This will move the cursor to the selected element and aim the camera at it. I recomend binding it to alt+a or cmd+a

ApplyMeshPose.py

this adds a new menu item to the pose menu on an amature  "Appy > Apply Pose as Rest Pose with Mesh”.  This will sets the current skeleton pose as the new rest pose AND update the skinned meshes to use the current shape as the new edit shape. Essential for sculpting or modelling on meshes with an armature and skinning already attached.

must have third party free addons:

AssetGen : This will decimated a symmetrical model with vertex color (dynamesh, dynatopo, medium, scan etc) into a low poly game ready asset that is automatically UV mapped with baked w albedo and orm textures and automatically exports a .glb file at a desired polycount for upload to sketchfab or to put into your game.  more info here:
https://www.youtube.com/watch?v=TH5CZMdrASw
https://github.com/Linko-3D/AssetGen

FastCarve:
quick boolean tool
https://www.youtube.com/watch?v=Con5uMDwRQ0&list=PLboXykqtm8dxZxhA1P-iyy_vpis04Hyem
https://github.com/jayanam/fast-carve

I also strongly suggest these paid addons:

https://blendermarket.com/products/voxel-heat-diffuse-skinning

https://blendermarket.com/products/auto-rig-pro

http://renderhjs.net/textools/blender/

https://gumroad.com/l/uvpackmaster

https://lollypopman.com/2016/08/09/addon-shapekey-helpers/

https://en.blender.org/index.php/Extensions:2.6/Py/Scripts/Animation/Corrective_Shape_Key

https://blendermarket.com/products/asset-management?ref=2

https://github.com/knekke/blender_addons

https://www.blendernation.com/2016/06/15/addon-zaloopok/

good luck with your art.

-b

my 3D Graphic Novel "Nanite Fulcrum" http://spiraloid.net/nanitefulcrum

my patreon https://www.patreon.com/spiraloid
