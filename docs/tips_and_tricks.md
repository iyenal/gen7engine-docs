# Tips & Tricks

Some tips that will save you time and energy when using Gen7.

### Using an External Code Editor

You can use an external Code Editor (such as Visual Studio Code, SublimeText...) to edit your project script (in Python mode) and see the changes reflected in Gen7. To do so, just open the proj.py file in your project folder in your editor. Everytime you will preview in-engine (top Preview button), Gen7 Engine will load your changes and reflect them in the internal editor.

### Debugging events? createLog() Magic

When you're not sure a specific block of code is reached, being involved by a specific event or not, use createLog('text or character') in that block to know it clearly. "createLog()" will log the text on your game, using an internal monospaced font so it doesn't need any asset. Just make sure to use createLog() reasonably, as it's very heavy on performance (due to its fail-safe nature) and limited to approximately 200 characters on all the game, so disable the unnecessary calls. 

### Automatic Preview, Quick Camera Tests

You can automatically generate a new preview when you save your script or visual program, just enable the Auto Preview checkbox (next to the Preview button). You can also enable the camera toolbox (bottom of Preview), to directly change its parameters there and check immediately the result. Just make sure that your program doesn't have a "setCamera" call that would otherwise override the toolbox camera setup.
In case of scenes, the Preview will automatically preview the current scene loaded. Make sure before to build to set the project in the main scene, so in the final build the application/game will start with it.

### Delta time? Ensure the same behavior no matter the framerate

Use setTargetFPS(XX) to make sure that your update code (code that's executed repeatedly each frame) will be executed as much as you specify in setTargetFPS (eg. 45 or 60), no matter the actual framerate in-game. The engine will compensate for lower framerates by executing the update 2 times more, and for higher framerates by executing update only on half of the render framerates for example.
That way you're sure that even by targeting multiple platforms and therefore multiple performance rates, the behavior will be identical.
You can also monitor performance with "timeSinceStartup()" and "timeSinceFrameMs()".

### Save files, JSON parsing

You can save files in case you want for example to have savegames, or to load levels, and then read them as a text (string) with openFile().
Gen7 Engine also has a Python JSON parsing library available through "import json".

### IDE crash logs

In case of IDE crashes, a log is written in the logs folder. That log can be useful to investigate the issue.
Feel free to add it in case of an issue creation, or in the Discord Server when seeking support.
