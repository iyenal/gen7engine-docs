**Example: Create procedurally objects**

In this example, we'll use lists to create procedurally objects.  
This project is included in your Gen7 folder.

## Project overview:

We have imported 3 sprites in our project (see File Explorer), and rearranged the layout to the following.  
We can enable too the Auto-Preview feature to immediately see any changes in live.

[![image.png](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.thumb.png.975b043a4b390c8a9e54fd2a61a7a057.png)](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.png.d9de1aee98e184ec22e5109dcaa07ce7.png)

## Our visual programming script

**On start:**

![image.png](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.png.b926671750a95cb5182c4a0576994411.png)

We create a global list, creating and storing our procedurally created objects (the maces) in **Start** block, and manipulating them later in **Update** block.

We set up our scene with a background and a player, and then a loop to create our procedural objects with an unique name, stored in the previously created list.  
For debug purposes, we log the name of our objects stored in the array just after to check their conformity:

![image.png](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.png.9723cb5cd7a9e664c1dd3741c3e6fab6.png)

We have now tile1 to tile5 objects, rendered as the 5 maces at the bottom of our scene.

![image.png](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.png.9611673455ae5f24ebdf790fc7e883e3.png)

**On update:**

At every update, we check if the button Right is pressed, and we move the player and our sprites generated procedurally together by referring to the list storing their names.

![image.png](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.png.50d79a9a47f9d7a7b7085716a560f923.png)

## Let's test!

We play our application to check our behaviour:

![image.png](http://www.gen7.idpowered.com/forums/ips/uploads/monthly_2022_10/image.png.ea82288f3d3fb4815de2aca032f9b598.png)

It's working great!