# Hooks

- What is a hook?

- A hook is basically just a thing where you redirect a function call to another, a lot mods (not just GD mods!) rely on function hooking.

- How does Serpent handle function hooking?
- Serpent looks for a `ClassName_FunctionName` function within your script's class, if it exists, then it would hook `ClassName::FunctionName` (note that `ClassName::FunctionName` should be a function available to hook within Serpent and geode itself for the hook to be initialized!)

# Creating a simple hook

- Let's replace the MenuLayer's onMoreGames function!

- ### Steps:

- We define a function named `MenuLayer_onMoreGames` within our script's class.
- then pass `self, this` as the first two arguments, Serpent requires these two arguments so we'd be able to call the original if we need to (we will explain what an original is later.)
- Then we just pass whatever arguments `MenuLayer_onMoreGames` takes, in this case it's a single argument, it can have any name you want.
- Our function's signature is: `MenuLayer_onMoreGames(self, this, sender)`

- #### Code:

```python
class simplescript_yellowcat98:
    def __init__(self):
        self.script = script("simplescript_yellowcat98", self)

    def MenuLayer_onMoreGames(self, this, sender):
        popup = FLAlertLayer.create("Popup Title", "This is the body of a popup.", "i think this is the button!") # create a popup.
        popup.show() # show the popup to the screen!

if __name__ == "__main__":
    simplescript_yellowcat98()
```

- Now you have hooked a function! 

# Calling the Original
- What is the original in terms of function hooking?
- It's just the function you hooked, since all hooking does it just redirect function calls, the original in fact still exists and is callable!

- In Serpent, we take advantage of the `this` argument, `this` is of type MenuLayer, MenuLayer is a class which contains the original.

- Let's call the original in a MenuLayer_onQuit hook!
- (the onQuit function is the function that gets called when you press the X button in the main menu.)


```python
def MenuLayer_onQuit(self, this, sender):
    self.script.info("Before original!")
    this.onQuit(sender) # Make sure to pass any required arguments! excluding `self, this`
    self.script.info("After original, btw this info function prints to the geode platform console because the regular print function doesnt show you the script's name!")
```