# Teardown mapping documentation. 

These are all supported XML tags with their settings.

<a href="lua.md">Lua documentation here</a>

## Scene
    - shadowsVolume (vec) - World bounds in meters. Everything inside this volume cast shadows. Keep as small as possible.

## Environment	
    - skybox (string) - The dds file used as skybox. Search path is data/env.
    - skyboxtint (vec) - The sky box color tint
    - skyboxbrightness (float) - The sky box brightness scale
    - skyboxrot (float) - The sky box rotation around y axis. Use this to determine angle of sun shadows.
    - ambient (float) - Determines how much the skybox will light up the scene.
    - fogColor (vec) - Color used for distance fog
    - fogParams (vec4) - Four fog parameters: fog start, fog end, fog amount, fog exponent (higher gives steeper falloff along y axis)
    - sunBrightness (float?) - Light contribution by sun (gives directional shadows)
    - sunColorTint (vec) - Color tint of sunlight. Multiplied with brightest spot in skybox.
    - sunDir (int?) - Direction of sunlight. A value of zero will point from brightest spot in skybox 
    - sunSpread (int?) - Divergence of sunlight as a fraction. A value of 0.05 will blur shadows 5 cm per meter
    - sunLength (int?) - Maximum length of sunlight shadows. AS low as possible for best performance.
    - sunFogScale (float) - Volumetric fog caused by sunlight
    - sunGlare (float) - Sun glare scaling
    - exposure (vec2) - Limits for automatic exposure, min max
    - brightness (unknown, possibly a float) - Desired scene brightness that controls automatic exposure. Set higher for brighter scene.
    - wetness (int?) - Base wetness
    - puddleamount (int?) - Puddle coverage. Fraction between zero and one.
    - puddlesize (float) - Puddle size
    - rain (int?) - Amount of rain
    - nightlight (bool) - If set to false, all lights tagged night will be removed
    - ambience (string) - Environment sound path [volume]

## Group 
    - layer (string?, value?) - Override parameter in group. Example dynamic=true will set any parameter named dynamic of every entity in this group to true

# Compound objects

## Instance 
    - file (unknown) - Load prefab instance

## Body 	
    - dynamic (bool) - Set to true for a movable body
    - desc (string) - Text description

## Vox 			
    - file(string) - Magicavoxel .vox file. Search path data/vox
    - object (string?) - Vox file sub object
    - pos (vec3) - Position in meters
    - rot (vec3) - Rotation in degrees (e.g. 0-360) (example value to rotate backwards: rot="0 180 0")
    - scale (int?) - Voxel scaling. Use for background objects only with disabled collisions.

## Light		
    - type (string) - Type of light source. Can be sphere, cone or area
    - color (vec) - Light color RGB value. Do not include intensity here. All values should be in between zero and one.
    - scale (float?) - Light intensity
    - angle (int)	- Cone angle in the case of a cone light type
    - penumbra (int?) - Penumbra angle in the case of a cone type
    - size (float) - Light radius in case of sphere of cone. Width and height in case of area light. Specified in meters.
    - unshadowed (float) - A small distance in meters that is always unshadowed. Useful to avoid shadows from a nearby light fixture and/or emissive light surface.
    - fogscale (float?) - Volumetric fog amount
    - fogiter (float?) - Quality of volumetric fog. Usually leave at one. For very bright and important lights, you may set increase it to avoid flickering.
    - sound (string) - path [volume]
    - glare (int?) - Glare amount

## SpawnPoint
    - pos (vec3) - Position in meters
    - rot (vec3) - Rotation in degrees (e.g. 0-360) (example value to rotate backwards: rot="0 180 0")

## Location

## Enemy

## VoxScript 
    - file (string) - possibly the voxscript file to be executed?

## Joint 
    - type (string) - ball, hinge or prismatic
    - size (float) - The joint attachment point search radius
    - rotstrength (float) - Rotational strength of joint. Set to zero for freely rotating joint.
    - rotspring (float) - Springyness of joint. Set to zero for pure damper. Keep below one to stay stable.
    - collide (bool) - Allow collisions between jointed shapes
    - limits (int?) - Optional min and max angle of hinge rotation
    - sound (bool) -Joint makes sound

## Water	
    - type (string) - Geometry type: box or polygon
    - size (Vec2) - Size in meters along X and Z axes. Only applicable to box
    - depth (int?) - Depth along negative y axis
    - wave (float) - Large wave amount
    - ripple (float) - Small wave amount
    - motion (float) - Sideways motion amount
    - foam (float) - Foam amount

## VoxBox 		
    - size (vec) - Size in voxels
    - brush (string) - Magicavoxel file to use as brush or 3D texture
    - object (string?) - Brush file subobject, if any
    - offset (vec) - Offset into voxel brush, in voxels along x, y and z
    - material (string) - Set material if no brush is given. Should be one of glass, wood, masonry, plaster, metal, heavymetal, rock, dirt, foliage, unphysical
    - color (vec) - Color tint, RGB values between zero and one
    - pbr (vec4) - Additinal PBR properties - reflectivity, shinyness, metalness and emissive. Emissive is in range 0-32, the others in range 0-1

## Voxagon 
    - brush (string) - Magicavoxel file to use as brush or 3D texture
    - object (string) - Brush subobject, if any
    - offset (vec) - Offset into voxel brush, in voxels along x, y and z
    - axis (str) - Extrusion axis as seen in vox file. For floors this is z, for walls it is y
    - extrude (unknown) - Extrution along axis

## Vehicle	
    - driven (bool) - 
    - sound (string) - Sound preset (small, medium, truck, v8), optional pitch
    - spring (float) - Stiffness of suspension spring
    - damping (float) - Suspension damping
    - topspeed (float) - Top speed in km/h
    - acceleration (float) - Combine with strength to control how fast the car accelerates.
    - strength (float) - Engine strength
    - antispin (float) - Prevent wheels from spinning during acceleration. between zero and one.
    - antiroll (float) - Prevent vehicle from tipping over. Similar to lowering the center of mass, but looks less weird
    - difflock (float) - Differential control. Zero is open differential, one is fully locked. Use zero for regular cars, one for heavy vehicles.
    - steerassist (float) - Arcade steering. This improves handling a lot. Should normally never be more than 1.0
    - friction (float) - Tire friction. For most cars leave as is. For small cars and sports car, increase slightly.

## Wheel 
    - drive (vec2) - Control how much of the engine power is applied to wheel. Normally 0.0 or 1.0.
    - steer (float)
    - travel (vec2) - Suspension travel distance from normal position, min max along Y axis.
    
## Rope 
    - size (float) - Rope attachment point radius
    - color (vec) - Rope color
    - slack (float) - Desired slack. Can be negative for more tension.
    - strength (float) - Rope strength. Negative is infinite.
    - maxstretch (float) - Rope breaks if stretching more than this
    Exemple of rope usage
    
### Usage
```xml
<rope>
    <!-- Attach points -->
    <location pos="1.0 1.0 0.0"/>
    <location pos="10.0 1.0 0.0"/>
</rope>
```
    
    
## Boundary

## Screen
    - pos (vec3) - Position in meters
    - rot (vec3) - Rotation in degrees (e.g. 0-360) (example value to rotate backwards: rot="0 180 0")
    - size (vec2) - width and height
    - bulge (vec2) - bulge height at center
    - resolution (vec2) - render resolution
    - script (string) - script location relative to data folder
    - enabled (bool) - 
    - interactive (false)
    - emissive (float?)
    - fxraster (int or bool?)
    - fxca (int or bool?)
    - fxnosie( int or bool?)
    - fxglitch(int or bool?)



## Trigger
    - type(string)
    - size (int)
    - sound (string)
    - soundramp (float)
    
# Script
    - file (string) -
