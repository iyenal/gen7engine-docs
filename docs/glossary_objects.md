You may ask yourself, actually what Gen7 provides me to create my marvellous game?  
This glossary of assets supported will help you answer this.  
 

## Primitives

**Description:**  
Basic 3D primitives.

**Usage:**  
Create the primitive with the following calls and chose a name that will be used to instantiate them.

**Code/Blocks:**

```python
createAssetPlane(Text name);  
createAssetTeapot(Text name);  
createAssetCone(Text name);  
createAssetTorus(Text name);  
createAssetSphere(Text name);  
createAssetCube(Text name);  
```

**Example:**

```python
# Create our primitive library
createAssetCube("cube")
createAssetPlane("plane")
createAssetSphere("sphere")
createAssetTeapot("teapot")
createAssetCone("cone")
createAssetTorus("torus")

# Create a scene object named "obj1" and using a plane with coordinates posX, pY, pZ, rotationX, rY, rZ, scaleX, scaleY, scaleZ
createObjectwithRotationScale("obj1", "plane", 0.0, 1.0, \-20.0, 90.0, 0, 0, 5, 1.0, 6)
```

## Textures

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
createAssetTexture("fonttexture", "spritefont.png")

# Create a spritefont object in our scene with the previous texture
createSpritefontText("my\_text", 20, 20, 30, 0.6, 1, 26, str(x), "ABCDEFGHIJKLMNOPQRSTUVWXYZ", "fonttexture")
```

## 3D Assets

**Description:**  
3D Model with materials and textures exported from a 3D Editor and to be instantiated in scenes.

**Usage:**  
Name the asset imported with "name" to be referenced by other objects, and filename for the model's filename (Wavefront .OBJ); to be placed next to the executable.  
Materials file .MTL and textures in common formats will be automatically imported.

> Quote
> 
> ![❗](https://twemoji.maxcdn.com/2/72x72/2757.png)_createAssetModel_ automatically creates objects for each shape contained in the model at scene's origin to render it; to modify its properties use Object Management methods (_moveObjectwithRotationScale, disableObject...,_ please refer to the methods glossary) with the shape material name to refer independently to the objects.

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