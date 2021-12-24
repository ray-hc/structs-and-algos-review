# Classes, Inheritance in Python

```Python
class Mammal:
    def __init__(self, x, y):
        self.x = x
        self.y = y 

    def walk(self):
        print(“walk”)

class Dog(Mammal):
    def bark(self):
        print(“bark”)
```