Use these script examples and templates to help you develop parts of your game/application.
These can be recreated in Visual Programming with the corresponding blocks.

## Collectable Objects

**Description:**  
Collect all objects whose names starts by 'coin', and delete them in the scene.

**Usage:**  
Copy and paste directly the code. Add code for player movements (or use directly the 2d_platformer) template.

**Script:**

```python
coins = 0

def start():
  setTargetFPS(60)

  createAssetTexture('pl_str','2d_player.png')
  createAssetTexture('coin_sp','2d_coin.png')

  createSprite('player','pl_str',70,200,50,50,0)
  createSprite('coin01','coin_sp',200,100,50,50,0)
  createSprite('coin02','coin_sp',350,100,50,50,0)
  addToCollisionList('coin01')
  addToCollisionList('coin02')
  setCollisionController('player',0)

def update():
  global coins

  # Move the Player with your code
  # [CODE]
  # eg. moveSprite('player',x,y,layer), check 2d_platformer template for complete example
  
  # If last collision is a collision with an object that starts with "coin" name
  if isObjectClass('coin',(getLastCollisionName())):
    deleteObject((getLastCollisionName()))
    coins = coins + 1
```
    
## Orbit in 3D space

**Description:**  
Orbit the camera around a point in 3D Space. Method originally developed for the gamejam.

**Usage:**  
Copy and paste directly the code.

**Script:**

```python
import math

# orbit around the player
def orbitAroundPoint(ox, oy, deg):
  global player_name

  # x and z to orbit
  px = getObjectPX(player_name)
  pz = getObjectPY(player_name)+3
  rad = math.radians(-deg-180)
  qx = ox + math.cos(rad) * (px - ox) - math.sin(rad) * (pz - oy)
  qz = oy + math.sin(rad) * (px - ox) + math.cos(rad) * (pz - oy)
  setCameraLeg(qx, qz, 0, 25, 0, deg) #deg, camera legacy system
```

## Third Person View player

**Description:**  
Third Person View player, suitable to TPV games or racing, can be changed to an FPS system

**Usage:**  
Copy and paste directly the code.

**Script:**

```python
import math

def playerTPVmovements():
    global player_name

    # check input
    if (isButtonRight()):
      # createLog("R")
      rad = math.radians(-getObjectRZ(player_name))
      nx = (speed * math.cos(rad))
      ny = (speed * math.sin(rad))
      moveObjectwithRotationScale(player_name, nx,ny,0, 0,0,0,0,0,0)

    if (isButtonLeft()):
      #createLog("L")
      rad = math.radians(-getObjectRZ(player_name)+180)
      nx = (speed * math.cos(rad))
      ny = (speed * math.sin(rad))
      moveObjectwithRotationScale(player_name, nx,ny,0, 0,0,0,0,0,0)
      # orbitAroundPoint(getObjectPX(player_name), getObjectPY(player_name), -getObjectRZ(player_name))

    if (isButtonDown()):
      #createLog("U")
      rad = math.radians(-getObjectRZ(player_name)-90)
      nx = (speed * math.cos(rad))
      ny = (speed * math.sin(rad))
      moveObjectwithRotationScale(player_name, nx,ny,0, 0,0,0,0,0,0)

    if (isButtonUp()):
      #createLog("U")
      rad = math.radians(getObjectRZ(player_name)+90)
      nx = (speed * math.cos(rad))
      ny = (speed * math.sin(rad))
      moveObjectwithRotationScale(player_name, nx,ny,0, 0,0,0,0,0,0)

    if (isButtonX()):
      # createLog("T")
      moveObjectwithRotationScale(player_name, 0,0,0, 0,0,speed*10, 0,0,0)

    if (isButtonY()):
      # createLog("B")
      moveObjectwithRotationScale(player_name, 0,0,0, 0,0,-speed*10, 0,0,0)

    orbitAroundPoint(getObjectPX(player_name), getObjectPY(player_name), -getObjectRZ(player_name))
```


## Create a 3D Collision space

**Description:**  
3D Collision space to setup a simple 3D FPS/TPS player scene.

**Usage:**  
Copy and paste directly the code. The collision shapes have been generated with the Blender plugin.

**Script:**

```python
def start():
  setTargetFPS(60)
  setCamera(7.5,0,18,30,0,90)
  # createAssetModel('dungeon','dungeon.obj')
  addToCollisionList('coin02')

  # Creating the 3D collider space
  createAssetCube("cube");
  createObjectwithScale("Platform", "cube",-4.1471,0.0239,-0.1399,7.8596,8.1615,0.0655);hideObject("Platform");addToCollisionList("Platform");
  createObjectwithScale("coin1", "cube",-4.4481,0.3545,1.2464,0.4237,1.0,1.0);hideObject("coin1");addToCollisionList("coin1");
  createObjectwithScale("Walls.001", "cube",-3.913,7.5618,2.2565,8.1334,0.4529,2.172);hideObject("Walls.001");addToCollisionList("Walls.001");
  createObjectwithScale("coin2", "cube",-9.3749,0.3545,1.2464,0.4237,1.0,1.0);hideObject("coin2");addToCollisionList("coin2");
  createObjectwithScale("Walls.003", "cube",-3.913,-7.7849,2.2565,8.1334,0.4529,2.172);hideObject("Walls.003");addToCollisionList("Walls.003");
  createObjectwithScale("Walls.004", "cube",3.6937,-0.1021,2.2565,0.6277,8.231,2.172);hideObject("Walls.004");addToCollisionList("Walls.004");
  createObjectwithScale("Walls.002", "cube",-11.9755,-4.2484,2.2565,0.6277,7.2022,2.172);hideObject("Walls.002");addToCollisionList("Walls.002");
  createObjectwithScale("Walls.005", "cube",-11.9755,4.4365,2.2565,0.6277,2.7894,2.172);hideObject("Walls.005");addToCollisionList("Walls.005");
  
  createObject('player','cube',0,0,3)
  setCollisionController('player',0)

# Small update to navigate the scene and collect coins
def update():
  moveObjectwithRotationScale('player',0,0,(-0.1),0,0,0,0,0,0)
  global coins
  if isButtonUp():
    moveObjectwithRotationScale('player',(-0.1),0,0,0,0,0,0,0,0)
  if isButtonDown():
    moveObjectwithRotationScale('player',0.1,0,0,0,0,0,0,0,0)
  if isButtonRight():
    moveObjectwithRotationScale('player',0,0.1,0,0,0,0,0,0,0)
  if isButtonLeft():
    moveObjectwithRotationScale('player',0,(-0.1),0,0,0,0,0,0,0)
  if isObjectClass('coin',(getLastCollisionName())):
    deleteObjectClass((getLastCollisionName()))
```

## Nice Scene Transition
