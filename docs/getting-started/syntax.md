# Script syntax
- Your script is required to have a class (in which you guessed must have the same name as the ID!!)
- Each class must have an instance of the built-in class `script`, which its constructor takes two arguments, which are:
> ID: the ID of your script!
> mainClass: your script's class.

- Syntax example:
```py
# Serpent binds all geode and cocos functions/classes into __main__, you do not need to import any modules.

class simplescript_yellowcat98:
    def __init__(self):
        self.script = script("simplescript_yellowcat98", self)

if __name__ == "__main__":
    simplescript_yellowcat98() # Initailze an instance of simplescript_yellowcat98, this will be executed on startup.
```
- Now we have a script that does NOTHING!
- What can you do with it? nothing basically because uhh it does nothing other than initialize a new script, it should execute if it's enabled though.

- (make sure its enabled because serpent doesn't enable scripts by default)

- Now all that's left is to package it into a .zip file, the .zip file MUST have the same filename as the ID.