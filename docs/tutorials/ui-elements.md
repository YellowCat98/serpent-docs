# UI Elements
- To do anything UI related, you will have to hook the MenuLayer_init function. as it is reponsible for UI elements.

- Lets try adding a label to the main menu!
```python
def MenuLayer_init(self, this):
    if not this.init(): return False # Make sure to call original (otherwise the UI will be BLACK.)
    label = CCLabelBMFont.create("Hello, World!", "bigFont.fnt") 
    this.addChild(label)
    return True
```
- Now we have a label that says "Hello, World!", though the label is placed in the bottom corner, to fix this, we have to do some positioning!

```python
def MenuLayer_init(self, this):
    if not this.init(): return False
    label = CCLabelBMFont.create("Hello, World!", "bigFont.fnt")
    label.setPosition(CCPoint(6, 9)) # This moves the label to X position 6, and Y position 9.
    this.addChild(label)
    return True
```

# Node IDs
- Geode has a little feature added into cocos2d, which is Node IDS!
- What is a Node ID? its a string, which is linked to a UI element, some nodes don't have Node IDs though, to check, it is recommended to install the Dev Tools mod.

## Getting a child node through a Node ID
- We use the `CCNode.getChildByID` function, what is a CCNode? its just everything you see on the screen, under the hood, everything derives from CCNode.

- Example:
```python
def MenuLayer_init(self, this):
    if not this.init(): return False
    menu = this.getChildByID("bottom-menu") # This retrieves a CCMenu of ID bottom-menu.
    # Do something with `menu`
    return True
```

