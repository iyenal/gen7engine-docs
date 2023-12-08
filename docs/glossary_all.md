### All methods available

Following are all the methods you can use in Gen7. In case of new additions, it'll be updated first here, before being documented in Methods and Objects glossary.

Note that Micropython modules are available too:

Math support: https://docs.micropython.org/en/v1.11/library/math.html  
Random generation support: https://docs.micropython.org/en/latest/library/random.html (available as import urandom -> urandom.randrange(...))   
JSON support: https://docs.micropython.org/en/v1.11/library/ujson.html  

```python
enableRenderTexturePixel();
enableRenderWireframe();
enableRenderSolid();
enableRenderTexture();
enableRenderShaded();
moveCamera2D(float x,float y);
setCamera2D(float x,float y);
moveCamera(float x,float y,float z,float rx,float ry,float rz);
setCamera(float x,float y,float z,float rx,float ry,float rz);

dumpSceneObjects();
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

createAssetSkybox(Text s1,Text s2,Text s3,Text s4,Text s5,Text s6);
createAssetPlane(Text name);
createAssetTeapot(Text name);
createAssetCone(Text name);
createAssetTorus(Text name);
createAssetSphere(Text name);
createAssetCube(Text name);
Text createAssetTiled(Text filename); // Returns the tileset data (text) to be used directly in createTileset
createAssetModel(Text name,Text filename);
createAssetParticle(Text name,Text filename,int ParticleCount,int FrameCount,float scaleParticle);
createAssetSpriteSheet(Text name,int lines,int columns,Text condens,Text fontface,Text filename);
createAssetTexture(Text name,Text filename);

showObject(Text name);
hideObject(Text name);
enableObject(Text name);
disableObject(Text name);
deleteObjectClass(Text name);
removeFromCollisionList(Text objname);
createLog(Text text);
cleanLog();
createText(int xpos,int ypos,int r,int g,int b,float fontsize,Text text);
deleteLight(Text name);
setLight(Text name,float x,int y,int z,int r,int g,int b,int intensity);
createLight(Text name,float x,int y,int z,int r,int g,int b,int intensity);

float getCameraRZ();
float getCameraRY();
float getCameraRX();
float getCameraPZ();
float getCameraPY();
float getCameraPX();
// getClass returns objects that start with the name, while others return only ones that have the exact same
// Returns a string in the form “3,4,5” for IDs 3, 4 and 5 for example. Just use “IntArray=[int(i) for i in getObject.split(‘,’)]” to convert it to an int array.
Text getListSpritesClassID(Text name);
Text getListObjectsClassID(Text name);
Text getListSpritesID(Text name);
Text getListObjectsID(Text name);
int isObjectClass(Text class,Text fullname);

Text getSpriteName(int ID);
Text getObjectName(int ID);
int getObjectID(Text name);
float getSpriteLayer(Text name);
float getObjectSZ(Text name); // All getObject works with sprites too
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
int getSpriteFrame(Text name);

setSpriteFrame(Text name,int frame);
setSpriteAsset(Text name,Text asset);
moveSprite(Text name,float x,float y,int layer);
setSpriteCoords(Text name,float t0,float t1,float t2,float t3);
setSpriteScale(Text name,float sX,float sY);
setSpriteLayer(Text name,int layer);
setSpritePos(Text name,float x,float y);
setSprite(Text name,float x,float y,float sX,float sY,int layer);
createTilesetUniqueOnly(Text name,int id,int xpos,int ypos,int fontsize,int layer,Text tilesetChar,Text spritesheet);
setSpritefontText(Text name,Text text);
deleteObject(Text name);
deleteSpritefontText(Text name);
createTilesetUnique(Text name,int xpos,int ypos,int fontsize,int layer,Text tilesetChar,Text spritesheet);
createTileset(Text name,int xpos,int ypos,int fontsize,int layer,Text tilesetChar,Text spritesheet);
createSpritefontText(Text name,int xpos,int ypos,int fontsize,int layer,Text text,Text spritesheet);
setSpriteFrameTex(Text name,int frame,int save);
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
LoadScene(Text folder_scene);
LoadSceneAssets(Text folder_scene);
CleanAllScene();
CleanAllModels();
writeFile(Text filename,Text text);
Text openFile(Text filename);
int timeGetFPS();
int timeUpdateFPS();
setTargetFPS(int tF);
float timeSinceFrameMs();
int timeSinceStartup(); // Is resetted at scene change
Text getPlatform();

checkCollisionState(); // Internal, is automatically called
saveCollisionState(); // Internal, is automatically called
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
```
