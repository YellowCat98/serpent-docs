# Sprites
- Sprites in Serpent are called CCSprite, in order to create a CCSprite, we call the static method `CCSprite.create()`, which takes a single argument and returns a CCSprite. CCSprite is a CCNode, so we can add it as a child node to other nodes!

- Example:
```python
def MenuLayer_init(self, this):
    if not this.init(): return False
    winSize = CCDirector.get().getWinSize()
    sprite = CCSprite.create("<spriteName>.png") # Remember, this doesn't get sprites from spritesheets, we need a different method for that!
    sprite.setPosition(CCPoint(winSize.width / 2, winSize.height / 2)) # Place the sprite in the middle of the screen.
    return True
```

# Sprites from Spritesheets

- It's pretty simple, instead of calling the static method `CCSprite.create` we call `CCSprite.createWithSpriteFrameName`, here's an example!

```python
def MenuLayer_init(self, this):
    if not this.init(): return False
    sprite = CCSprite.createWithSpriteFrameName("GJ_arrow_01_001.png") # GJ_arrow_01_001.png is a sprite from the GJ_gamesheet_03.png spritesheet, though it does not matter!
    return True
```