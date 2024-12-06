# Buttons
- In RobTop's version of cocos, most buttons are CCMenuItemSpriteExtra's, the way they work is like this:
- You make a callback function with `sender` as the first argument, then create a CCMenuItemSpriteExtra through its `create()` method, this is the function signature.
- `CCMenuItemSpriteExtra::create(my_sprite, this, menu_selector(MyFunction));`
- This is C++, but since i have literally no idea on how i would get menu_selector working through python, we will use geode's awesome `CCMenuItemExt.createSpriteExtra` method, here's some example code:

