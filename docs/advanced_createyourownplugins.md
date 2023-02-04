**Advanced: Creating your own plugins**

You can create your own plugins to create new behaviors, ease development and implement specific systems such as collision or physics.  
These plugins can be redistributed at your ease to extend Gen7 Engine.  
 

### Python implementation specification

Gen7 Engine uses the official micropython interpreter implementation:

> Quote
> 
> MicroPython implements the entire Python 3.4 syntax (including exceptions, with, yield from, etc., and additionally async/await keywords from Python 3.5 and some select features from later versions). The following core datatypes are provided: str(including basic Unicode support), bytes, bytearray, tuple, list, dict, set, frozenset, array.array, collections.namedtuple, classes and instances. Note that only a subset of Python 3 functionality is implemented for the data types and modules.  
>   
> Gen7 Engine uses _MICROPY\_CONFIG\_ROM\_LEVEL\_CORE\_FEATURES_ profile and all the modules related, provides the urandom module, and Gen7 API writeFile and openFile for file I/O.  
> Python native print is unrecommended: use createLog from Gen7. createLog should however only be used for debug as it has a large footprint on performance. (Temporary)

### Python's plugin specification

Define your custom methods in _editor\\plugins\\python.py ._  
These methods can use Gen7 API, and be interfaced to visual programming blocks that will be specified in the XML file.

### Blocks creation

Define your blocks in _blocks.xml_ and link them to your custom methods defined _python.py._ For that, use the [Blockly Developer Tools](https://blockly-demo.appspot.com/static/demos/blockfactory/index.html):

[![image.png](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.thumb.png.1155c698638f2ff54c12bdf98179a6ae.png)](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.png.ab99bbd2183ac77f1d1ee3af63f863f7.png)