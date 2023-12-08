### Main available methods

The following methods are available either in Python or Visual Programming blocks, and are interfaced to the internal engine API for best performance.
However this may not represent all the calls available, so please check (Complete Glossary)[glossary_all.md] to have all the calls on hand.

▶️ Undocumented or unavailable methods? Create an issue to have it added.  
▶️ Questions about some method usage? Create an issue to get more information.

**Internal/External assets:**

```python
createAssetSkybox(Text s1, Text s2, Text s3, Text s4, Text s5, Text s6);
createAssetPlane(Text name);
createAssetTeapot(Text name);
createAssetCone(Text name);
createAssetTorus(Text name);
createAssetSphere(Text name);
createAssetCube(Text name);
createAssetModel(Text name, Text filename);
createAssetParticle(Text name, Text filename, int ParticleCount, int FrameCount, float scaleParticle);
createAssetTexture(Text name, Text filename);
```

**Object Management:**

General:
```python
createObjectwithRotationScale(Text name, Text asset, float x, float y, float z, float rotX, float rotY, float rotZ, float scX, float scY, float scZ);
createObjectwithScale(Text name, Text asset, float x, float y, float z, float scX, float scY, float scZ);
createObjectwithRotation(Text name, Text asset, float x, float y, float z, float rotX, float rotY, float rotZ);
createObject(Text name, Text asset, float x, float y, float z);
setObjectwithRotationScale(Text name, float x, float y, float z, float rotX, float rotY, float rotZ, float scX, float scY, float scZ);
moveObjectwithRotationScale(Text name, float x, float y, float z, float rotX, float rotY, float rotZ, float scX, float scY, float scZ);
setObject(Text name, float x, float y, float z);
enableObject(Text name);
disableObject(Text name);
deleteObject(Text name);
```

ℹ️ setObject, deleteObject, disableObject, enableObject and getObject[...] can all be used with sprite objects too.

2D Specific:
```python
updateSpritefontText(Text name,int xpos,int ypos,int fontsize,int layer,float condens,int lines,int columns,Text text,Text fontface,Text spritefont);
updateSprite(Text name,Text asset);
refreshSpriteSheets();
int getSpriteFrame(Text name);
setSpriteFrameTex(Text name,int frame,int save);
setSpriteFrame(Text name,int frame);
setSpriteAsset(Text name,Text asset);
moveSprite(Text name,float x,float y,int layer);
setSpriteCoords(Text name,float t0,float t1,float t2,float t3);
setSpritePos(Text name,float x,float y);
setSprite(Text name,float x,float y,float sX,float sY,int layer);
setSpritefontText(Text name,Text text);
deleteSpritefontText(Text name);
createTilesetUnique(Text name,int xpos,int ypos,int fontsize,int layer,Text tilesetChar,Text spritesheet);
createTileset(Text name,int xpos,int ypos,int fontsize,int layer,Text tilesetChar,Text spritesheet);
createSpritefontText(Text name,int xpos,int ypos,int fontsize,int layer,Text text,Text spritesheet);
setSpriteAnim(Text name,Text spritesheet,int loopMode,int everyFrame);
createText(int xpos,int ypos,int r,int g,int b,float fontsize,Text text);
createSpriteWithAnim(Text name,Text asset,float x,float y,float sX,float sY,int loopmode,int everyframe,int layer);
createSpriteWithCoords(Text name,Text asset,float x,float y,float sX,float sY,float t0,float t1,float t2,float t3,int layer);
createSpriteWithColor(Text name,Text asset,float x,float y,float sX,float sY,int r,int g,int b,int layer);
createSprite(Text name,Text asset,float x,float y,float sX,float sY,int layer);
```

ℹ️ createTilesetUnique creates corresponding tiles' sprites with unique names (generated from the tileset index and position). It can be used to add specific behavior to special tiles, or to even replace them with "smarter" objects without having to define by hand their location.

**Returns a value:**

```python
float timeSinceFrameMs();
bool isButtonRight();
bool isButtonLeft();
bool isButtonDown();
bool isButtonUp();
bool isButtonY();
bool isButtonX();
bool isButtonB();
bool isButtonA();
float getObjectSZ(Text name);
float getObjectSY(Text name);
float getObjectSX(Text name);
float getObjectRZ(Text name);
float getObjectRY(Text name);
float getObjectRX(Text name);
float getObjectPZ(Text name);
float getObjectPY(Text name);
float getObjectPX(Text name);
Text openFile(Text filename);
int timeSinceStartup();
Text getPlatform();
```

**Get objects lists:**

```python
Text getListSpritesClassID(Text name); # Sprite's name starts with the name given (prefix)
Text getListObjectsClassID(Text name);
Text getListSpritesID(Text name); # Sprite's exact name is the one given
Text getListObjectsID(Text name);
```

⚠️ Returns a string in the form "3,4,5" for IDs 3, 4 and 5 for example. Just use "IntArray=[int(i) for i in getObject.split(',')]" to convert it to an int array.

**Misc:**

```python
moveCamera(float x, float y, float z, float rx, float ry, float rz);
setCamera(float x, float y, float z, float rx, float ry, float rz);
createLog(Text text);
cleanLog();
writeFile(Text filename, Text text);
enableRenderWireframe();
enableRenderSolid();
enableRenderTexture();
enableRenderShaded();
```
