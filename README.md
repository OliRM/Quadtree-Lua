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
