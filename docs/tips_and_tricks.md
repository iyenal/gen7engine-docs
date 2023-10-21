# Tips & Tricks

Some tips that will save you time and evergy when using Gen7.

### Using an External Code Editor

You can use an external Code Editor (such as Visual Studio Code, SublimeText...) to edit your project script (in Python mode) and see the changes reflected in Gen7. To do so, just open the proj.py file in your project folder in your editor. Everytime you will preview in-engine (top Preview button), Gen7 Engine will load your changes and reflect them in the internal editor.

### Automatic Preview, Quick Camera Tests

You can automatically generate a new preview when you save your script or visual program, just enable the Auto Preview checkbox (next to the Preview button). You can also enable the camera toolbox (bottom of Preview), to directly change its parameters there and check immediately the result. Just make sure that your program doesn't have a "setCamera" call that would otherwise override the toolbox camera setup.

### Save files, JSON parsing, get from internet

Gen7 Engine has a Python JSON parsing library available through "import json". This can be used too with the experimental "download file" function calls.
You can also save files in case you want for example to have savegames, and then read them as a text (string).

### IDE crash logs

In case of IDE crashes, a log is written in the logs folder. That log can be useful to investigate the issue.
Feel free to add it in case of an issue creation, or in the Discord Server when seeking support.
