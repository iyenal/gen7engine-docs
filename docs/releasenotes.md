# Release Notes

Full release information can be found in the release Discord server: https://discord.gg/pXdeUqb

### PSPHDC22 - 13/03/2022

Micropython port to Wii

### PSPHDC22 - 18/08/2022

Micropython port to PSP  
PSPHDC22 Presentation: https://www.youtube.com/watch?v=E6X1y7F8St8  
PSPHDC21: https://youtu.be/PEJV0e9ot60?t=14914  
PSPHDC20: https://www.youtube.com/watch?v=RnZFg98ajDs  

### 18/09/2022

SDL Backend implementation

### 06/12/2022

Opening and creating projects from custom folders, Monaco editor freeze fix, C-implemented collision detection, size fix for primitives.
Harmonised the coordinate management for both sprites and 3D objects.
Collision routines
Heap memory issues fixed

### 11/12/2022

Method getObject now use lookup table
New: isCollisionX, isCollisionY, isCollisionZ for specific axis collision check, setCollisionController to set the object where to check all collisions, and unsetCollision to reset it

### 18/12/2022

Method setSprite and moveSprite now obsolete, replaced by the more generic setObject and moveObject

### 25/12/2022

Implemented collision system for 2D objects, fixed incorrect returns by getObjectSX/SY for sprites
Implemented 2 collision modes: by axis, the engine automatically corrects the object's position to respect the collision while keeping most of the wanted movement, or normal collision

### 07/01/2022

Important change: all assets must be now in an "assets" folder next to executable
Blender plugin for automatic box colliders exports

### 22/01/2022

Repository for plugins

### 02/02/2022

- Added high-DPI screens support (4k monitors+)
- Fixed file encoding issues 
