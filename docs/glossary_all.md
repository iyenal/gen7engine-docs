### All methods available

Following are all the methods you can use in Gen7. In case of new additions, it'll be updated first here, before being documented in Methods and Objects glossary.

Note that Micropython modules are available too:

Math support: https://docs.micropython.org/en/v1.11/library/math.html  
Random generation support: https://docs.micropython.org/en/latest/library/random.html (available as import urandom -> urandom.randrange(...))   
JSON support: https://docs.micropython.org/en/v1.11/library/ujson.html  

```python
/* This file was automatically generated.  Do not edit! */
createAssetSkybox(Text s1,Text s2,Text s3,Text s4,Text s5,Text s6);
createAssetPlane(Text name);
createAssetTeapot(Text name);
createAssetCone(Text name);
createAssetTorus(Text name);
createAssetSphere(Text name);
createAssetCube(Text name);
createAssetModel(Text name,Text filename);
createAssetParticle(Text name,Text filename,int ParticleCount,int FrameCount,float scaleParticle);
createAssetSpriteSheet(Text name,int lines,int columns,Text condens,Text fontface,Text filename);
createAssetTexture(Text name,Text filename);
checkCollisionState(); # Internal but can be used for tricks (force collision calculation manually)
saveCollisionState(); # Internal but can be used for tricks (force collision calculation manually)
setCollidedUniqueName(Text newName);
Text getLastCollisionName();
int getLastCollisionID();
resetCollisionController();
resetCollisionList();
addToCollisionList(Text objname);
setCollisionController(Text objname,int type);
int isCollisionZ(Text one,Text two);
int isCollisionY(Text one,Text two);
int isCollisionX(Text one,Text two);
int isCollisionBox(Text one,Text two);
int isTriggerRight();
int isTriggerLeft();
int isTriggerDown();
int isTriggerUp();
int isTriggerY();
int isTriggerX();
int isTriggerB();
int isTriggerA();
int isButtonRight();
int isButtonLeft();
int isButtonDown();
int isButtonUp();
int isButtonY();
int isButtonX();
int isButtonB();
int isButtonA();
showObject(Text name);
hideObject(Text name);
enableObject(Text name);
disableObject(Text name);
deleteObjectClass(Text name);
removeFromCollisionList(Text objname);
createLog(Text text);
cleanLog();
createText(int xpos,int ypos,int r,int g,int b,float fontsize,Text text);
float getCameraRZ();
float getCameraRY();
float getCameraRX();
float getCameraPZ();
float getCameraPY();
float getCameraPX();
Text getListSpritesClassID(Text name);
Text getListObjectsClassID(Text name);
Text getListSpritesID(Text name);
Text getListObjectsID(Text name);
int isObjectClass(Text class,Text fullname);
Text getSpriteName(int ID);
Text getObjectName(int ID);
int getObjectID(Text name);
float getObjectSZ(Text name);
float getObjectSY(Text name);
float getObjectSX(Text name);
float getObjectRZ(Text name);
float getObjectRY(Text name);
float getObjectRX(Text name);
float getObjectPZ(Text name);
float getObjectPY(Text name);
float getObjectPX(Text name);
int getObjectEnabled(Text name);
int getObjectType(Text name);
updateSpritefontText(Text name,int xpos,int ypos,int fontsize,int layer,float condens,int lines,int columns,Text text,Text fontface,Text spritefont);
updateSprite(Text name,Text asset);
refreshSpriteSheets();
int getSpriteFrame(Text name);
setSpriteFrameTex(Text name,int frame,int save);
setSpriteFrame(Text name,int frame);
setSpriteAsset(Text name,Text asset);
moveSprite(Text name,float x,float y,int layer);
setSpriteCoords(Text name,float t0,float t1,float t2,float t3);
setSpritePos(Text name,float x,float y,float sX,float sY,int layer);
setSprite(Text name,float x,float y,float sX,float sY,int layer);
setSpritefontText(Text name,Text text);
deleteObject(Text name);
deleteSpritefontText(Text name);
createTilesetUnique(Text name,int xpos,int ypos,int fontsize,int layer,Text tilesetChar,Text spritesheet);
createTileset(Text name,int xpos,int ypos,int fontsize,int layer,Text tilesetChar,Text spritesheet);
createSpritefontText(Text name,int xpos,int ypos,int fontsize,int layer,Text text,Text spritesheet);
setSpriteAnim(Text name,Text spritesheet,int loopMode,int everyFrame);
createSpriteWithAnim(Text name,Text asset,float x,float y,float sX,float sY,int loopmode,int everyframe,int layer);
createSpriteWithCoords(Text name,Text asset,float x,float y,float sX,float sY,float t0,float t1,float t2,float t3,int layer);
createSpriteWithColor(Text name,Text asset,float x,float y,float sX,float sY,int r,int g,int b,int layer);
createSprite(Text name,Text asset,float x,float y,float sX,float sY,int layer);
float placeholder3(Text name,float x,float y,float z);
float placeholder2(Text name,float x,float y,float z);
float placeholder1(Text name,float x,float y,float z);
setObjectwithRotationScale(Text name,float x,float y,float z,float rotX,float rotY,float rotZ,float scX,float scY,float scZ);
moveObjectwithRotationScale(Text name,float x,float y,float z,float rotX,float rotY,float rotZ,float scX,float scY,float scZ);
setObjectwithScale(Text name,float x,float y,float z,float scX,float scY,float scZ);
setObject(Text name,float x,float y,float z);
createObjectwithRotationScale(Text name,Text asset,float x,float y,float z,float rotX,float rotY,float rotZ,float scX,float scY,float scZ);
createObjectwithScale(Text name,Text asset,float x,float y,float z,float scX,float scY,float scZ);
createObjectwithRotation(Text name,Text asset,float x,float y,float z,float rotX,float rotY,float rotZ);
createObject(Text name,Text asset,float px,float py,float pz);
writeFile(Text filename,Text text);
Text openFile(Text filename);
int timeGetFPS();
int timeUpdateFPS();
setTargetFPS(int tF);
float timeSinceFrameMs();
int timeSinceStartup();
Text getPlatform();
enableRenderTexturePixel();
enableRenderWireframe();
enableRenderSolid();
enableRenderTexture();
enableRenderShaded();
moveCamera2D(float x,float y);
setCamera2D(float x,float y);
moveCamera(float x,float y,float z,float rx,float ry,float rz);
setCamera(float x,float y,float z,float rx,float ry,float rz);
CleanAllScene();
CleanAllModels();
```
