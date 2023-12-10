Use these script examples and templates to help you develop parts of your game/application.
These can be recreated in Visual Programming with the corresponding blocks.

## Scene Transition

**Description:**  
Cool scene transition with circular opening/closing animation.
![image](https://github.com/iyenal/gen7engine-docs/assets/14296095/dd382de7-977f-4561-8d2f-f6165de809f9)

**Usage:**  
Copy and paste the script at top of your script. 
Then use in your start method to start it closed and get it to open:
```python
def start():
    global tr
    tr = TransitionAnim()
    tr.initClosed()
    tr.startOpen()
```
If you wish to close it and go to another Scene:
```python
def update():
    tr.update()
    global go_to_level # create a go_to_level = 0 after "tr = None" so we can load the scene after the transition is finished
    if(isTriggerA()):
        tr.startClose()
        go_to_level = timeSinceStartup()

    if(go_to_level != -1 and timeSinceStartup() > go_to_level+5 ): # Go to level 5 secs after it clicked A button (time that transition anim finishes)
        LoadScene("assets/first_level/")
```
Make sure to have "tr.update()" in your update method.

**Script:**

```python

class TransitionAnim:
    anim_trans = 1001
    def __init__(self):
        createAssetTexture("transition", "anim_transition.png");
        pass

    def initClosed(self):
        size = 1000;
        createSprite("trans", "transition", 320-(size/2),240-(size/2),size,size,100);
        createSpriteWithColor("trans_top", "", -(size/2), 240 + (size/2) -5,1000,1000,  28,28,28,  100); # TOP, +15 to hide thin lines (because pixel precision)
        createSpriteWithColor("trans_bot", "", -(size/2), 240 - (size/2) -1000 +5,1000,1000,   28,28,28,   100); # BOTTOM
        createSpriteWithColor("trans_right", "", 320+(size/2) - 5, -100,1000,1000,   28,28,28,   100); # RIGHT
        createSpriteWithColor("trans_left", "", 320-(size/2)-1000 +5, -100,1000,1000,   28,28,28,  100); # LEFT

        size = 1;
        setSprite("trans", 320-(size/2),240-(size/2),size,size,  100);
        setSprite("trans_top", -(size/2), 240 + (size/2) -2,1000,1000,  100); # TOP, +15 to hide thin lines (because pixel precision)
        setSprite("trans_bot", -(size/2), 240 - (size/2) -1000 +2,1000,1000,  100); # BOTTOM
        setSprite("trans_right",320+(size/2) - 2, -100,1000,1000,   100); # RIGHT
        setSprite("trans_left", 320-(size/2)-1000 +2, -100,1000,1000,   100); # LEFT
        pass

    def initOpen(self):
        size = 1000;
        createSprite("trans", "transition", 320-(size/2),240-(size/2),size,size,100);
        createSpriteWithColor("trans_top", "", -(size/2), 240 + (size/2) -5,1000,1000,  28,28,28,  100); # TOP, +15 to hide thin lines (because pixel precision)
        createSpriteWithColor("trans_bot", "", -(size/2), 240 - (size/2) -1000 +5,1000,1000,   28,28,28,   100); # BOTTOM
        createSpriteWithColor("trans_right", "", 320+(size/2) - 5, -100,1000,1000,   28,28,28,   100); # RIGHT
        createSpriteWithColor("trans_left", "", 320-(size/2)-1000 +5, -100,1000,1000,   28,28,28,  100); # LEFT

        size = 1000;
        setSprite("trans", 320-(size/2),240-(size/2),size,size,  100);
        setSprite("trans_top", -(size/2), 240 + (size/2) -2,1000,1000,  100); # TOP, +15 to hide thin lines (because pixel precision)
        setSprite("trans_bot", -(size/2), 240 - (size/2) -1000 +2,1000,1000,  100); # BOTTOM
        setSprite("trans_right",320+(size/2) - 2, -100,1000,1000,   100); # RIGHT
        setSpriteP("trans_left", 320-(size/2)-1000 +2, -100,1000,1000,   100); # LEFT

    def startOpen(self):
        if(self.anim_trans > -1):
            self.anim_trans = -1

    def startClose(self):
        if(self.anim_trans < 0):
            self.anim_trans = 0

    def update(self):

        if(self.anim_trans > -1000 and self.anim_trans < 1000):

            # Close animation
            if(self.anim_trans >= 0):
                if(self.anim_trans == 0):
                    pass

                if(self.anim_trans > 0):
                    size = 1000-self.anim_trans;
                    setSprite("trans", 320-(size/2),240-(size/2),size,size,  100);
                    setSprite("trans_top", -(size/2), 240 + (size/2) -2,1000,1000,  100); # TOP, +15 to hide thin lines (because pixel precision)
                    setSprite("trans_bot", -(size/2), 240 - (size/2) -1000 +2,1000,1000,  100); # BOTTOM
                    setSprite("trans_right",320+(size/2) - 2, -100,1000,1000,   100); # RIGHT
                    setSprite("trans_left", 320-(size/2)-1000 +2, -100,1000,1000,   100); # LEFT

                self.anim_trans+=5;

            # Open animation
            if(self.anim_trans <= -1):

                if(self.anim_trans == -1):
                    pass

                if(self.anim_trans < -1):
                    size = -self.anim_trans;
                    setSprite("trans", 320-(size/2),240-(size/2),size,size,  100);
                    setSprite("trans_top", -(size/2), 240 + (size/2) -2,1000,1000,  100); # TOP, +15 to hide thin lines (because pixel precision)
                    setSprite("trans_bot", -(size/2), 240 - (size/2) -1000 +2,1000,1000,  100); # BOTTOM
                    setSprite("trans_right",320+(size/2) - 2, -100,1000,1000,   100); # RIGHT
                    setSprite("trans_left", 320-(size/2)-1000 +2, -100,1000,1000,   100); # LEFT

                self.anim_trans-=5;

tr = None
```

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
