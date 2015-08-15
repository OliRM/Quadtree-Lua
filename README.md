# LuaQuadtree
A basic quadtree type for retrieving potential collisions

![example quadtree](https://cloud.githubusercontent.com/assets/8511306/9291243/e1edad9c-43f7-11e5-8956-a5894201bbca.png)

## Methods

The datatype to be used for inserting and retrieving "object" is defined as:

``` Lua
object = {}
object.left   = _
object.top    = _
object.width  = _
object.height = _
```

##### Quadtree.create(left, top, width, height, depth = 0, maxObjects = 10, maxDepth = 5)

Creates the quadtree


##### Quadtree:insert(object)

Inserts an object into the quadtree

##### Quadtree:collidables(object)

Fetches a table of objects that potentially collide with the provided object

##### Quadtree:clear()

Clears all objects in the quadtree, and its children

## Example

``` Lua
-- example.lua

-- Get the library
Quadtree = require "quadtree"

-- Create a quadtree at position (0, 0,) with dimensions of (640, 480)
quadtree = Quadtree.create(0, 0, 640, 480)

-- Insert an object at position (64, 64) with dimensions (128, 128)
quadtree:insert({left = 64, top = 64, width = 128, height = 128)

-- Retrieve potential collisions with object at position (32, 32) with dimensions (128, 128)
local objects = quadtree:collidables({left = 32, top = 32, width = 128, height = 128})
```
