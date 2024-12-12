# Buttons
- In RobTop's version of cocos, most buttons are CCMenuItemSpriteExtra's, the way they work is like this:
- You make a callback function with `sender` as the first argument, then create a CCMenuItemSpriteExtra through its `create()` method, this is the function signature.
- `CCMenuItemSpriteExtra::create(my_sprite, this, menu_selector(MyFunction));`
- This is C++, but since i have literally no idea on how i would get menu_selector working through python, we will use geode's awesome `CCMenuItemExt.createSpriteExtra` method, here's some example code:

```python
# `sender`: is the button that uses this function as a callback.
def my_function_callback(self, sender):
    self.script.info("Hello, World, This is from a button!")

def MenuLayer_init(self, this):
	if not this.init(): return False
	button = CCMenuItemExt.createSpriteExtra(CCSprite.createWithSpriteFrameName("GJ_arrow_01_001.png"), my_function_callback)
	menu = this.getChildByID("bottom-menu")

	return True
```

- This will put a button in the button menu! like this:
![The image](../img/buttons-test-img.png)

# Complete code:
- Since this is kinda complex. this is the complete source if you wanna just copy and paste!

```python
class buttons_yellowcat98:
	def __init__(self):
		self.script = script("buttons_yellowcat98", self)
		self.script.initAllHooks()

	def callback(self, sender):
                FLAlertLayer.create("Hello", "Hello World", "thanks").show()

	def MenuLayer_init(self, this):
		if not this.init(): return False
		button = CCMenuItemExt.createSpriteExtra(CCSprite.createWithSpriteFrameName("GJ_arrow_01_001.png"), self.callback)
		this.getChildByID("bottom-menu").addChild(button)
		return True

if __name__ == "__main__":
        buttons_yellowcat98()
```