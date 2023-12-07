Use this tutorial to help you create a SpriteFont (Text's fonts based on a spritesheet) on Leap!

## Generate the SpriteFont

We will first generate the spritefont from a font installed on your system (eg. TTFs files installed) using a software named GiveYourFontsMono. Get GiveYourFontsMono (it's portable) on https://shatter-box.com/download/giveyourfontsmono/
Extract the software's zip and open GYFM3.exe:

[IMAGE OF GYFM]

Now you can select the font you want to generate the spritesheet from, and the size you would like.
Then type in the top text box the character set you want to include in your spritesheet. More characters you have, bigger it'll be. For example choose "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789,:!?" to have an extensive character set and click Refresh to see what it would look like.

You can set also the margin settings at the bottom, by checking at the preview to setup the best parameters (you can also change the preview's text.

## Exporting the SpriteFont

Click Save to export the SpriteFont. That will create the actual SpriteFont which will be the image containing a spritesheet for all the characters, but also a text file to setup it.
Install an image editing software such as Paint.NET (available for free online). Open the spritesheet in your image editing software (with pixel capabilities):

[IMAGE OF SPRITESHEET IN PAINT.NET]

Now count how much characters there's on all the lines and columns.
Here for example we have 7 lines, and 10 columns. Note this somewhere, it'll be needed. We will now resize the image to fit exactly our character set, that way: open "Change Image Zone", and set in width the number of columns MULTIPLIED by the width of each character (that you can find in the image's filename), and in height the number of columns MULTIPLIED by the height of each character. Set top-left as anchor's crop:

[RESULT OF SPRITESHEET IN PAINT.NET]

Save the image, and put it in assets folder of your project's scene in Leap.

## Use the SpriteFont

For the image, we're all set! We now just have to setup the correct spacing data for each character, as some letters take less space than others (for example the "i" character). For that, open the text file that was generated:

Now copy the text array "for Construct 3 ONLY":

Paste in this utility, which is a Python script, along the character set that is at top:

```python
import json

# Your character set
character_set = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789,:!?"

# Your JSON array
json_array = '[[7," "],[5,"il"],[6,"jI,:!"],[9,"r1"],[10,"ftJ"],[13,"nzL"],[14,"hsuvxyF23679?"],[15,"abcdegkpqT0458"],[16,"oENPZ"],[17,"BHKRUV"],[18,"ACDGSXY"],[19,"MO"],[21,"wQ"],[22,"m"],[23,"W"]]'

# Parse the JSON array
width_data = json.loads(json_array)

# Create a dictionary to map characters to their widths
width_map = {}
for width, chars in width_data:
    for char in chars:
        width_map[char] = width

# Create the array of widths corresponding to the order of the character set
widths = [width_map[char] for char in character_set]

print(widths)
```

You get the spacing data compatible with Leap in output!
We now just have to copy this snippet with these values to have our SpriteFont on Leap:

```python
createAssetSpriteSheet("your_font_name", LINES, COLUMNS, """YOUR SPACING DATA""",
"YOUR CHARACTER SET", "YOUR_FONT_IMAGE_NAME.png");
createSpritefontText("UI_Score", 30, 420, 20, 101, "Score:0", "your_font_name")
```

Example with our SpriteFont:

```python
createAssetSpriteSheet("font_com", 7, 10, """[15,15,15,15,15,10,15,14,5,6,15,5,22,13,16,15,15,9,14,10,14,14,
21,14,14,13,18,17,18,18,16,14,18,17,6,10,17,13,19,16,19,16,21,17,18,15,17,17,23,18,18,16,15,9,14,14,15,15,14,
14,15,14,6,6,6,14]""",
"abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789,:!?", "SFB.png");
createSpritefontText("UI_Score", 30, 420, 20, 101, "Score:0", "font_com")
```

And you're good to go! Congratulations.

[IMAGE OF RESULT]
    
