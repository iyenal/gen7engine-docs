### All methods available

Following are all the methods you can use in Gen7. In case of new additions, it'll be updated first here, before being documented in Methods and Objects glossary.

Note that Micropython modules are available too:

Math support: https://docs.micropython.org/en/v1.11/library/math.html  
Random generation support: https://docs.micropython.org/en/latest/library/random.html (available as import urandom -> urandom.randrange(...))   
JSON support: https://docs.micropython.org/en/v1.11/library/ujson.html  

```python
checkCollisionState();
saveCollisionState();
setCollidedUniqueName(string newName);
string getLastCollisionName();
int getLastCollisionID();
resetCollisionController();
resetCollisionList();
addToCollisionList(string objname);
setCollisionController(string objname,int type);
bool isCollisionZ(string one,string two);
bool isCollisionY(string one,string two);
bool isCollisionX(string one,string two);
bool isCollisionBox(string one,string two);
bool isTriggerRight();
bool isTriggerLeft();
bool isTriggerDown();
bool isTriggerUp();
bool isTriggerY();
bool isTriggerX();
bool isTriggerB();
bool isTriggerA();
bool isButtonRight();
bool isButtonLeft();
bool isButtonDown();
bool isButtonUp();
bool isButtonY();
bool isButtonX();
bool isButtonB();
bool isButtonA();
createAssetSkybox(string s1,string s2,string s3,string s4,string s5,string s6);
createAssetPlane(string name);
createAssetTeapot(string name);
createAssetCone(string name);
createAssetTorus(string name);
createAssetSphere(string name);
createAssetCube(string name);
createAssetModel(string name,string filename);
createAssetParticle(string name,string filename,int ParticleCount,int FrameCount,float scaleParticle);
createAssetTexture(string name,string filename);
showObject(string name);
hideObject(string name);
enableObject(string name);
disableObject(string name);
deleteObjectClass(string name);
removeFromCollisionList(string objname);
createLog(string text);
cleanLog();
createText(int xpos,int ypos,int r,int g,int b,float fontsize,string text);
updateSprite(string name,string asset);
moveSprite(string name,float x,float y,int layer);
setSprite(string name,float x,float y,float sX,float sY,int layer);
float getCameraRZ();
float getCameraRY();
float getCameraRX();
float getCameraPZ();
float getCameraPY();
float getCameraPX();
bool isObjectClass(string class,string fullname);
int(array) getListSpritesID(string name);
int(array) getListObjectsID(string name);
string getSpriteName(int ID);
string getObjectName(int ID);
int getObjectID(string name);
float getObjectSZ(string name);
float getObjectSY(string name);
float getObjectSX(string name);
float getObjectRZ(string name);
float getObjectRY(string name);
float getObjectRX(string name);
float getObjectPZ(string name);
float getObjectPY(string name);
float getObjectPX(string name);
bool getObjectEnabled(string name);
int getObjectType(string name);
createSpriteTilemap(string name,int xpos,int ypos,int fontsize,int layer,float condens,int lines,int columns,string text,string fontface,string spritefont);
updateSpritefontText(string name,int xpos,int ypos,int fontsize,int layer,float condens,int lines,int columns,string text,string fontface,string spritefont);
deleteObject(string name);
deleteSpritefontText(string name);
createSpritefontText(string name,int xpos,int ypos,int fontsize,int layer,float condens,int lines,int columns,string text,string fontface,string spritefont);
createSpriteWithCoords(string name,string asset,float x,float y,float sX,float sY,float t0,float t1,float t2,float t3,int layer);
createSpriteWithColor(string name,string asset,float x,float y,float sX,float sY,int r,int g,int b,int layer);
createSprite(string name,string asset,float x,float y,float sX,float sY,int layer);
float placeholder3(string name,float x,float y,float z);
float placeholder2(string name,float x,float y,float z);
float placeholder1(string name,float x,float y,float z);
setObjectwithRotationScale(string name,float x,float y,float z,float rotX,float rotY,float rotZ,float scX,float scY,float scZ);
moveObjectwithRotationScale(string name,float x,float y,float z,float rotX,float rotY,float rotZ,float scX,float scY,float scZ);
setObjectwithScale(string name,float x,float y,float z,float scX,float scY,float scZ);
setObject(string name,float x,float y,float z);
createObjectwithRotationScale(string name,string asset,float x,float y,float z,float rotX,float rotY,float rotZ,float scX,float scY,float scZ);
createObjectwithScale(string name,string asset,float x,float y,float z,float scX,float scY,float scZ);
createObjectwithRotation(string name,string asset,float x,float y,float z,float rotX,float rotY,float rotZ);
createObject(string name,string asset,float px,float py,float pz);
writeFile(string filename,string text);
string openFile(string filename);
int timeGetFPS();
int timeUpdateFPS();
setTargetFPS(int tF);
float timeSinceFrameMs();
int timeSinceStartup();
string getPlatform();
enableRenderWireframe();
enableRenderSolid();
enableRenderTexture();
enableRenderShaded();
moveCamera2D(float x,float y);
setCamera2D(float x,float y);
moveCamera(float x,float y,float z,float rx,float ry,float rz);
setCamera(float x,float y,float z,float rx,float ry,float rz);
```
