You may ask yourself, actually what Gen7 provides me to create my marvellous game?  
This glossary of assets supported will help you figure out.  


## Textures/Sprites

**Description:**  
Texture to be used on sprites or specific objects.

**Usage:**  
Name the asset imported with "name" to be referenced by other objects, and filename for the texture's filename (common formats supported such as PNG, JPG, BMP...); to be placed next to the executable.

**Code/Blocks:** 

```python 
createAssetTexture(Text name, Text filename);
```

**Example:**

```python
# Create our texture asset
createAssetTexture('bg','bg.png')

# Create a background sprite object with a -10 layer
createSprite('BACKGROUND','bg',0,0,640,480,(-10))
```


## Spritesheet

**Description:**  
Spritesheet containing several sprites in one image, to create Spritefont, Tilesets, or Sprite Animation objects.

**Usage:**  
Create the Spritesheet asset, then use it in createSpritefontText, createTileset or createSprite followed by setSpriteAnim/createSpriteWithAnim for a sprite animation.

**Code/Blocks:** 

```python 
createAssetSpriteSheet(Name,lines,columns,condens,fontface,filename);
```

**Example:**

```python

# Create a spritesheet animation, using an image containing 26 sprites in 1 line:
createAssetSpriteSheet("check", 1, 26, "", "", "checkpoint.png");	
createSpriteWithAnim("check", "check", 200, 200, 80, 80, 1, 4, 1);
# 1: loop enabled, 4: change frame every 4 frames

# Create a spritesheet font, with a specific condensation configuration (each sprite takes a specific size, such as "[2,4,1]" -> 1st sprite will take 2 times more space than the third, 2nd will take 4 times more than the third) and the fontface to refer to it when creating the text. You can use the GiveYourFonts utility (https://shatter-box.com/download/giveyourfontsmono/) to generate a spritefont, and its condensation in JSON file.
createAssetSpriteSheet("font", 1, 26, "[2,1,1,1,3,1,1,4]", "ABCDEFGHIJKLMNOPQRSTUVWXYZ", "spritefont2.png");
createSpritefontTextNew("font_text", 20, 150, 20, 100, "AHELLO", "font");
# Create a tileset with the same font, with [0, 1, 2, 3, -2, 0, 1, -1, 2] for the frames (-2 for line jump, -1 for space)
createTilesetNew("tileset", 300, 100, 20, 1, "[0, 1, 2, 3, -2, 0, 1, -1, 2]", "font");
```


## 3D Primitive

**Description:**  
Primitives as basic 3D shapes, to experiment or collision eg. build collision cubes.

**Usage:**  
Create the asset primitive with the according call (createAssetCube(Name)...), and then create the object using the asset with the wanted coordinates.

**Code/Blocks:** 

```python 
createAssetCube(Text name)
createAssetTeapot(Text name)
...
```

**Example:**

```python
# Create our texture asset
createAssetCube("cube");

# Create a cube platform, hide it and add it to collision lists
createObjectwithScale("Platform", "cube",-4.1471,0.0239,-0.1399,7.8596,8.1615,0.0655);
hideObject("Platform");
addToCollisionList("Platform");
```

## 3D Assets

**Description:**  
3D Model with materials and textures exported from a 3D Editor and to be instantiated in scenes.

**Usage:**  
Name the asset imported with "name" to be referenced by other objects, and filename for the model's filename (Wavefront .OBJ); to be placed next to the executable.  
Materials file .MTL and textures in common formats will be automatically imported.

> ❗ _createAssetModel_ automatically creates objects for each shape contained in the model at scene's origin to render it; to modify its properties use Object Management methods (_moveObjectwithRotationScale, disableObject...,_ please refer to the methods glossary) with the shape material name to refer independently to the objects.

**Code/Blocks:**

```python
createAssetModel(Text name, Text filename);
```

**Example:**

```python
# Create our texture asset
createAssetModel("fire", "Multitextured.obj")

# Refer to shapes with mat1 material and move them to a specific position coordinate
setObject("mat1", 0.0, 10.0, 5.0)
# Other shapes will be still rendered at the origin if not specified
```

## Particle systems

**Description:**  
Particle systems imported from external editors (Gen7 Blender plugin) or generated in realtime.  
Not yet released.

**Usage:**  
Not yet released.

**Code/Blocks:** 

```python 
createAssetParticle(Text name, Text filename, int ParticleCount, int FrameCount, float scaleParticle);
```

**Example:**

```python
createAssetParticle("fluidParticleSystem", "anim\_fluid.px", 300, 150, 0.07)
```

**Skybox**

**Description:**  
Skybox for the current scene, using 6 textures imported by the following call.

**Usage:**  
Use the 6 arguments for the 6 textures to be used in the skybox.

**Code/Blocks:**

```python
createAssetSkybox(Text s1, Text s2, Text s3, Text s4, Text s5, Text s6);  
```

**Example:**

```python
# Create our texture asset
createAssetSkybox("sky1.png","sky2.png","sky3.png","sky4.png","sky5.png","sky6.png")
```
