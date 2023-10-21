### Main available methods

The following methods are available either in Python or Visual Programming blocks, and are interfaced to the internal engine API for best performance.
However this may not represent all the calls available, so please check (Complete Glossary)[glossary_all.md] to have all the calls on hand.

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

2D Specific:
```python
createSpritefontText(Text name, int xpos, int ypos, int fontsize, float condens, int lines, int columns, Text text, Text fontface, Text spritefont);
createSpriteWithCoords(Text name, Text asset, float x, float y, float sizeX, float sizeY, float t0, float t1, float t2, float t3, int layer);
createSpriteWithColor(Text name, Text asset, float x, float y, float sizeX, float sizeY, int r, int g, int b, int layer);
createSprite(Text name, Text asset, float x, float y, float sizeX, float sizeY, int layer);
createText(int xpos, int ypos, int r, int g, int b, float fontsize, Text text);
moveSprite(Text name, float x, float y, int layer);
setSprite(Text name, float x, float y, float sizeX, float sizeY, int layer);
updateSprite(Text name, Text asset);
deleteSpritefontText(Text name);
```

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
